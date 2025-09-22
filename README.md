# 💰 n8n Crypto Price Tracker

## 📌 Description
This project is an **n8n workflow** that tracks the price of cryptocurrencies (e.g., Bitcoin, Ethereum, or any other coin) using the **CoinGecko API**.  
The workflow can be scheduled (every 5 minutes, hourly, or daily) and will send you updates via **Telegram**, **Slack**, or **Email** if the price changes significantly.

---

## ⚙️ How it works
1. **Cron Node** → Triggers the workflow on a schedule (e.g., every 1 hour).  
2. **HTTP Request Node** → Calls the [CoinGecko API](https://www.coingecko.com/en/api/documentation) to get the latest price of selected cryptocurrencies.  
   - Example endpoint:  
     ```
     https://api.coingecko.com/api/v3/simple/price?ids=bitcoin,ethereum&vs_currencies=usd
     ```
3. **IF Node** → Checks if the price has gone above or below a threshold.  
4. **Telegram / Slack / Email Node** → Sends an alert message with the updated price.  

---

## 🚀 Setup
1. Import the `workflow.json` file into your **n8n instance**.  
2. No API key required (CoinGecko’s free API).  
3. Configure your preferred notification channel:  
   - **Telegram Bot**: set your `BOT_TOKEN` and `CHAT_ID`.  
   - **Slack**: set your Slack Webhook URL.  
   - **Email**: configure SMTP settings.  

---

## 🖼 Example
- If Bitcoin price drops below **40,000 USD**, you get a Telegram alert:  
