# Drinking_Water_Reminder
Drinking Water Reminder
!pip install python-telegram-bot
import asyncio
import random
from telegram import Bot

TOKEN = "8159926153:AAGIYvoRVVKuA2quMXxQMwiIeatKGn7ol3M"
CHAT_ID = "6346624628"

bot = Bot(token=TOKEN)

messages = [
    "Hey ❤️ drink water 💧",
    "Hydration reminder 💧",
    "Time to drink water 💧",
    "Stay healthy ❤️ drink water"
]

stop_bot = False  # Global flag to control bot execution

async def main():
    global stop_bot
    print("Bot Running 24/7")

    while not stop_bot:
        msg = random.choice(messages)
        await bot.send_message(chat_id=CHAT_ID, text=msg)
        print("Reminder sent")
        await asyncio.sleep(1800)   # 30 minutes (Currently 60 seconds)
    print("Bot stopped.")

await main()
