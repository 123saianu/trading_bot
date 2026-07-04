# trading_bot
# Binance Futures Testnet Trading Bot

A simple Python CLI application that places MARKET and LIMIT orders on the Binance USDT-M Futures Testnet.

## Features

- Place MARKET orders
- Place LIMIT orders
- Supports BUY and SELL orders
- Command-line interface using Typer
- Input validation
- Logging of API requests, responses, and errors
- Exception handling for invalid inputs and API errors

## Project Structure

```
trading_bot/
│
├── bot/
│   ├── __init__.py
│   ├── client.py
│   ├── orders.py
│   ├── validators.py
│   └── logging_config.py
│
├── logs/
│   └── trading.log
│
├── cli.py
├── requirements.txt
├── README.md
└── .env
```

## Requirements

- Python 3.10+
- Binance Futures Testnet account
- Binance API Key and Secret

## Installation

### 1. Clone the repository

```bash
git clone <repository-url>
cd trading_bot
```

### 2. Create a virtual environment

Windows:

```bash
python -m venv venv
```

Activate:

PowerShell

```powershell
.\venv\Scripts\Activate.ps1
```

Git Bash

```bash
source venv/Scripts/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

## Environment Variables

Create a `.env` file in the project root.

```text
BINANCE_API_KEY=YOUR_API_KEY
BINANCE_API_SECRET=YOUR_API_SECRET
```

## Usage

### MARKET BUY

```bash
python cli.py --symbol BTCUSDT --side BUY --order-type MARKET --quantity 0.001
```

### MARKET SELL

```bash
python cli.py --symbol BTCUSDT --side SELL --order-type MARKET --quantity 0.001
```

### LIMIT BUY

```bash
python cli.py --symbol BTCUSDT --side BUY --order-type LIMIT --quantity 0.001 --price 100000
```

### LIMIT SELL

```bash
python cli.py --symbol BTCUSDT --side SELL --order-type LIMIT --quantity 0.001 --price 120000
```

## Output

The application displays:

- Order request summary
- Order response
- Order ID
- Order status
- Executed quantity
- Average execution price (if available)
- Success or failure message

## Logging

Logs are stored in:

```
logs/trading.log
```

The log file contains:

- API requests
- API responses
- Errors
- Exceptions

## Error Handling

The application handles:

- Invalid order side
- Invalid order type
- Invalid quantity
- Missing price for LIMIT orders
- Binance API errors
- Network failures

## Assumptions

- The user has a valid Binance Futures Testnet account.
- API credentials are stored in a `.env` file.
- The account has sufficient virtual balance to place orders.
- Internet connectivity is available.

## Technologies Used

- Python 3
- python-binance
- Typer
- python-dotenv
- Logging
