# Architecture - Renaissance V3+

## Overview

Renaissance V3+ implements a complete ML trading pipeline with the following architecture:

## Pipeline Flow

```
Data Ingestion → Dollar Bars → Feature Engineering → ML Training → Validation → Inference
```

## Components

### 1. Data Ingestion (`src/data_ingestion/`)
- Real-time and historical data from Binance (CCXT)
- WebSocket streaming
- Asynchronous processing

### 2. Processing (`src/processing/`)
- Dollar Bars re-sampling
- Polars Lazy API for massive data processing
- Parquet storage with zstd compression

### 3. Feature Engineering (`src/feature_engineering/`)
- FracDiff (fractional differentiation)
- TDA (Topological Data Analysis)
- Microstructure features (VPIN, OBI)
- Candlestick patterns
- Technical indicators

### 4. Modelling (`src/modelling/`)
- Meta-Labeling architecture (M1: XGBoost + M2: CatBoost)
- Hyperparameter optimization
- Cross-validation (PurgedKFold)

### 5. Validation (`src/validation/`)
- CPCV (Combinatorial Purged Cross-Validation)
- DSR (Deflated Sharpe Ratio)
- Backtesting framework

### 6. Execution (`src/execution/`)
- Real-time inference
- Apple Silicon optimization (CoreML)
- Risk management

## Data Flow

```
Binance API → Polars Processing → Parquet Storage (SSD External)
                                      ↓
                            Feature Engineering
                                      ↓
                            ML Pipeline (M1+M2)
                                      ↓
                            Validation (CPCV, DSR)
                                      ↓
                            CoreML Inference (< 100ms)
```

## Storage

- **External SSD** : `/Volumes/Lacie/Renaissance_Data/`
- **Format** : Parquet with zstd compression
- **Partitioning** : By date and symbol
- **Scale** : Tera-bytes of data

## Performance

- **Latency** : < 100ms for real-time inference
- **Throughput** : Handles Tera-bytes of data
- **Memory** : Optimized for 36GB RAM (M4 Max)

