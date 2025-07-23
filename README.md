# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.\
You will also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: [https://facebook.github.io/create-react-app/docs/code-splitting](https://facebook.github.io/create-react-app/docs/code-splitting)

### Analyzing the Bundle Size

This section has moved here: [https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size](https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size)

### Making a Progressive Web App

This section has moved here: [https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app](https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app)

### Advanced Configuration

This section has moved here: [https://facebook.github.io/create-react-app/docs/advanced-configuration](https://facebook.github.io/create-react-app/docs/advanced-configuration)

### Deployment

This section has moved here: [https://facebook.github.io/create-react-app/docs/deployment](https://facebook.github.io/create-react-app/docs/deployment)

### `npm run build` fails to minify

This section has moved here: [https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify](https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify)


Plant Disease Detection System

An AI-powered system that detects plant diseases from leaf images using a deep learning model. It includes a web interface (React), mobile app (React Native), and backend powered by FastAPI and TensorFlow Serving.

---


## 📁 Project Structure

plant-disease-detection/
├── training/ # Jupyter Notebooks for model training and conversion
├── api/ # FastAPI backend with TensorFlow Serving
├── frontend/ # ReactJS frontend
├── mobile-app/ # React Native mobile app
└── models/ # Exported model versions

yaml
Copy
Edit

---

## ⚙️ Setup Instructions

### 🔧 Python Backend Setup

1. **Install Python**  
   → [Python Setup Instructions](https://www.python.org/downloads/)

2. **Install Dependencies**  
   ```bash
   pip3 install -r training/requirements.txt
   pip3 install -r api/requirements.txt
Install TensorFlow Serving
→ TF Serving Setup Guide

💻 Frontend (ReactJS) Setup
Install Node.js & NPM
→ Node.js Setup

Install Dependencies

bash
Copy
Edit
cd frontend
npm install --from-lock-json
npm audit fix
Setup Environment Variables

Copy .env.example to .env

Update REACT_APP_API_URL in .env

Run Frontend

bash
Copy
Edit
npm run start
📱 React Native Mobile App Setup
Set up React Native CLI Environment
→ React Native Setup Guide

Install Dependencies

bash
Copy
Edit
cd mobile-app
yarn install
For macOS Users

bash
Copy
Edit
cd ios && pod install && cd ../
Setup Environment

Copy .env.example to .env

Set API URL

Run Mobile App

bash
Copy
Edit
npm run android
# or
npm run ios
🧠 Model Training (Jupyter Notebook)
Download PlantVillage Dataset from Kaggle
Only keep folders related to potatoes.

Run Notebook

bash
Copy
Edit
jupyter notebook
Open and Modify

Navigate to training/potato-disease-training.ipynb

Update the dataset path in cell #2

Run all cells to train and save the model

Save the Model

Export trained model to /models with appropriate version number

🧪 Running the API
Option 1: FastAPI Only
bash
Copy
Edit
cd api
uvicorn main:app --reload --host 0.0.0.0
Your API will be available at: http://0.0.0.0:8000

Option 2: FastAPI with TensorFlow Serving
Create Model Config

bash
Copy
Edit
cd api
cp models.config.example models.config
# Edit paths as needed
Run TF Serving via Docker

bash
Copy
Edit
docker run -t --rm -p 8501:8501 \
  -v C:/Code/potato-disease-classification:/potato-disease-classification \
  tensorflow/serving \
  --rest_api_port=8501 \
  --model_config_file=/potato-disease-classification/models.config
Run FastAPI

bash
Copy
Edit
uvicorn main-tf-serving:app --reload --host 0.0.0.0
🤖 TF Lite Conversion (For Mobile)
Run Notebook

bash
Copy
Edit
jupyter notebook
Open and Modify

Navigate to training/tf-lite-converter.ipynb

Update dataset path in cell #2


Run all cells

Model will be saved in tf-lite-models/

<img width="1920" height="1020" alt="Screenshot 2025-07-23 111354" src="https://github.com/user-attachments/assets/b3d23bce-eb6c-49a3-814d-c05c4049b934" />
![Uploading Screenshot 2025-07-23 111354.png…]()
<img width="1920" height="1020" alt="Screenshot 2025-07-23 112530" src="https://github.com/user-attachments/assets/ca747df1-e78d-4f35-8d6e-a3fa396fdfab" />
