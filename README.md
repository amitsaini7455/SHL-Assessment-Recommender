SHL Assessment Recommender
An intelligent system that helps hiring managers discover relevant SHL assessments based on natural language queries or detailed job descriptions.

🔍 Key Features
Semantic Search: Discover matching assessments using advanced NLP techniques.

Gemini AI Integration: Leverages Google’s Gemini AI for context-aware, accurate recommendations.

Streamlit Web Interface: Interactive UI for exploring assessment suggestions with ease.

RESTful API: Access recommendations programmatically using FastAPI.

Evaluation Metrics: Built-in support for MAP@K and Recall@K to assess recommendation performance.

Dynamic Scraper: Automatically retrieves up-to-date assessment data from SHL’s product catalog.

🧠 System Architecture
The system is composed of three main modules:

Scraper
Extracts assessment information directly from SHL’s product catalog.

Recommendation Engine
Matches job roles or descriptions to SHL assessments using semantic similarity and Gemini AI.

Web Interface
Provides an intuitive Streamlit-based UI for end-user interaction.

⚙️ Installation
Prerequisites
Python 3.9+

pip (Python package manager)

Setup Instructions
Clone the repository:

bash
Copy
Edit
git clone https://github.com/yourusername/shl-recommender.git
cd shl-recommender
Create and activate a virtual environment:

bash
Copy
Edit
python -m venv venv

# On Windows
venv\Scripts\activate

# On macOS/Linux
source venv/bin/activate
Install the dependencies:

bash
Copy
Edit
pip install -r requirements.txt
Install Playwright browsers (used by the scraper):

bash
Copy
Edit
playwright install
Configure Gemini API key:

Obtain a key from Google AI Studio.

Create a .env file in the project root:

env
Copy
Edit
GOOGLE_API_KEY=your_api_key_here
API_URL=http://localhost:8000
🚀 Usage Guide
You can run the components independently or as a full pipeline:

Run Individual Modules
bash
Copy
Edit
# Run scraper to fetch latest data
python main.py --scrape

# Launch FastAPI server
python main.py --api

# Start Streamlit web app
python main.py --app

# Run both API and web app simultaneously
python main.py --all

# Evaluate model performance
python main.py --evaluate

# Execute a sample query
python main.py --query "Software Engineer with Java experience"
🌐 Access Points
Web UI: http://localhost:8501

API Docs: http://localhost:8000/docs

📡 API Examples
GET Request
bash
Copy
Edit
curl -X GET \
  'http://localhost:8000/recommendations?query=Software%20Engineer%20with%20Java%20experience&num_recommendations=3' \
  -H 'accept: application/json'
POST Request
bash
Copy
Edit
curl -X POST \
  'http://localhost:8000/recommendations' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -d '{
    "query": "Software Engineer with Java experience",
    "num_recommendations": 3
  }'
📁 Project Structure
scraper.py – Extracts assessment data from SHL

recommender.py – Core logic for recommendation

evaluation.py – Metrics for assessing model performance

api.py – FastAPI backend service

app.py – Streamlit frontend interface

main.py – CLI entry point for managing components

💡 Sample Queries
"Software Engineer with Java and Spring experience"

"Marketing Manager with digital marketing background"

"Data Scientist with machine learning expertise"

"Customer Service Representative for a call center"

"Project Manager for software development team"
