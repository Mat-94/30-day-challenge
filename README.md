1. Project Initialization
Repository Creation:

Created a new GitHub repository named weather-dashboard-demo.
Cloned the repository locally to set up the project structure.
Project Directory Structure:

plaintext
Copy code
weather-dashboard-demo/
├── src/
│   ├── weather-dashboard.py    # Main Python script
├── .env                        # Environment variables file
├── README.md                   # Project documentation
├── aws/                        # AWS configuration files or utilities
├── requirements.txt            # Dependencies list
└── .gitignore                  # Files to be ignored in version control
2. API and AWS Credential Setup
OpenWeather Account and API Key:

Created an account on the OpenWeather platform.
![Screenshot (245)](https://github.com/user-attachments/assets/7da0de05-53cb-4f2f-b755-525e4f8af308)

Generated an API Key for accessing weather data.
AWS Credentials:

Generated AWS Access Key ID and Secret Access Key using the AWS Management Console.
Configured AWS CLI locally with:
bash
Copy code
aws configure
Environment Variables (.env):

Stored sensitive credentials securely in the .env file:
plaintext
Copy code
OPENWEATHER_API_KEY=your_openweather_api_key
AWS_ACCESS_KEY_ID=your_aws_access_key_id
AWS_SECRET_ACCESS_KEY=your_aws_secret_access_key
AWS_BUCKET_NAME=your_s3_bucket_name
AWS_REGION=your_aws_region
3. Python Environment and Dependencies
Virtual Environment Creation:

bash
Copy code
python3 -m venv venv
source venv/bin/activate
Dependencies Installation:
Installed required Python packages from requirements.txt:

plaintext
Copy code
boto3==<version>
requests==<version>
python-dotenv==<version>
bash
Copy code
pip install -r requirements.txt
4. S3 Bucket Management and Script Execution
S3 Bucket Setup:

The script dynamically checks if the specified AWS S3 bucket exists.
If not, it creates the bucket in the defined AWS region.
Python Script Workflow (weather-dashboard.py):

Fetch Weather Data: Retrieves weather data from OpenWeather API for specified cities.
Bucket Verification/Creation: Ensures the AWS S3 bucket exists.
Data Storage: Uploads the JSON weather data to the S3 bucket with a timestamped filename.
Logs and Error Handling: Ensures meaningful logs and error messages are displayed.
Run the Script:

bash
Copy code
python3 src/weather-dashboard.py
5. Verification and Testing
Local Logs: Ensured weather data is fetched correctly and displayed in the terminal.
AWS S3 Verification: Logged into the AWS Management Console and verified:
Bucket existence.
Uploaded weather JSON files in the weather-data/ folder.
Manual Testing: Tested the script multiple times to validate its functionality.
![Screenshot (242)](https://github.com/user-attachments/assets/82945eb0-09b5-4897-8a81-034421faa414) 
![Screenshot (243)](https://github.com/user-attachments/assets/b52734e0-96c6-4225-92e7-a80a13098756)

![Screenshot (244)](https://github.com/user-attachments/assets/a9b7b75e-41b8-4162-918c-4ffaeb89f608)

6. Documentation and Version Control
Documentation:

Wrote a comprehensive README.md explaining the purpose, setup, and usage of the project.
Included steps for contributors and users to replicate the setup.
Git Workflow:

Added all files to version control:
bash
Copy code
git add .
git commit -m "Initial commit: Weather Dashboard setup and S3 integration"
git push origin main
7. Final Review and Deployment
Ensured all credentials were securely stored in .env and not exposed in public repositories.
Verified data consistency in AWS S3 bucket.
The script is now fully operational, fetching weather data and uploading it securely to AWS S3.
