Instructions: Running the Student Performance System (Partial Build) Current Status: v0.5 (Interface + Model Integration Testing) Last Updated: March 4, 2026

Verify Directory Structure Before running anything, ensure your folder looks exactly like this so Python can find the files:
Plaintext /Student_Project

├── Backend/
│    └── api.py
│    └── test_api.py
├── Data/
│    └── student-mat.csv
├── Dataset_loading/
│    └── data_loading.ipynb
├── Environment/
│    └── environment setup.ipynb
│    └── requirements.txt
├── Frontend/   
│    └── instance/
│        └── users.db
│    └── static/
│        └── style.css
│    └── templates/
│        └── dashboard.html
│        └── login.html
│        └── regiser.html
│    └── app.py
├── Model/
│    └── model.pkl
│    └── scaler.pkl
├── Model Training/
│    └── Student_tst.ipynb
├── Preprocessing
│    └── preprocessing.ipynb

Environment Setup Open your terminal (Command Prompt or VS Code Terminal) and navigate to the project folder.
Step A: Create a Virtual Environment (Optional but Recommended)

Windows: python -m venv venv then venv\Scripts\activate

Mac/Linux: python3 -m venv venv then source venv/bin/activate

Step B: Install Required Libraries Copy and paste this command to install all necessary tools at once:

Bash pip install flask pandas numpy scikit-learn pip intsall flask_login request flask_sqlalchemy

===================================== STARTUP GUIDE - Student Performance Prediction System
To run the application correctly, you need to start BOTH the Backend API and Frontend in separate terminals.

IMPORTANT: Your model files must be present at:

Model/Model_File/model.pkl
Model/Model_File/scaler.pkl
===================================== STEP 1: Start the Backend API
Open a NEW terminal/PowerShell window
Navigate to the Backend folder: cd Backend
Run the API (it will run on port 5000): python api.py
You should see output like: Model loaded from: ...

Running on http://127.0.0.1:5000
Keep this terminal running!

===================================== STEP 2: Start the Frontend
Open ANOTHER NEW terminal/PowerShell window
Navigate to the Frontend folder: cd Frontend
Run the app (it will run on port 8000): python app.py
You should see output like:

Running on http://127.0.0.1:8000
Keep this terminal running!

===================================== STEP 3: Access the Application
Open your browser and go to: http://localhost:8000

Login with the test account: Username: admin Password: password123

Enter student data and click "Analyze Risk"

The prediction should now appear below the form!

===================================== TROUBLESHOOTING
If results don't show:

Check that BOTH terminals are running (Backend on 5000, Frontend on 8000)
Look at the console output in both terminals for error messages
The Frontend console (where you ran python app.py) will show error details
The Backend console (where you ran python api.py) will show if there's an issue with predictions
If you get "Cannot connect to Backend API":

Make sure Backend API is running (it should say "Running on http://127.0.0.1:5000")
Make sure both are using Python from the same virtual environment
If model files are not found:

Verify model.pkl and scaler.pkl exist in Model/Model_File/
Check that you trained the model using the notebooks in Model Training/
