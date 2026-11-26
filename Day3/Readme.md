# Sweet Crumbs Home Bakery — LangChain Assistant with Memory & Tests

This project is a conversational bakery assistant built with Python, LangChain (`ChatGroq`), and Google Colab[cite: 8]. Designed for **Sweet Crumbs Home Bakery**, the bot uses a LangChain Expression Language (LCEL) chain with conversation history to answer customer questions, includes an automated CSV-based test suite, and demonstrates how to wrap the same assistant into a LangChain agent[cite: 8].

## What It Does

* **Builds a LangChain LCEL Chain:** Connects `ChatPromptTemplate`, `ChatGroq` (`openai/gpt-oss-20b`), and `StrOutputParser` into a clean pipeline.
* **Remembers Conversation History:** Uses `MessagesPlaceholder("history")` and a Python list to track previous human and AI messages across turns.
* **Sticks to Bakery Facts:** Quotes exact prices in rupees and confirms store policies such as the 24-hour advance notice requirement and eggless cake availability.
* **Follows Store Policies:** Avoids promising exact delivery times or places, escalates unknown queries to the owner, and replies in English or Telugu to match the customer.
* **Runs Automated Evaluation Tests:** Reads test cases from `tests.csv` (`question` and `must_include` columns) and reports pass/fail accuracy across all prompts.
* **Demonstrates Agent Setup:** Includes a preview of initializing the exact same system prompt using LangChain's `create_agent`.[cite: 8]

## Bakery Catalog

| Item | Price (INR) |
| :--- | :---: |
| Plum Cake | 500 |
| Chocolate Cake | 650 |
| Cupcake | 80 each[cite: 8] |

## System Used

* **ROLE:** You are the friendly assistant for Sweet Crumbs Home Bakery.
* **FACTS:** Plum cake Rs 500. Chocolate cake Rs 650. Cupcake Rs 80 each. Orders need 24 hours' notice. All cakes have eggless versions.
* **RULES:** Never promise a delivery time or place. If it isn't in FACTS, say "I'll check with the owner." Work out totals carefully.
* **FORMAT:** Under 50 words, friendly, English or Telugu matching the customer.[cite: 8]
