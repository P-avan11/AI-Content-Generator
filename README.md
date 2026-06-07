# AI-Content-Generator
Developed a full-stack Flask web application that hosts an interactive text-generation workspace. By integrating the Gemini 2.5 Flash model via Google’s Generative AI client, the backend intercepts asynchronous JSON prompts from the interface and instantly returns low-latency, AI-generated content.


A full-stack, lightweight web application that allows users to submit text-based prompts through an interactive front-end workspace and receive instant, high-quality, AI-generated responses. 

The application utilizes a secure backend architecture built with **Python** and **Flask**, integrated with Google’s next-generation foundational models via the **Google Generative AI SDK**.

---

## 🚀 Key Features

* **Advanced LLM Ingestion:** Integrates Google's **Gemini 2.5 Flash** model (`gemini-2.5-flash`), built for high-speed, low-latency, and versatile content generation tasks.
* **Asynchronous Client Interface:** Features a non-blocking JSON transmission pipeline (`POST` requests) that allows prompts to be evaluated live without requiring page reloads.
* **Isolated Web Server Routing:** Implements modular backend route controls that separate front-end asset loading from downstream AI generation endpoints.
* **Exception & Outage Resilience:** Includes full server-side validation and structured try-except blocks to capture data discrepancies and avoid backend engine crashes.

---

## 🛠️ Tech Stack & Dependencies

* **Backend Web Framework:** Python, Flask
* **Artificial Intelligence Core:** Google Generative AI Python Client (`google-generativeai`)
* **Foundational Model:** Gemini 2.5 Flash
* **Data Format:** Non-blocking JSON payloads

---

## 📂 Project Architecture

```text
├── app.py                  # Main Flask application, server configuration, and Gemini API logic
├── templates/
│   └── generator.html      # Front-end dashboard user interface layout
└── requirements.txt        # Tracked Python libraries (flask, google-generativeai)
⚙️ Installation & Setup
1. Environment Setup
Clone this repository to your localized machine and navigate to the project root directory:

Bash
git clone [https://github.com/yourusername/ai-content-generator.git](https://github.com/yourusername/ai-content-generator.git)
cd ai-content-generator
2. Install Dependencies
Install all required libraries using pip:

Bash
pip install flask google-generativeai
3. Setup Gemini API Key
Obtain an authorized API access key from Google AI Studio. Replace the key initialization in app.py or export it to your environment variables:

Python
# Configure your API key in app.py
genai.configure(api_key="YOUR_GEMINI_API_KEY")
4. Launch the Application
Start the localized microservice development server:

Bash
python app.py
Open your preferred web browser and navigate to http://127.0.0.1:5000/.

🧠 Core Processing Workflow
Prompt Ingestion: The client types text inside the front-end dashboard, packaging it into a standard JSON payload that maps an asynchronous request to the server.

Server-Side Validation: The Flask backend catches the transmission, extracts the prompt data, and checks that the content isn't empty before proceeding.

Model Generation: The server invokes the model.generate_content() method, transmitting the prompt to the Gemini API cloud layers for computation.

Interface Response: The extracted text result is sent back to the front end as a JSON payload, instantly displaying the generated content in the workspace bubble.
