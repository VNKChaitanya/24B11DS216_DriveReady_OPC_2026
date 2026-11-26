# Senpai's Shelf — Anime Figurine Store Assistant

This project is a simple, conversational store assistant built with Python, LangChain, and Groq. Designed for a fictional anime collectibles shop called **Senpai's Shelf**, the bot answers customer questions using a fixed set of store facts, follows clear behavioral guardrails, and replies in either English or Telugu to match the customer.

## What It Does

* **Maintains a Store Persona:** Acts as an enthusiastic, slightly nerdy store clerk while keeping every reply short (under 50 words).
* **Sticks to Store Facts:** Quotes exact prices in rupees from the catalog and reassures buyers that all figures are authentic Japanese imports with official hologram stickers.
* **Follows Store Policies:** Avoids making promises about exact delivery dates, turns down haggling or unauthorized discounts, and escalates anything outside its catalog to the store owner ("Super Senpai").
* **Matches Customer Language:** Automatically detects whether the user writes in English or Telugu and responds in the same language.
* **Keeps Keys Safe:** Loads the Groq API key via Google Colab Secrets or a local `.env` file rather than hardcoding credentials in the script.

## Store Catalog

| Item | Price (INR) |
| :--- | :---: |
| Gojo Satoru Nendoroid | 4,500 |
| Luffy Gear 5 Scale Figure | 12,000 |
| Naruto Ramen Pop | 1,500 |
| Anya Forger Chibi | 2,200 |
| Zoro Katana Keychain | 450 |

## Requirements

* Python 3.9 or higher
* `langchain-groq`
* `python-dotenv` (optional, for running locally)
* A Groq API key

## Setup and Installation

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/](https://github.com/)<your-username>/<your-repo-name>.git
   cd <your-repo-name>
