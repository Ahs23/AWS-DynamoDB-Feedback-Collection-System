# AWS DynamoDB Feedback Collection System

A complete end-to-end AWS project that demonstrates how to collect user feedback through a web interface hosted on an EC2 instance and store the data securely in Amazon DynamoDB using a Python CGI backend.

---

## 🚀 Project Overview

This project implements a simple feedback collection system using core AWS services.  
Users submit feedback via a web form hosted on an EC2 instance. The backend Python CGI script processes the form data and stores it in a DynamoDB table in real time.

The project showcases practical usage of:
- EC2 as a web server
- Apache with CGI enabled
- Python (boto3) for AWS integration
- IAM Roles for secure access
- DynamoDB for serverless data storage

---

## 🛠️ Tech Stack Used

- **Frontend:** HTML
- **Backend:** Python (CGI)
- **Web Server:** Apache
- **AWS Services:**
  - Amazon EC2
  - Amazon DynamoDB
  - AWS IAM
- **SDK:** boto3
- **OS:** Amazon Linux

---

## 🏗️ Architecture Flow

1. User accesses the feedback form hosted on EC2.
2. User submits name, course, and feedback.
3. Data is sent to a Python CGI script.
4. The script uses boto3 to insert data into DynamoDB.
5. User receives a success confirmation message.
6. Data appears instantly in the DynamoDB table.

---

## 📂 Project Structure

```text
/var/www/html/
 └── index.html

/usr/lib/cgi-bin/
 └── feedback.py
🗄️ DynamoDB Table Details
Property	Value
Table Name	CloudWithArmanFeedback
Partition Key	id (String)
Data Stored	id, name, course, feedback

🔐 IAM Configuration
IAM Role attached directly to EC2

Policy attached: AmazonDynamoDBFullAccess

No hardcoded AWS credentials used (best practice)

⚙️ Setup & Deployment Steps
Launch an EC2 instance (Amazon Linux).

Install Apache and enable CGI.

Place index.html in /var/www/html/.

Place feedback.py in /usr/lib/cgi-bin/.

Give execute permission:

bash
Copy code
chmod +x feedback.py
Create DynamoDB table.

Attach IAM role to EC2.

Access application via EC2 public IP.

✅ Output Verification
Feedback form loads successfully.

Submission redirects to confirmation page.

Data is stored in DynamoDB instantly.

IAM role access verified via EC2 metadata.

🌟 Key Learnings
Hosting dynamic web applications on EC2

Using CGI with Python

Secure AWS access using IAM roles

Real-time NoSQL data storage with DynamoDB

End-to-end AWS service integration

📌 Future Enhancements
Convert backend to AWS Lambda

Use API Gateway instead of CGI

Add CSS for better UI

Add timestamps and validation

Enable HTTPS using ALB + ACM

👨‍💻 Author
Arman Shaikh
Aspiring AWS & Cloud Engineer
