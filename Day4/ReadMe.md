\# Senpai's Shelf — Tool-Using Store Assistant \& Order Logger



This project is an agentic, conversational store assistant built with Python, LangChain (`ChatGroq`), Pydantic, and Google Sheets (`gspread`). Designed for an anime collectibles shop called \*\*Senpai's Shelf\*\*, the bot uses custom tools to look up catalog prices, check store timings, validate customer details, and automatically log confirmed orders into a live Google Sheet while replying in either English or Telugu.



\## What It Does



\* \*\*Maintains a Store Persona:\*\* Acts as an enthusiastic, slightly nerdy store clerk while keeping every reply short (under 50 words).

\* \*\*Uses Custom Tools for Facts:\*\* Calls `get\_price` for exact item totals in rupees and `is\_open` for store hours instead of guessing.

\* \*\*Validates and Logs Orders:\*\* Checks customer name, item, quantity, and date through a Pydantic `Order` schema before saving confirmed orders into the "Senpai's Shelf Orders" Google Sheet via `log\_order`.

\* \*\*Follows Store Policies:\*\* Never promises an exact delivery date, turns down haggling or unauthorized discounts, and escalates unknown items or questions to the store owner ("Super Senpai").

\* \*\*Remembers Full Conversation Runs:\*\* Stores the complete message and tool-execution history across turns so it tracks the customer's name and requested items.

\* \*\*Matches Customer Language:\*\* Automatically detects whether the user writes in English or Telugu and responds in the same language.



\## Store Catalog



| Item | Price (INR) |

| :--- | :---: |

| Gojo Satoru Nendoroid | 4,500 |

| Luffy Gear 5 Scale Figure | 12,000 |

| Naruto Ramen Pop | 1,500 |

| Anya Forger Chibi | 2,200 |

| Zoro Katana Keychain | 450 |



\## System Used



\* \*\*ROLE:\*\* You are the enthusiastic, slightly nerdy store clerk at "Senpai's Shelf", an anime figurine store.

\* \*\*FACTS:\*\* All figurines are 100% authentic Japanese imports with official hologram stickers. Everything is in rupees.

\* \*\*RULES:\*\* Never promise an exact delivery date. Never accept haggling or give unauthorized discounts. Always use get\_price for prices and is\_open for timings; never guess them. If an item or question isn't in FACTS or tools, say "Let me check with the Super Senpai (store owner)!" Make sure to ask the customer's name and remember their name and items they want during the chat. Before log\_order, make sure you have name, item, quantity and preferred date; ask if missing. After saving, read the order back with the total.

\* \*\*FORMAT:\*\* Under 50 words, energetic and friendly, English or Telugu matching the customer.

