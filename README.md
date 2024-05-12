# i201787_MLOPs_Assignment-2

Data Extraction
I collected articles from BBC and Dawn using a tool called BeautifulSoup along with requests. Then, I sorted through the links and only kept the ones that were important for our project.

Data Transformation
Next, I cleaned up the articles by removing any messy HTML code, extra spaces, and ensuring that all the text looked neat and consistent.

Data Loading
After cleaning up the articles, I saved them to a JSON file. This makes it easy for us to access and use the data later on.

DVC Setup
First, I installed DVC by running pip install dvc.
Then, I set up DVC in our project by typing dvc init.
I connected DVC to a place where we can store our files, like Google Drive, by typing dvc remote add -d gdrive_remote gdrive://your_folder_id.
Next, I told DVC to keep track of our data file by typing dvc add data/articles.json.
Finally, I sent our data to the place we set up in step 3 by typing dvc push.
Workflow and Challenges
Workflow
Airflow DAG:
I created a special plan using Airflow to manage our data extraction, transformation, and loading.

DVC Integration:
I used DVC to keep track of our data for version control and reproducibility. We set up Google Drive as our remote storage.

Challenges
- Data Access Issues:
Sometimes, I had trouble accessing data from certain websites because their structure was inconsistent. I made sure our plan could handle these problems by implementing error handling and retries.

- Environment Setup:
Getting Airflow to work properly on Windows was tricky. I solved this by using WSL2, which makes Windows act like a different type of computer that works better with Airflow.


- Overview
I created a special process to collect, clean, and store data. We used Airflow to manage this process and DVC to keep track of our data.

- Setup Instructions
Step 1. Clone the repository and install dependencies:
bash git clone https://github.com/MuhammadAhsan-DataScientist/i201787_MLOPs_Assignment-2.git
cd i201787_MLOPs_Assignment-2
pip install -r requirements.txt

Step 2. Initializing Airflow:
bash airflow db init

Step 3. Running the web server and scheduler:
bash airflow webserver -p 8080 airflow scheduler

Usage
You can start the process using Airflow's special website. Just click on the name of our plan, mlops_etl_dag, and choose "run" to start the process.



