# Stay-Insight-project

# Stay-Insight: Customer Churn Prediction & Retention Platform

![Project Banner - Placeholder Image if available, otherwise remove](https://via.placeholder.com/1200x400?text=Stay-Insight+Customer+Churn+Prediction)

Welcome to Stay-Insight! This project provides a comprehensive solution for businesses to predict customer churn (مغادرة العملاء) using machine learning. It offers data-driven insights to empower customer retention strategies and improve overall business growth. The platform features a user-friendly frontend built with **Streamlit** and a robust backend API powered by **FastAPI**.

---

## 💡 Overview (نظرة عامة)

In today's competitive market, customer retention is paramount. Losing customers can significantly impact a business's revenue and growth. Stay-Insight is designed to identify customers at risk of churning *before* they leave, allowing businesses to take proactive measures and implement targeted retention campaigns.

**Key Idea:** Predicting churn helps in reducing acquisition costs and increasing customer lifetime value.

---

## ✨ Features (الميزات)

* **Customer Churn Prediction:** Predicts the probability of a customer churning based on their demographic and service usage patterns.
* **Interactive Web Interface:** A user-friendly graphical interface (GUI) developed with Streamlit for easy data input and real-time predictions.
* **Robust Backend API:** A scalable and efficient FastAPI backend to handle prediction requests.
* **Machine Learning Powered:** Utilizes a pre-trained LightGBM model for accurate churn probability estimation.
* **Data Preprocessing Pipeline:** Includes a `ColumnTransformer` to ensure consistent data transformation between training and prediction.
* **Actionable Insights:** Provides immediate recommendations for high-risk customers.
* **Separate Frontend & Backend:** A modular architecture facilitating independent development, deployment, and scalability.

---

## 🛠️ Technologies Used (التقنيات المستخدمة)

This project leverages the following technologies:

* **Python 3.x:** The core programming language.
* **Streamlit:** For building the interactive web application (frontend).
* **FastAPI:** For developing the high-performance backend API.
* **Uvicorn:** An ASGI server for running FastAPI applications.
* **Pandas:** For efficient data manipulation and analysis.
* **Scikit-learn:** For machine learning utilities, including data preprocessing (`StandardScaler`, `OneHotEncoder`, `ColumnTransformer`), model selection, and metrics.
* **LightGBM:** A gradient boosting framework for the machine learning model.
* **Joblib:** For saving and loading Python objects, specifically the trained ML model and preprocessor.
* **Requests:** A Python library for making HTTP requests to the API from the Streamlit app.
* **Numpy:** For numerical operations.
* **Imbalanced-learn:** For handling imbalanced datasets (e.g., using SMOTE during training).
* **KaggleHub:** Used in the training script to easily access the Telco Customer Churn dataset.

---

## 📁 Project Structure (هيكل المشروع)

The repository is organized as follows:


### File Descriptions:

* **`requirements.txt`**:
    * **English:** Specifies all Python libraries required for the project to run. Deployment environments (like Streamlit Cloud and Render) read this file to install necessary dependencies.
    * **العربية:** يحدد جميع مكتبات بايثون التي يحتاجها المشروع للعمل بشكل صحيح. تقوم بيئات النشر (مثل Streamlit Cloud و Render) بقراءة هذا الملف لتثبيت المتطلبات الضرورية.
* **`train_and_save_model.py`**:
    * **English:** This script handles the entire machine learning pipeline: data loading, preprocessing, feature engineering, training the customer churn prediction model (LightGBM), and then saving the trained model (`final_churn_predictor.pkl`) and data preprocessor (`data_preprocessor.pkl`).
    * **العربية:** يتولى هذا السكريبت خط أنابيب تعلم الآلة بالكامل: تحميل البيانات، المعالجة المسبقة، هندسة الميزات، تدريب نموذج التنبؤ بمغادرة العملاء (LightGBM)، ثم حفظ النموذج المُدرب (final_churn_predictor.pkl) ومعالج البيانات المسبق (data_preprocessor.pkl).
    * **❗ Important Note:** You **do NOT run** this file on your deployment server! You run it **once** (or whenever you need to retrain the model) in a **development environment** like Google Colab. After successful execution, you must **manually download** the generated `.pkl` files and then **upload them to your GitHub repository** along with other project files.
* **`api_main.py`**:
    * **English:** This is the core of your backend API. It uses FastAPI to receive prediction requests, preprocesses the input data using the saved preprocessor, then uses the trained model to make a prediction, and returns the churn probability. This API will be deployed on a service like Render.
    * **العربية:** هذا هو الجزء المركزي من واجهة برمجة التطبيقات (API) الخاصة بك. يستخدم إطار عمل FastAPI لاستقبال طلبات التنبؤ، ويقوم بمعالجة البيانات المدخلة باستخدام المعالج المسبق الذي تم حفظه مسبقًا، ثم يستخدم النموذج المُدرب لإجراء التنبؤ، ويعيد النتيجة. سيتم نشر هذا الـ API على خدمة مثل Render.
* **`streamlit_app.py`**:
    * **English:** This is your frontend application, built with the Streamlit library, that users will interact with. It collects input data from users via various UI elements, sends this data to your deployed FastAPI API, and then displays the predictions and relevant insights.
    * **العربية:** هذا هو تطبيق الواجهة الأمامية الذي سيتفاعل معه المستخدمون، وهو مبني باستخدام مكتبة Streamlit. يقوم بجمع بيانات المدخلات من المستخدمين عبر عناصر واجهة المستخدم المختلفة، ويرسل هذه البيانات إلى واجهة برمجة التطبيقات (API) التي تم نشرها، ثم يعرض التنبؤات والرؤى ذات الصلة.
* **`final_churn_predictor.pkl`**:
    * **English:** The serialised (saved) machine learning model, ready to be loaded and used for predictions.
    * **العربية:** نموذج تعلم الآلة المُسلسل (المحفوظ)، جاهز للتحميل والاستخدام للتنبؤات.
* **`data_preprocessor.pkl`**:
    * **English:** The serialised (saved) data preprocessing pipeline (a `ColumnTransformer` object), essential for transforming raw input data into the format expected by the model.
    * **العربية:** خط أنابيب معالجة البيانات المسبقة المُسلسل (كائن `ColumnTransformer`)، وهو ضروري لتحويل بيانات المدخلات الخام إلى التنسيق الذي يتوقعه النموذج.

---

## 🚀 Setup & Local Development (الإعداد والتطوير المحلي)

To run this project on your local machine, follow these steps:

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/YourUsername/Stay-Insight-project.git](https://github.com/YourUsername/Stay-Insight-project.git)
    cd Stay-Insight-project
    ```
    (Replace `YourUsername` with your GitHub username and `Stay-Insight-project` with your actual repository name.)

2.  **Create a virtual environment (recommended):**
    ```bash
    python -m venv venv
    # On Windows:
    .\venv\Scripts\activate
    # On macOS/Linux:
    source venv/bin/activate
    ```

3.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Ensure Model Assets Exist:**
    * Make sure `final_churn_predictor.pkl` and `data_preprocessor.pkl` files are present in the project root directory.
    * **If they are missing:** You need to run the `train_and_save_model.py` script (preferably in a Google Colab or Jupyter Notebook environment) and then download these `.pkl` files manually to your project root.

5.  **Run the FastAPI Backend Locally:**
    * First, temporarily modify `streamlit_app.py` to point to the local API:
        Find `api_url = "https://your-api-name.onrender.com/predict_churn/"` and change it to `api_url = "http://localhost:8000/predict_churn/"`
    * Start the FastAPI server:
        ```bash
        uvicorn api_main:app --reload --host 0.0.0.0 --port 8000
        ```
        The `--reload` flag allows the server to restart automatically on code changes.
        You can test the API at `http://localhost:8000/docs` in your browser.

6.  **Run the Streamlit Frontend Locally:**
    * In a **new terminal window** (keep the FastAPI server running in the first one):
    * Activate your virtual environment (if you closed it).
    * Run the Streamlit app:
        ```bash
        streamlit run streamlit_app.py
        ```
    * This will open the Streamlit application in your web browser.

---

## ☁️ Deployment (النشر)

This project is designed for easy deployment using cloud platforms.

### Prerequisites:

* All project files (including `final_churn_predictor.pkl` and `data_preprocessor.pkl`) must be uploaded to a **Public GitHub Repository**.

### 1. Deploying the FastAPI Backend (API) on Render

Render.com is an excellent platform for deploying web services like FastAPI.

1.  **Create a Render Account:** Sign up or log in to [Render.com](https://render.com/).
2.  **Create a New Web Service:** From your Render Dashboard, click "New" -> "Web Service".
3.  **Connect to GitHub:** Connect your GitHub account and select the repository containing your project.
4.  **Configuration:**
    * **Name:** Choose a unique name for your API (e.g., `stay-insight-churn-api`). This will form part of your public URL.
    * **Region:** Select a region close to your users or Streamlit app for lower latency.
    * **Branch:** `main` (or `master`, depending on your repo).
    * **Root Directory:** Leave empty if your files are in the repository root.
    * **Runtime:** Python 3 (choose the specific version you used, e.g., 3.9, 3.10, 3.11).
    * **Build Command (أمر البناء):**
        ```bash
        pip install -r requirements.txt
        ```
    * **Start Command (أمر البدء):**
        ```bash
        uvicorn api_main:app --host 0.0.0.0 --port $PORT
        ```
    * **Plan Type:** Choose a plan (e.g., "Free" or "Starter" for initial testing).
5.  **Deploy:** Click "Create Web Service". Render will automatically build and deploy your API.
6.  **Note the Public URL:** Once deployed, Render will provide a public URL for your API (e.g., `https://your-api-name.onrender.com`). You will need this for the Streamlit app.

### 2. Deploying the Streamlit Frontend (Web App) on Streamlit Community Cloud

Streamlit Cloud provides a simple way to deploy Streamlit applications.

1.  **Go to Streamlit Cloud:** Visit [share.streamlit.io](https://share.streamlit.io/) and log in with your GitHub account.
2.  **Deploy a New App:** Click "New app" or "Deploy an app".
3.  **Configure Deployment:**
    * **Repository:** Select your GitHub repository (`YourUsername/Stay-Insight-project`).
    * **Branch:** `main` (or `master`).
    * **Main file path:** `streamlit_app.py`
    * **Python version:** Select the version you used (e.g., 3.9, 3.10, 3.11).
    * **Advanced settings (Optional):** You might need this for specific environment variables if your project scales.
4.  **Deploy!** Click the "Deploy!" button. Streamlit Cloud will clone your repo, install dependencies, and launch your app.

### ⚠️ CRUCIAL STEP: Update API URL in Streamlit App (After Backend is Deployed!)

After you have successfully deployed your FastAPI backend on Render and obtained its public URL (e.g., `https://your-api-name.onrender.com`), you **MUST** update your `streamlit_app.py` file:

1.  **Open `streamlit_app.py`** on your local machine.
2.  **Find the line:**
    ```python
    api_url = "http://localhost:8000/predict_churn/" # هذا الرابط لن يعمل في النشر! قم بتغييره!
    ```
3.  **Change it to your Render API's public URL:**
    ```python
    api_url = "[https://your-api-name.onrender.com/predict_churn/](https://your-api-name.onrender.com/predict_churn/)"
    ```
    **(Remember to replace `your-api-name` with your actual Render API URL.)**
4.  **Save the file.**
5.  **Commit and push this change to your GitHub repository.**
    * Using GitHub Web UI: Navigate to `streamlit_app.py` in your repo, click the 'Edit' icon (pencil), paste the updated line, then commit changes.
    * Using Git Command Line:
        ```bash
        git add streamlit_app.py
        git commit -m "Update Streamlit app to use Render API URL"
        git push origin main
        ```
6.  **Automatic Redeployment:** Streamlit Cloud will detect the changes in your GitHub repository and automatically re-deploy your application. Once done, your Streamlit app should now successfully communicate with your deployed FastAPI API.

---

## 📈 How to Use the Deployed Application (كيفية استخدام التطبيق المنشور)

1.  Access the public URL of your Streamlit application (provided by Streamlit Cloud).
2.  Fill in the customer's details using the interactive input forms.
3.  Click the "توقع المغادرة" (Predict Churn) button.
4.  The application will display the predicted churn probability and provide recommendations based on the risk level.

---

## 💡 Future Enhancements (تحسينات مستقبلية)

* **Model Interpretability:** Integrate SHAP or LIME to explain model predictions directly within the Streamlit interface.
* **User Authentication:** Implement secure user login and management.
* **Bulk Predictions:** Allow users to upload a CSV file for predictions on multiple customers.
* **Dashboard & Analytics:** Develop a comprehensive dashboard displaying churn trends, key influencing factors, and customer segments.
* **Automated Retraining Pipeline:** Set up an automated process to retrain the model periodically with new data.
* **Database Integration:** Store customer data and predictions in a database.

---

## 🤝 Contributing (المساهمة)

Contributions are welcome! If you have suggestions for improvements or new features, please feel free to:

1.  Fork the repository.
2.  Create a new branch (`git checkout -b feature/YourFeature`).
3.  Make your changes.
4.  Commit your changes (`git commit -m 'Add new feature'`).
5.  Push to the branch (`git push origin feature/YourFeature`).
6.  Open a Pull Request.

---

## 📄 License (الترخيص)

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details (if you have one, otherwise create a LICENSE file or remove this section).

---

## 📧 Contact (للتواصل)

For any questions or inquiries, please feel free to reach out:

* **Your Name:** hamza alawneh
* **Email:** hamzamdhatalawneh@gmail.com
* **LinkedIn:** [(https://www.linkedin.com/in/hamza-medhat-alawneh-ab622a247/)]
* **GitHub:** [(https://github.com/HamzahAlawneh16)]

---
