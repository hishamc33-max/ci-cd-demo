🚀 CI/CD Pipeline using Jenkins on RHEL 9
📌 Project Overview
This project demonstrates the implementation of a Continuous Integration and Continuous Deployment (CI/CD) pipeline using Jenkins. The pipeline automates the process of fetching code from GitHub and deploying it to a web server without manual intervention.

🎯 Objectives
Automate code integration
Enable automatic deployment
Ensure consistency and reliability
Reduce manual effort in deployment
🛠️ Tools & Technologies Used
Jenkins – Automation server
GitHub – Source code repository
RHEL 9 – Operating system
Apache (httpd) – Web server
Git – Version control system
🏗️ Architecture
GitHub → Jenkins → Apache Server → Live Website

⚙️ Implementation Steps
Installed Java 17 for Jenkins
Installed and configured Jenkins on RHEL 9
Installed Git for version control
Created a GitHub repository and added index.html
Created a Jenkins pipeline job
Configured pipeline to clone repository and deploy code
Set proper permissions and configured SELinux
Verified deployment on Apache web server
Configured GitHub webhook for automatic deployment
🔁 CI/CD Pipeline Flow
Developer pushes code to GitHub
GitHub sends webhook to Jenkins
Jenkins pulls latest code
Jenkins deploys code to /var/www/html
Website updates automatically
📜 Jenkins Pipeline Script
pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git branch: 'main', url: 'https://github.com/hishamc33-max/ci-cd-demo.git'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                rm -rf /var/www/html/*
                cp -r * /var/www/html/
                '''
            }
        }
    }
}
