# Gemini Study Chatbot — Mini Generative AI Project

A beginner-friendly conversational chatbot built with **Google Gemini**, **Python**, and **Streamlit**. It accepts a user's question, sends the conversation to the Gemini model, and displays the answer in a chat interface.

## 1. Project objective

Build and run a simple Generative AI chatbot that:
- Accepts questions through a chat interface.
- Uses Google's Gemini model to generate responses.
- Keeps earlier messages in the current session for follow-up questions.
- Uses a system instruction to encourage simple, helpful explanations.
- Handles common configuration/API errors.
- Keeps the API key outside the source code using an environment variable.

## 2. Technology stack

- **Python** — application logic
- **Google Gemini API** — large language model (LLM)
- **Google Gen AI SDK (`google-genai`)** — Python SDK to call Gemini
- **Streamlit** — web-based chat UI
- **python-dotenv** — loads the local `.env` configuration file
- **Git/GitHub** — version control and project submission

## 3. Project structure

```text
Gemini_Chatbot_Mini_Project/
├── app.py              # Main chatbot application
├── requirements.txt    # Python dependencies
├── .env.example        # Safe template for the API key
├── .gitignore          # Prevents secrets and temporary files from being committed
├── README.md           # Setup and usage guide
└── PROJECT_REPORT.md   # Mini-project report for mentor submission
```

## 4. Before you start

Install:
1. Python 3.10 or newer.
2. Git (optional, for uploading through the command line).
3. A Google account and access to Google AI Studio.

### Get a Gemini API key
1. Open [Google AI Studio](https://aistudio.google.com/).
2. Sign in and open the API key section.
3. Create or select a Gemini API key, following Google's current instructions.
4. Copy the key and keep it private. API access, model availability, and usage limits depend on Google's current terms and your account.

**Security:** Do not paste your API key into `app.py`, commit it to GitHub, or share it in screenshots. The `.env` file is ignored by Git.

## 5. Set up the project

Open a terminal in this project folder.

### Windows PowerShell

```powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
pip install -r requirements.txt
Copy-Item .env.example .env
```

If PowerShell blocks activation, you can run the environment's Python directly:
```powershell
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
```

### macOS / Linux

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
pip install -r requirements.txt
cp .env.example .env
```

## 6. Configure the API key

Open `.env` in a text editor and replace the placeholder:

```text
GEMINI_API_KEY=your_actual_api_key
```

Save the file. Do not add quotes unless required by your local environment. Do not upload `.env`.

## 7. Run the chatbot

From the project folder, run:

```bash
streamlit run app.py
```

Streamlit should open a local browser tab. If it does not, copy the local URL printed in the terminal (usually `http://localhost:8501`) into your browser.

Choose a model in the sidebar, type a question in the chat box, and press Enter. Ask a follow-up question to test conversation context. Use **Clear conversation** to start over.

## 8. Test cases

| Test | Example input | Expected result |
|---|---|---|
| Basic question | What is machine learning? | Gemini gives a plain-language explanation |
| Follow-up | Give me one real-world example | Response uses the recent conversation context |
| Step-by-step request | Explain how to create a GitHub repository | Answer uses clear steps |
| Empty or unclear prompt | Ask a very vague question | Gemini may ask for clarification or give a cautious answer |
| Missing API key | Remove/rename `.env` and restart | App displays a configuration message |
| API/network issue | Temporarily disconnect internet or use an invalid key | App displays a helpful error message |

## 9. How it works

1. Streamlit displays the chat interface.
2. The user enters a question.
3. The application stores the message in session state.
4. Previous turns are converted into Gemini message contents.
5. The Google Gen AI SDK sends the conversation and system instruction to Gemini.
6. Gemini generates a response.
7. Streamlit displays and stores the answer for follow-up questions.

## 10. Troubleshooting

- **`GEMINI_API_KEY` not found:** Confirm `.env` is named exactly `.env`, is in the same folder as `app.py`, and contains the key.
- **`ModuleNotFoundError`:** Activate your virtual environment and run `pip install -r requirements.txt`.
- **Authentication/permission error:** Check that the key is correct, enabled, and not revoked. Never share it to debug.
- **Model not found / unavailable:** Select a model currently available to your API key. Model names and access can change.
- **Quota or rate-limit error:** Check usage and limits in Google AI Studio; wait or follow Google's quota guidance.
- **Port already in use:** Run `streamlit run app.py --server.port 8502`.

## 11. Limitations and responsible use

- Answers may be incorrect; verify important information.
- This starter project is intended for learning and demonstration, not medical, legal, financial, or other high-stakes decisions.
- The app sends prompts and conversation content to Google's API for processing. Do not enter confidential, sensitive, or personally identifiable information.
- A public deployment requires appropriate secret management, usage limits, monitoring, and a privacy notice.
- This is an API-powered chatbot, not a model trained from scratch.

## 12. Future enhancements

- Add PDF/document question answering (RAG).
- Add speech input and text-to-speech.
- Save chat history in a database.
- Add user feedback and response ratings.
- Add prompt templates and downloadable chat transcripts.
- Deploy to a hosting platform using secure environment secrets.

## 13. GitHub submission

1. Create a new repository on [GitHub](https://github.com/) named `Gemini-Study-Chatbot`.
2. Add a short description: `Beginner Generative AI chatbot using Google Gemini API, Python and Streamlit`.
3. Keep the repository public if your mentor requires public access.
4. Upload `app.py`, `requirements.txt`, `.env.example`, `.gitignore`, `README.md`, and `PROJECT_REPORT.md`.
5. **Do not upload `.env`, API keys, virtual environments, or personal information.**

### Git commands (optional)

```bash
git init
git add app.py requirements.txt .env.example .gitignore README.md PROJECT_REPORT.md
git commit -m "Build Gemini Study Chatbot mini project"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/Gemini-Study-Chatbot.git
git push -u origin main
```

Replace `YOUR-USERNAME` with your GitHub username. If GitHub says the remote already contains a README, follow the GitHub instructions to sync the repository.

## 14. Submission checklist

- [ ] App runs locally.
- [ ] At least three test prompts work.
- [ ] `.env` contains the API key locally.
- [ ] `.env` is not uploaded.
- [ ] README and project report are included.
- [ ] Repository link is shared with the mentor.
