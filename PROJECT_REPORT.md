# Mini Project Report: Chat Bot Creation Using Google Gemini

## 1. Title
**Chat Bot Creation Using Google Gemini**

## 2. Aim
To develop a simple conversational Generative AI chatbot using Google's Gemini API, Python, and Streamlit.

## 3. Problem statement
Users often need quick explanations of learning topics. This project demonstrates how a Large Language Model (LLM) can receive a prompt and generate a natural-language response through a simple chat interface.

## 4. Objectives
- Connect a Python application to the Gemini API.
- Create an interactive chat UI.
- Send user prompts and conversation history to the model.
- Display generated responses.
- Handle common API errors and protect credentials.

## 5. Tools and technologies
| Tool | Purpose |
|---|---|
| Python | Main programming language |
| Google Gemini API | Generates responses |
| Google Gen AI SDK | API integration |
| Streamlit | Chat user interface |
| python-dotenv | Loads API key from `.env` |
| GitHub | Stores and shares project code |

## 6. Methodology
1. Obtain a Gemini API key from Google AI Studio.
2. Create a Python virtual environment.
3. Install dependencies from `requirements.txt`.
4. Store the key in a local `.env` file.
5. Build the Streamlit chat interface.
6. Send the conversation to Gemini using the Google Gen AI SDK.
7. Display the model's response and test different prompts.
8. Upload project files to GitHub without exposing the API key.

## 7. Working principle
The user submits a prompt through Streamlit. The application combines the current prompt with prior messages from the session, then sends them to Gemini. Gemini generates a response, which is displayed in the interface and stored for context in later turns.

## 8. Expected output
A local web application where a user can:
- Ask questions in a chat box.
- Receive AI-generated answers.
- Ask follow-up questions.
- Clear the conversation.
- See a helpful message when configuration or API errors occur.

## 9. Testing plan
| No. | Test input/action | Expected result |
|---:|---|---|
| 1 | Ask “What is Generative AI?” | A relevant explanation appears |
| 2 | Ask “Give one example” afterward | A contextual follow-up appears |
| 3 | Click “Clear conversation” | Previous chat is cleared |
| 4 | Remove API key and restart | Missing-key warning appears |
| 5 | Use an unavailable model | Error message suggests checking model access |

Record the actual result after running each test. Do not claim a test passed until you have run it.

## 10. Limitations
- The chatbot depends on internet connectivity and Gemini API access.
- Usage limits may apply.
- Model responses can contain errors.
- It does not train a new AI model; it uses a pre-trained Gemini model through an API.
- The starter version does not store chats permanently.

## 11. Conclusion
This mini project demonstrates the end-to-end workflow of building an API-powered Generative AI chatbot: environment setup, secure configuration, UI creation, model integration, response generation, testing, and GitHub submission.

## 12. Possible improvements
Add document-based question answering, persistent chat history, speech features, user feedback, and secure cloud deployment.
