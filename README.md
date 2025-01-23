# **Telegram E commerce data processing**

## **Overview**
This project focuses on developing a Named Entity Recognition (NER) system tailored for Amharic text, specifically for e-commerce data extracted from Telegram channels. The system aims to identify entities such as product names, prices, and locations in messages and documents shared across various Ethiopian-based e-commerce Telegram channels.

The pipeline leverages multilingual pre-trained models like **XLM-Roberta**, fine-tuned for Amharic-specific NER tasks, and integrates data preprocessing, labeling, and model training processes.

---

## **Features**
- Real-time data extraction from Telegram e-commerce channels.
- Support for Amharic tokenization and text preprocessing.
- Semi-automated and manual labeling in **BIO format** for NER tasks.
- Fine-tuning of multilingual models for Amharic-specific entity extraction.
- Model evaluation using metrics like **F1-score**, **precision**, and **recall**.

---

## **Project Workflow**
1. **Data Collection**:
   - Scrape text, images, and metadata from multiple Telegram channels using the Telethon library.
   - Consolidate data into CSV and structured formats.

2. **Data Preprocessing**:
   - Tokenize Amharic text.
   - Normalize text by handling diacritics, removing special characters, and splitting messages into tokens.

3. **Data Labeling**:
   - Convert text into CoNLL format for NER labeling.
   - Use pre-trained models for initial labeling and refine manually using tools like Label Studio or Doccano.

4. **Model Fine-Tuning**:
   - Fine-tune models like **XLM-Roberta** or **AfriBERTa** on the labeled dataset.
   - Use the Hugging Face `transformers` library for model training.

5. **Model Evaluation and Comparison**:
   - Compare models using metrics such as **precision**, **recall**, and **F1-score**.
   - Interpret model outputs using tools like **SHAP** or **LIME** for transparency.

6. **Deployment**:
   - Package the NER system for use in consolidating e-commerce data into a centralized database.

---

## **Setup Instructions**

### **1. Environment Setup**
1. Clone the repository:
   ```bash
   git clone https://github.com/SaraFedlu/Telegram-E-commerce-data-processing.git
   cd Telegram-E-commerce-data-processing
   ```

2. Create a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate   # On Windows: venv\Scripts\activate
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

### **2. Credentials for Telegram API**
1. Obtain Telegram API credentials from [my.telegram.org](https://my.telegram.org/).
2. Create a `.env` file in the project root:
   ```
   TG_API_ID=<your_api_id>
   TG_API_HASH=<your_api_hash>
   phone=<your_phone_number>
   ```

### **3. Run the Data Scraper**
- Execute the Telegram scraper to fetch messages:
   ```bash
   python telegram_scraper.py
   ```

---

## **Requirements**
- Python 3.8 or higher
- Libraries:
  - `telethon`
  - `transformers`
  - `pandas`
  - `scikit-learn`
  - `torch`
  - `dotenv`

Install dependencies using the provided `requirements.txt`.

---

## **File Structure**
```
Amharic-NER/
├── data/
│   ├── raw/                   # Raw data from Telegram scraping
│   ├── preprocessed/          # Preprocessed text data
│   ├── labeled/               # Labeled CoNLL-format files
├── models/
│   ├── fine-tuned/            # Fine-tuned NER models
├── scripts/
│   ├── telegram_scraper.py    # Script to scrape Telegram channels
├── requirements.txt           # Python dependencies
├── .env                       # Telegram API credentials (not included in repo)
```

---

## **Contributor**
- **Sara Fedlu** – [GitHub](https://github.com/SaraFedlu)

---

## **License**
This project is licensed under the MIT License. See the `LICENSE` file for details.
