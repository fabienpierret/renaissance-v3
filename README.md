# Renaissance V3+ - ML Trading Pipeline

**Complete ML trading pipeline with advanced data engineering, feature engineering, and scientific validation. Optimized for Apple Silicon.**

[![Python](https://img.shields.io/badge/Python-3.11+-blue.svg)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Apple Silicon](https://img.shields.io/badge/Apple%20Silicon-M4%20Max-purple.svg)](https://www.apple.com/mac-studio/)

---

## 🎯 Overview

Renaissance V3+ is a complete machine learning trading system that demonstrates advanced data engineering, feature engineering, and ML pipeline orchestration. The system processes Tera-bytes of crypto market data from Binance, implements 50+ advanced features, and uses scientific validation methods (CPCV, DSR) for model evaluation.

**Key Highlights** :
- ✅ **Data Engineering** : Complete pipeline from ingestion to storage (Tera-bytes of crypto data)
- ✅ **Feature Engineering** : Advanced features (FracDiff, TDA, Microstructure, Patterns)
- ✅ **ML Pipeline** : Meta-Labeling architecture (M1: XGBoost + M2: CatBoost)
- ✅ **Scientific Validation** : Implements CPCV (Combinatorial Purged Cross-Validation) and DSR (Deflated Sharpe Ratio)
- ✅ **Apple Silicon Optimized** : Optimized for M4 Max with < 100ms latency
- ✅ **Massive Data Processing** : Handles Tera-bytes of data with Polars Lazy API

---

## 🛠️ Technologies

- **Python** 3.11+
- **Polars** (Lazy API for massive data processing)
- **Parquet** (Optimized storage with zstd compression)
- **XGBoost, CatBoost** (Meta-Labeling architecture)
- **CoreML** (Apple Silicon optimization)
- **CCXT** (Crypto exchange integration)

---

## 📊 Architecture

```
┌─────────────────┐
│  Data Ingestion │  (Binance, CCXT, WebSockets)
└────────┬────────┘
         │
┌────────▼────────┐
│  Dollar Bars    │  (Re-sampling, Polars)
└────────┬────────┘
         │
┌────────▼────────┐
│ Feature Eng.    │  (FracDiff, TDA, Microstructure)
└────────┬────────┘
         │
┌────────▼────────┐
│  ML Pipeline    │  (M1: XGBoost + M2: CatBoost)
└────────┬────────┘
         │
┌────────▼────────┐
│  Validation     │  (CPCV, DSR)
└─────────────────┘
```

---

## 🚀 Key Features

### **1. Data Engineering**
- **Ingestion** : Real-time and historical data from Binance (CCXT)
- **Processing** : Dollar Bars re-sampling with Polars Lazy API
- **Storage** : Parquet format with zstd compression on external SSD
- **Scale** : Handles Tera-bytes of data efficiently

### **2. Feature Engineering**
- **FracDiff** : Fractional differentiation (d=0.4, window=100)
- **TDA** : Topological Data Analysis (Betti Numbers, Persistence Entropy)
- **Microstructure** : VPIN, OBI (Order Book Imbalance)
- **Patterns** : Candlestick pattern detection
- **Technical** : RSI, MACD, Bollinger Bands, ATR

### **3. Machine Learning**
- **Architecture** : Meta-Labeling (M1: XGBoost + M2: CatBoost)
- **Validation** : CPCV (Combinatorial Purged Cross-Validation)
- **Metrics** : DSR (Deflated Sharpe Ratio), Sharpe Ratio, Profit Factor
- **Optimization** : Hyperparameter tuning with cross-validation

### **4. Apple Silicon Optimization**
- **M4 Max** : Optimized for 36GB RAM
- **Latency** : < 100ms for real-time inference
- **CoreML** : Model optimization for Apple Silicon
- **Local-First** : All processing local (no cloud dependencies)

---

## 📈 Results

- **Data Processed** : Tera-bytes of crypto market data
- **Features** : 50+ engineered features
- **Validation** : Scientific validation with CPCV and DSR
- **Performance** : < 100ms latency on M4 Max

---

## 📝 Status

**Phase** : Completed - Infrastructure ready for production use

**Completed** :
- ✅ Complete data ingestion pipeline
- ✅ Feature engineering (50+ features)
- ✅ ML pipeline with Meta-Labeling
- ✅ Scientific validation (CPCV, DSR)
- ✅ Apple Silicon optimization

**Note** : This project demonstrates advanced ML/data engineering skills. The trading strategy results were mixed, but the infrastructure has significant technical value.

---

## 🔗 Links

- **Portfolio** : [fabienpierret.github.io/projects/renaissance](https://fabienpierret.github.io)
- **Author** : [Fabien Pierret](https://github.com/fabienpierret)

---

## 📄 License

MIT License - See LICENSE file for details

---

**Built with ❤️ for demonstrating advanced ML/data engineering capabilities**

