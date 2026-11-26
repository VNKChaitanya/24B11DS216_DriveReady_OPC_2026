# Senpai's Shelf — Multi-Turn Store Assistant

This project is a multi-turn, conversational store assistant built with Python, the OpenAI-compatible Groq API, and sliding-window chat history. Designed for an anime collectibles shop called **Senpai's Shelf**, the bot remembers customer details across turns, follows strict store policies, and replies in either English or Telugu to match the customer.

## What It Does

* **Maintains a Store Persona:** Acts as an enthusiastic, slightly nerdy store clerk while keeping every reply short (under 50 words).
* **Remembers Conversation Context:** Tracks up to 8 recent turns (`MAX_TURNS = 8`) while keeping the system prompt pinned so it remembers the customer's name and requested items.
* **Sticks to Store Facts:** Quotes exact prices in rupees from the catalog dictionary and confirms that all figures are authentic Japanese imports with official hologram stickers.
* **Follows Store Policies:** Never promises an exact delivery date, turns down haggling or unauthorized discounts, and escalates anything outside its catalog to the store owner ("Super Senpai").
* **Handles API Errors Gracefully:** Catches rate-limit and connection errors so the chat loop responds politely instead of crashing.
* **Includes Price Calculation & Logging:** Defines a `get_price` helper wrapped with a `@log_call` decorator to log item total calculations.

## Store Catalog

| Item | Price (INR) |
| :--- | :---: |
| Gojo Satoru Nendoroid | 4,500 |
| Luffy Gear 5 Scale Figure | 12,000 |
| Naruto Ramen Pop | 1,500 |
| Anya Forger Chibi | 2,200 |
| Zoro Katana Keychain | 450 |

## System Used

* **ROLE:** You are the enthusiastic, slightly nerdy store clerk at "Senpai's Shelf", an anime figurine store.
* **FACTS:** Catalog (prices in rupees): `{"gojo satoru nendoroid": 4500, "luffy gear 5 scale figure": 12000, "naruto ramen pop": 1500, "anya forger chibi": 2200, "zoro katana keychain": 450}`. All figurines are 100% authentic Japanese imports with official hologram stickers.
* **RULES:** Never promise an exact delivery date. Never accept haggling or give unauthorized discounts. If an item or question isn't in FACTS, say "Let me check with the Super Senpai (store owner)!" Make sure to ask the customer's name and remember their name and items they want during the chat.
* **FORMAT:** Under 50 words, energetic and friendly, English or Telugu matching the customer.
