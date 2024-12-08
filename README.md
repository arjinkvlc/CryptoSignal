
# **CryptoSignal - Trading Bot**

This project is a **crypto trading bot application** that includes a **frontend** developed with **Kotlin** and a **backend** written in **Python**. The bot retrieves real-time price data using Binance API and makes buy-sell decisions based on predefined strategies. Indicators can also be dynamically updated and customized.

---

## **Project Overview**

- **Frontend**: Built with Kotlin, providing a user-friendly interface to control the bot.
- **Backend**: Developed using Python, Flask, and Socket.IO, supporting real-time trading strategies and indicator calculations.
- **Crypto Trading**: Uses Binance API to fetch live market data and execute trades based on user-defined strategies.

---

## **Features**

- **Dynamic Trading Strategies**  
   Includes indicators such as Bollinger Bands, RSI, CCI, and VWAP. Users can customize these strategies through the frontend.

- **Real-Time Data Processing**  
   Retrieves live crypto prices using Binance API and dynamically calculates indicators.

- **Start and Stop Functionality**  
   The bot can be started, stopped, and restarted with ease.

- **Real-Time Updates**  
   Updates, such as executed trades and balance changes, are sent to the frontend using Socket.IO.

- **Backtesting Support**  
   Run historical simulations using the `run_backtest.py` script to test strategies with past 4 months of data.

- **Date and Time Support**  
   All operations are timestamped in the UTC+3 time zone for accuracy.

---

## **Usage**

### **Setting Up API Keys**

You need to provide your own Binance Mainnet API keys for the application. Update the following fields in the `config.py` file:
```python
BINANCE_API_KEY = "your_api_key_here"
BINANCE_SECRET_KEY = "your_secret_key_here"
```

### **Running the Backend**

1. **Install Required Libraries**  
   Create a Python virtual environment and install the dependencies:
   ```bash
   python -m venv env
   source env/bin/activate  # On Windows: env\Scripts\activate
   pip install -r requirements.txt
   ```

2. **Start the Backend**
   Run the Flask server:
   ```bash
   python app.py
   ```

3. **Run Backtesting**
   To simulate strategies using historical data:
   ```bash
   python run_backtest.py
   ```
   This will execute backtests with the last 4 months of data and output indicator performance.

---

### **Running the Frontend**

1. **Open the Kotlin Project**  
   Use Android Studio or IntelliJ IDEA to open the project.

2. **Configure Backend Connection**  
   Set the backend server's IP and port in the frontend configuration.

3. **Run the Application**  
   Deploy the frontend to an emulator or physical device for testing.

---

## **API Endpoints**

| **Method** | **Endpoint**     | **Description**                                         |
|----------- |------------------|-----------------------------------------------------|
| `POST`     | `/start-bot`     | Starts the bot.                                      |
| `POST`     | `/stop-bot`      | Stops the bot.                                      |
| `GET`      | `/wallet`        | Returns the current wallet balance and coin amounts. |
| `GET`      | `/simulate`      | Runs a backtest with specified parameters.        |
| `GET`      | `/prices`        | Returns the prices of all coins.                      |
| `GET`      | `/coin`          | Returns wallet details for the specified coin.     |
| `GET`      | `/historical`    | Returns historical price data.                     |
| `GET`      | `/get-candlestick` | Returns candlestick chart data.                      |

---

## **Dependencies**

### **Backend**
- Python 3.8 or higher
- Flask
- Flask-SocketIO
- Pandas
- NumPy
- Binance API

### **Frontend**
- Kotlin
- Compose
- Retrofit
- Coroutine

---

## **Planned Features**

- Integration of additional trading strategies
- Viewing historical performance for users
- Profit and loss analysis in the mobile app
- Strategy optimization using Machine Learning
