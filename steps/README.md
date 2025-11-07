# Steps
1. AWS Console & Region

- Sign in to the AWS Management Console.
- Select the nearest region (e.g., Asia Pacific — Mumbai (ap-south-1)).
<img width="1885" height="877" alt="1" src="https://github.com/user-attachments/assets/775e3a0e-99e3-421f-94a9-4c49ad89583a" />

2. Create an S3 Bucket

- Go to S3 → Create bucket.
- Enter a unique bucket name (e.g., yourname-lab5-sagemaker).
- Leave default settings and click Create bucket.
<img width="1887" height="827" alt="2" src="https://github.com/user-attachments/assets/a54ed7c6-1916-4c75-bdbe-56c60e4c98f0" />

3. Upload Dataset to S3

- Open your bucket → Create folder → name it iris.
- Upload the provided iris.csv dataset.
<img width="1880" height="861" alt="4" src="https://github.com/user-attachments/assets/7ea6c7ba-7adc-4df8-8d41-baf0040caadd" />

4. Launch a SageMaker Notebook Instance

- Go to Amazon SageMaker → Notebook instances → Create notebook instance.
- Name: lab5-hpo-notebook
- Instance type: ml.t3.medium
- IAM role: Create new role with S3 access.
- Click Create notebook instance.
<img width="1893" height="875" alt="5" src="https://github.com/user-attachments/assets/3c5975a0-7de4-44d0-b162-cd128debed72" />
<img width="1888" height="868" alt="6" src="https://github.com/user-attachments/assets/fd293f2c-d179-4dfe-9221-2533ede14219" />
<img width="1894" height="857" alt="7" src="https://github.com/user-attachments/assets/829bb60e-e831-4bbd-9749-21125025db9c" />


5. Open the Notebook

- Once status is InService, click Open JupyterLab (or Open Jupyter).
<img width="1913" height="927" alt="8" src="https://github.com/user-attachments/assets/2734e8d2-a6c2-44fa-aeea-4f9517afa91f" />

6. Prepare Baseline Training Job

- Use the provided sample notebook to train a baseline model on the Iris dataset using XGBoost or similar algorithm.
Screenshot 6: SageMaker → Training Jobs page showing baseline job “Completed”.

7. View Baseline Training Results

- Click the baseline job name → view training metrics like accuracy.
Screenshot 7: Training job details page showing accuracy chart.

8. Create Hyperparameter Tuning Job

- Go to SageMaker → Hyperparameter tuning jobs → Create job.
- Name: iris-hpo-job
- Choose same algorithm (e.g., XGBoost).
- Define hyperparameter ranges and select validation accuracy as metric to optimize.
- Configure job limits (e.g., Max training jobs = 20, Max parallel = 3).
- Click Create tuning job.
<img width="1052" height="350" alt="image" src="https://github.com/user-attachments/assets/750b1bd9-4e84-486c-9562-a77ba4cbe82e" />


9. Monitor and Analyze Results

- Click the tuning job → view each trial’s hyperparameters and validation accuracy.
- Note the Best training job and metrics.


10. View Best Model

- Click the best training job name → check Output section for S3 path of model artifacts.


11. Deploy the Best Model

- Go to SageMaker → Models → Create model.
- Choose the best model artifacts and configure endpoint.
- Deploy model.


12. Record Results

- Create a comparison table of Baseline vs Tuned model accuracy and metrics.


13. Cleanup

- Delete endpoints, configurations, and models.



