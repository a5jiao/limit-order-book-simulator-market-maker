# limit-order-book-simulator-market-maker

**Goal**: Demonstrate advanced understanding of market microstructure, high-performance system design, and algorithmic market making strategies suitable for elite proprietary trading firms.  
**Status**: In Progress (v0.1)

---

## 🧠 Project Overview

This project is a high-fidelity simulation environment for a financial **Limit Order Book (LOB)** and multiple **Market Making (MM)** strategies, designed to mirror real-world exchange behavior and HFT trading systems.

The simulator models:
- A live LOB with price-time priority and matching logic
- Multi-agent environments with market makers and flow providers
- Advanced MM strategies like **Avellaneda-Stoikov**, **Glosten-Milgrom**, and **alpha-driven quoting**
- Risk management, delta hedging, latency modeling, and ML integration for predictive quoting

### 🎯 Target Audience
This project is explicitly built to showcase skills relevant for:
- Proprietary trading firms (e.g., Jane Street, HRT, Optiver, IMC, SIG)
- Quant hedge funds and market makers
- Interviews focused on microstructure, execution algorithms, or strategy research

---

## 💼 Project Motivation

Modern electronic markets operate on *sub-millisecond timescales* with complex LOB dynamics, adverse selection, and execution risk. The goal of this simulator is to build:

- A **production-style system** that mimics core exchange functionality
- **Market making agents** that intelligently quote prices based on volatility, inventory, and flow
- A sandbox for testing MM strategies under realistic constraints

---

## 📌 Key Features (Planned & In Progress)

### ✅ Core Infrastructure
- [x] Limit Order Book engine with full order type support (limit, market, IOC, GTC)
- [x] Price-time priority and FIFO queuing
- [ ] Synthetic & historical market data simulation
- [ ] Market event replay engine
- [ ] Customizable simulation config (latency, volatility, capital, etc.)

### 📉 Market Making Strategies
- [x] Naive symmetric MM
- [ ] **Avellaneda-Stoikov** inventory-sensitive quoting model
- [ ] **Glosten-Milgrom** information-based pricing
- [ ] **Alpha-driven MM** based on predictive signal skewing

### 🛡️ Risk Management
- [ ] Position tracking and real-time PnL
- [ ] Portfolio-level exposure and drawdown limits
- [ ] Delta-neutral hedging logic
- [ ] Execution model for realistic fills and slippage

### ⚡ Performance Engineering
- [ ] Sub-millisecond order matching
- [ ] Memory pooling and vectorized calculations
- [ ] `Cython` acceleration for critical paths

### 📊 Analytics & Visualization
- [ ] Real-time inventory and PnL dashboards
- [ ] Order book depth and trade heatmaps
- [ ] Trade logs, fill ratios, latency impact plots
- [ ] Backtest report generator

### 🤖 Machine Learning (Stretch Goal)
- [ ] LOB feature extraction (imbalance, spread, flow toxicity)
- [ ] ML model for predicting short-term midprice movement
- [ ] Alpha integration into MM quoting logic

---

## 🗂️ Project Structure

