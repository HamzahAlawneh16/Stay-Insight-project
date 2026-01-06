#  Stay-Insight: Customer Churn Prediction & Retention Platform

**Author:** Hamza Alawneh  
**Role:** AI Engineer / Data Scientist  
**Location:** Jordan  

---

##  Project Overview
**Stay-Insight** is a comprehensive, end-to-end platform designed to help businesses predict customer churn using advanced Machine Learning techniques. By leveraging data-driven insights, the platform empowers organizations to enhance customer retention strategies, minimize revenue loss, and foster sustainable business growth.

The solution features a modern decoupled architecture with a **Streamlit** interactive frontend and a high-performance **FastAPI** backend.

---

##  Project Visuals
The platform offers an intuitive user interface and visuals that communicate the product's vision:
* **Home / Landing Page:** Showcases our philosophy, the core problem, and our future vision.
* **Workflow:** Visualizing the AI-powered service and how it operates.
* **Strategic Solutions:** Detailed insights into Profit, Cost analysis, and AI forecasts.
* **Success Stories & Pricing:** Showcasing client results and available subscription plans.
* **Streamlit Dashboard:** A localized (Arabic/English support) interactive interface for real-time predictions.

---

##  The Problem & The Solution
In today's hyper-competitive market, customer retention is paramount. Acquiring a new customer is significantly more expensive than retaining an existing one.  
**Stay-Insight** identifies "at-risk" customers **before** they leave, allowing businesses to launch proactive retention campaigns and increase **Customer Lifetime Value (LTV)**.

---

##  Key Features
* **Churn Prediction:** Real-time probability estimation based on demographics and service usage.
* **Interactive Web UI:** A seamless graphical interface built with **Streamlit** for data input and visualization.
* **Robust Backend API:** A scalable **FastAPI** backend designed for high-concurrency prediction requests.
* **Machine Learning Core:** Powered by a pre-trained **LightGBM** model for high-accuracy classification.
* **Preprocessing Pipeline:** Integrated **ColumnTransformer** ensuring consistent data scaling and encoding.
* **Actionable Insights:** Provides immediate business recommendations for high-risk profiles.
* **Decoupled Architecture:** Separate frontend and backend for independent scaling and deployment.

---

##  Technologies Used
| Technology | Application |
| :--- | :--- |
| **Python 3.x** | Core logic and development |
| **Streamlit** | Interactive Frontend development |
| **FastAPI** | High-performance Backend API |
| **LightGBM** | Gradient Boosting Framework for ML |
| **Pandas & Numpy** | Data manipulation and numerical operations |
| **Scikit-learn** | Preprocessing (StandardScaler, OneHotEncoder) |
| **Imbalanced-learn** | Handling class imbalance using **SMOTE** |
| **Joblib** | Model serialization and deployment |

---

##  Project Structure
```text
Stay-Insight-project/
├── api_main.py                 # FastAPI Backend logic
├── streamlit_app.py            # Streamlit Frontend application
├── train_and_save_model.py     # ML Pipeline & training script
├── requirements.txt            # Project dependencies
├── final_churn_predictor.pkl   # Serialized LightGBM model
└── data_preprocessor.pkl       # Serialized Preprocessing pipeline

##  Setup & Local Development

To set up the project on your local machine, follow these steps:

1.  **Clone the Repository:**
    
    Bash
    
    ```plaintext
    git clone https://github.com/HamzahAlawneh16/Stay-Insight-project.git
    cd Stay-Insight-project
    ```
    
2.  **Create a Virtual Environment:**
    
    Bash
    
    ```plaintext
    # Create environment
    python -m venv venv
    
    # Activate on Windows:
    .\venv\Scripts\activate
    # Activate on macOS/Linux:
    source venv/bin/activate
    ```
    
3.  **Install Dependencies:**
    
    Bash
    
    ```plaintext
    pip install -r requirements.txt
    ```
    
4.  **Run the Backend (FastAPI):**
    
    Bash
    
    ```plaintext
    uvicorn api_main:app --reload
    ```
    
5.  **Run the Frontend (Streamlit):**
    
    Bash
    
    ```plaintext
    streamlit run streamlit_app.py
    ```
    

---

##  Deployment

The platform is engineered for seamless cloud deployment using a decoupled service model:

*   **Backend API:** Hosted on **Render** (Web Service).
*   **Frontend UI:** Hosted on **Streamlit Community Cloud**.

> ** Crucial Configuration:** After your Backend is live, you must update the `api_url` variable in `streamlit_app.py` to point to your Render public URL. This ensures the frontend can communicate with the Machine Learning model.

---

##  Future Enhancements

*   **Model Explainability (XAI):** Integrating **SHAP** or **LIME** to provide "Reasoning" for each prediction, allowing users to see which features (e.g., contract type, tenure) influenced the churn risk.
*   **Enterprise Security:** Implementing **OAuth2 / JWT** user authentication for secure access management.
*   **Batch Inference Engine:** Adding functionality to upload bulk CSV files for processing thousands of customer records simultaneously.
*   **Advanced Analytics Dashboard:** Developing a comprehensive visual suite for historical churn trends, revenue impact analysis, and segment heatmaps.

---

##  Contributing

Contributions are the backbone of the open-source community. If you would like to improve this project:

1.  **Fork** the Project.
2.  Create your **Feature Branch** (`git checkout -b feature/AmazingFeature`).
3.  **Commit** your Changes (`git commit -m 'Add some AmazingFeature'`).
4.  **Push** to the Branch (`git push origin feature/AmazingFeature`).
5.  Open a **Pull Request**.

---

##  Contact & Support

**Hamza Alawneh** _AI Engineer & Data Scientist_

*   **Email:** [hamzamdhatalawneh@gmail.com](mailto:hamzamdhatalawneh@gmail.com)
*   **LinkedIn:** [Hamza Alawneh Profile](https://www.linkedin.com/in/hamza-medhat-alawneh-ab622a247/)
*   **GitHub:** [HamzahAlawneh16](https://github.com/HamzahAlawneh16)

