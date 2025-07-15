# limit-order-book-simulator-market-maker

**Goal**: Demonstrate advanced understanding of market microstructure, high-performance system design, and algorithmic market making strategies suitable for elite proprietary trading firms.  
**Status**: In Progress (v0.1)

---

## Project Overview

This project is a high-fidelity simulation environment for a financial **Limit Order Book (LOB)** and multiple **Market Making (MM)** strategies, designed to mirror real-world exchange behavior and HFT trading systems.

The simulator models:
- A live LOB with price-time priority and matching logic
- Multi-agent environments with market makers and flow providers
- Advanced MM strategies like **Avellaneda-Stoikov**, **Glosten-Milgrom**, and **alpha-driven quoting**
- Risk management, delta hedging, latency modeling, and ML integration for predictive quoting

---

## \Project Motivation

Modern electronic markets operate on *sub-millisecond timescales* with complex LOB dynamics, adverse selection, and execution risk. The goal of this simulator is to build:

- A **production-style system** that mimics core exchange functionality
- **Market making agents** that intelligently quote prices based on volatility, inventory, and flow
- A sandbox for testing MM strategies under realistic constraints

---

## Key Features (Planned & In Progress)

### Core Infrastructure
- [x] Limit Order Book engine with full order type support (limit, market, IOC, GTC)
- [x] Price-time priority and FIFO queuing
- [ ] Synthetic & historical market data simulation
- [ ] Market event replay engine
- [ ] Customizable simulation config (latency, volatility, capital, etc.)

### Market Making Strategies
- [x] Naive symmetric MM
- [ ] **Avellaneda-Stoikov** inventory-sensitive quoting model
- [ ] **Glosten-Milgrom** information-based pricing
- [ ] **Alpha-driven MM** based on predictive signal skewing

### Risk Management
- [ ] Position tracking and real-time PnL
- [ ] Portfolio-level exposure and drawdown limits
- [ ] Delta-neutral hedging logic
- [ ] Execution model for realistic fills and slippage

### Performance Engineering
- [ ] Sub-millisecond order matching
- [ ] Memory pooling and vectorized calculations
- [ ] `Cython` acceleration for critical paths

### Analytics & Visualization
- [ ] Real-time inventory and PnL dashboards
- [ ] Order book depth and trade heatmaps
- [ ] Trade logs, fill ratios, latency impact plots
- [ ] Backtest report generator

### Machine Learning (Stretch Goal)
- [ ] LOB feature extraction (imbalance, spread, flow toxicity)
- [ ] ML model for predicting short-term midprice movement
- [ ] Alpha integration into MM quoting logic

---

## Project Structure
```
lob_mm_simulator/  
├── src/  
│   ├── order_book/  
│   │   ├── __init__.py  
│   │   ├── engine.py              # Core LOB matching engine  
│   │   ├── orders.py              # Order types and validation  
│   │   ├── market_data.py         # L1/L2 data generation  
│   │   └── book_state.py          # Order book state management  
│   ├── strategies/  
│   │   ├── __init__.py  
│   │   ├── base_strategy.py       # Abstract strategy interface  
│   │   ├── avellaneda_stoikov.py  # Optimal MM strategy  
│   │   ├── glosten_milgrom.py     # Information-based MM  
│   │   ├── alpha_mm.py            # Alpha-driven MM  
│   │   └── naive_mm.py            # Simple spread-based MM  
│   ├── risk_management/  
│   │   ├── __init__.py  
│   │   ├── position_manager.py    # Position tracking  
│   │   ├── risk_limits.py         # Risk limit enforcement  
│   │   ├── hedging.py             # Delta hedging logic  
│   │   └── pnl_attribution.py    # P&L breakdown  
│   ├── simulation/  
│   │   ├── __init__.py  
│   │   ├── backtester.py          # Historical simulation    
│   │   ├── market_simulator.py    # Synthetic market data  
│   │   ├── latency_model.py       # Network/processing delays  
│   │   └── execution_model.py     # Realistic execution  
│   ├── analytics/  
│   │   ├── __init__.py  
│   │   ├── performance.py         # Performance metrics  
│   │   ├── attribution.py        # Return attribution  
│   │   ├── visualization.py       # Plotting utilities  
│   │   └── dashboard.py           # Real-time monitoring  
│   ├── data/  
│   │   ├── __init__.py  
│   │   ├── market_data_loader.py  # Data ingestion  
│   │   ├── synthetic_data.py      # Synthetic market generation  
│   │   └── data_utils.py          # Data processing utilities  
│   └── utils/  
│       ├── __init__.py  
│       ├── config.py              # Configuration management  
│       ├── logging.py             # Logging utilities  
│       └── performance_utils.py   # Performance monitoring  
├── tests/  
│   ├── test_order_book/  
│   ├── test_strategies/  
│   ├── test_risk_management/  
│   └── test_simulation/  
├── notebooks/  
│   ├── 01_order_book_analysis.ipynb  
│   ├── 02_strategy_development.ipynb  
│   ├── 03_backtesting_results.ipynb  
│   └── 04_performance_analysis.ipynb  
├── data/  
│   ├── historical/  
│   ├── synthetic/  
│   └── reference/  
├── config/  
│   ├── trading_params.yaml  
│   ├── risk_limits.yaml  
│   └── simulation_config.yaml  
├── requirements.txt  
├── setup.py  
├── README.md  
└── docker-compose.yml
```
