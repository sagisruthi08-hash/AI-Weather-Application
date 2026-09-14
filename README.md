# 🌦️ AI Weather Function Calling Application

An AI-powered weather application built using **Python, Streamlit, Hugging Face LLM, Function Calling, Geocoding API, and Weather API**.

This project demonstrates how a **Large Language Model (LLM)** can understand a user's natural-language weather query, decide when a function needs to be called, execute a Python function, retrieve real-time weather information from an external API, and generate a natural-language response.

---

## 📌 Project Overview

The **AI Weather Function Calling Application** allows users to ask weather-related questions using natural language.

For example:

> **What is the weather in Chennai?**

Instead of requiring the user to enter latitude and longitude, the application automatically:

1. Understands the user's question using an LLM.
2. Identifies that weather information is required.
3. Calls the `get_weather()` Python function.
4. Converts the city name into geographical coordinates.
5. Retrieves current weather information.
6. Sends the weather data back to the LLM.
7. Generates a clear and natural-language response.
8. Displays the result through a Streamlit interface.

---

# 🎯 Objectives

The main objectives of this project are:

* To understand **LLM Function Calling**.
* To integrate an LLM with external APIs.
* To allow users to interact using natural language.
* To automatically identify when a tool/function is required.
* To retrieve real-time weather information.
* To understand the complete workflow:

```text
User → LLM → Function → API → Tool Result → LLM → Response
```

* To build an interactive AI application using Streamlit.
* To demonstrate the practical usage of Function Calling in an AI application.

---

# ✨ Key Features

* 🤖 AI-powered natural-language interaction
* 🌦️ Real-time weather information
* 🔧 LLM Function Calling
* 📍 Automatic city-to-coordinate conversion
* 🌐 Geocoding API integration
* ☁️ Weather API integration
* 💬 Chat-based Streamlit interface
* 📊 Easy-to-understand weather information
* 🔐 Secure Hugging Face token handling using `.env`
* ⚠️ Error handling for invalid cities and API failures
* 🧠 LLM-generated natural-language responses
* 📱 Interactive and user-friendly interface

---

# 🔄 Application Workflow

```text
                ┌─────────────────────┐
                │        USER         │
                │ "Weather in Chennai"│
                └──────────┬──────────┘
                           │
                           ▼
                ┌─────────────────────┐
                │      STREAMLIT      │
                │    Chat Interface   │
                └──────────┬──────────┘
                           │
                           ▼
                ┌─────────────────────┐
                │        LLM          │
                │  Hugging Face Model │
                └──────────┬──────────┘
                           │
                     Function Call
                           │
                           ▼
                ┌─────────────────────┐
                │   get_weather()     │
                │   Python Function   │
                └──────────┬──────────┘
                           │
                           ▼
                ┌─────────────────────┐
                │    Geocoding API    │
                │   City → Latitude   │
                │      Longitude      │
                └──────────┬──────────┘
                           │
                           ▼
                ┌─────────────────────┐
                │     Weather API     │
                │ Open-Meteo Forecast │
                └──────────┬──────────┘
                           │
                     Weather Data
                           │
                           ▼
                ┌─────────────────────┐
                │     Tool Result     │
                └──────────┬──────────┘
                           │
                           ▼
                ┌─────────────────────┐
                │        LLM          │
                │   Final Response     │
                └──────────┬──────────┘
                           │
                           ▼
                ┌─────────────────────┐
                │        USER         │
                │ Natural Language    │
                │  Weather Response   │
                └─────────────────────┘
```

---

# 🧠 What is Function Calling?

**Function Calling** is a capability that allows an LLM to decide when it needs to use an external function or tool.

Normally, an LLM generates responses based on the information available within its context. However, many real-world applications require access to external or up-to-date information.

For example:

* 🌦️ Current weather
* 📈 Stock prices
* 🗄️ Database information
* 🔎 Search results
* 🧮 Calculations
* 🌐 External APIs

Function Calling allows the model to request a specific function with the required parameters.

For example:

```text
User:
"What is the weather in Chennai?"

        ↓

LLM:
I need weather information.

        ↓

Function Call:
get_weather("Chennai")

        ↓

API:
Returns weather data.

        ↓

LLM:
Generates final response.

        ↓

User:
"Chennai is currently ..."
```

---

# 🔧 Function Used

The main Python function used in this project is:

```python
get_weather()
```

The function is responsible for:

1. Receiving the city name.
2. Finding the geographical coordinates.
3. Calling the weather API.
4. Retrieving weather information.
5. Returning the result to the LLM.

---

# 📍 Geocoding API

The **Geocoding API** converts a city name into geographical coordinates.

For example:

```text
Chennai
   ↓
Latitude
Longitude
```

These coordinates are then used by the weather API to retrieve weather information for the requested location.

---

# ☁️ Weather API

This project uses the **Open-Meteo Weather API** to retrieve weather information.

The API can provide information such as:

* 🌡️ Temperature
* 💨 Wind speed
* 🌧️ Weather conditions
* 📍 Location-based forecast information

The retrieved data is passed back to the LLM as a **tool result**.

---

# 🤖 Large Language Model

The application uses a **Hugging Face LLM** to process natural-language requests.

The LLM is responsible for:

* Understanding the user's query
* Identifying the need for weather information
* Deciding when to call the weather function
* Providing the required function arguments
* Interpreting the returned weather data
* Generating a natural-language response

---

# 💻 Streamlit Interface

The application uses **Streamlit** to create an interactive chat interface.

Users can enter questions such as:

```text
What is the weather in Chennai?
```

```text
Tell me the current weather in Hyderabad.
```

```text
How is the weather in Bangalore?
```

The application processes the query and displays the generated response.

---

# 🔐 Environment Variables

The Hugging Face authentication token is stored securely using an environment file.

Example:

```text
.env
```

The token should **not** be directly written inside the source code or uploaded to GitHub.

Example:

```env
HF_TOKEN=your_huggingface_token
```

The `.env` file should be added to `.gitignore`.

---

# 🛠️ Technologies Used

| Technology       | Purpose                         |
| ---------------- | ------------------------------- |
| Python           | Application development         |
| Streamlit        | User interface                  |
| Hugging Face     | LLM integration                 |
| Function Calling | Tool/function execution         |
| Geocoding API    | City-to-coordinate conversion   |
| Open-Meteo API   | Weather information             |
| dotenv           | Environment variable management |

---

# 📂 Project Structure

```text
AI-weather-Application/
│
├── app.py
├── .env
├── .gitignore
├── requirements.txt
├── README.md
└── assets/
    └── weather_app.png
```

---

# 📦 Installation

Clone the repository:

```bash
git clone https://github.com/nishahussain03-afk/AI-weather-Application.git
```

Navigate to the project directory:

```bash
cd AI-weather-Application
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

---

# 🔑 Configure Hugging Face Token

Create a `.env` file in the project directory:

```env
HF_TOKEN=your_huggingface_token
```

Replace the value with your own Hugging Face access token.

⚠️ **Never upload your API token or secret keys to GitHub.**

---

# ▶️ How to Run

Run the Streamlit application using:

```bash
streamlit run app.py
```

The application will open in your browser.

You can then enter a natural-language weather query.

Example:

```text
What is the weather in Chennai?
```

---

# 📊 Example Interaction

### 👤 User

```text
What is the weather in Chennai?
```

### 🤖 LLM

The model identifies that weather information is required and requests the weather function.

### 🔧 Function

```text
get_weather("Chennai")
```

### 🌐 API

The application retrieves the coordinates and current weather information.

### 🤖 Final Response

The LLM converts the API result into a simple natural-language response for the user.

---

# 🔄 Complete Function Calling Process

```text
1. User enters a natural-language query
              ↓
2. Streamlit receives the query
              ↓
3. LLM analyzes the query
              ↓
4. LLM decides to call get_weather()
              ↓
5. City name is sent to the Geocoding API
              ↓
6. Latitude and longitude are obtained
              ↓
7. Coordinates are sent to Weather API
              ↓
8. Weather data is retrieved
              ↓
9. Tool result is returned to the LLM
              ↓
10. LLM generates the final response
              ↓
11. Streamlit displays the response
```

---

# 🎯 Key Learning Outcomes

Through this project, we understand:

* What LLM Function Calling is
* How LLMs interact with external tools
* How APIs can be integrated with AI applications
* How natural-language queries can trigger functions
* How geocoding works
* How real-time weather data can be retrieved
* How tool results are passed back to an LLM
* How Streamlit can be used to build AI applications
* How environment variables can be used for secure API credentials
* How LLMs can be used to build practical real-world applications

---

# 🚀 Future Improvements

The project can be extended with:

* 🌡️ Multi-day weather forecasts
* 📍 Automatic location detection
* 🌧️ Weather alerts
* 📊 Weather charts and graphs
* 🗺️ Interactive maps
* 🌅 Sunrise and sunset information
* 💨 Air quality information
* 🌍 Support for multiple locations
* 🗣️ Voice-based weather queries
* 📱 Improved mobile-responsive interface
* 🤖 Multiple tool/function support

---

# 🌟 Applications

Function Calling can be used in many real-world AI applications, including:

* Weather assistants
* AI travel assistants
* Customer-support agents
* Database assistants
* Financial assistants
* Shopping assistants
* AI productivity tools
* Search assistants
* Smart personal assistants

---

# 📌 Project Status

🟢 **Completed**

This project demonstrates the practical implementation of **LLM Function Calling with external APIs** through an interactive Streamlit weather application.

---

# 👩‍💻 Author

**Sruthi S**



⭐ **If you find this project useful, consider giving the repository a star!**
