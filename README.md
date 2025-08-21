[THE KING.py](https://github.com/user-attachments/files/21910872/THE.KING.py)# birinchi_telegram-_bot
telegram bot 
[Upimport asyncio
from aiogram import Bot, Dispatcher, types
from aiogram.types import Message, ReplyKeyboardMarkup, KeyboardButton
from aiogram.filters import Command

TOKEN = ""

bot = Bot(token=TOKEN)
dp = Dispatcher()

# 🔹 Klaviatura tugmalari (menyu)
kb = ReplyKeyboardMarkup(
    keyboard=[
        [KeyboardButton(text="/start"), KeyboardButton(text="/yordam")],
        [KeyboardButton(text="👑 THE KING")]  # Qo‘shimcha tugma ham qo‘shish mumkin
    ],
    resize_keyboard=True
)

# 🔹 /start komandasi
@dp.message(Command("start"))
async def cmd_start(message: Message):
    await message.answer(
        "Salom! 👋 Tugmalardan foydalanib komandalarni tanlang:",
        reply_markup=kb
    )

# 🔹 /yordam komandasi
@dp.message(Command("yordam"))
async def cmd_help(message: Message):
    await message.answer("ℹ️ Bu yordam bo‘limi:\n\n/start - botni ishga tushirish\n/yordam - yordam oynasi")

# 🔹 Oddiy tugma matnini tekshirish
@dp.message()
async def echo(message: Message):
    if message.text == "👑 THE KING":
        await message.answer("Siz maxsus tugmani bosdingiz 👑")
    else:
        await message.answer(message.text)

async def main():
    await dp.start_polling(bot)

if __name__ == "__main__":
    asyncio.run(main())
loading THE KING.py…]()
