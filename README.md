
# 📺 AI-Powered Image Analyzer on AWS-Serverless AI Application with Terraform, AWS Bedrock & Rekognition

## 🧠 Overview  
This project demonstrates how to design and deploy a **serverless AI-powered image analysis application** using modern **cloud-native architecture and Infrastructure as Code (IaC)**. The system allows users to upload an image through a web interface, automatically detects objects using **AWS Rekognition**, and generates a natural-language description using **Amazon Bedrock (Mistral LLM)**. The entire infrastructure is provisioned using **Terraform** and automatically deployed using **GitHub Actions CI/CD**. This project reflects practical experience in building **end-to-end AI-powered cloud applications**, integrating AI services, serverless compute, and automated infrastructure deployment.

---

## 🎯 Project Goals
  -Build an AI-powered image analysis application
  
  -Deploy a serverless architecture on AWS
  
  -Automate infrastructure using Terraform
  
  -Implement CI/CD pipeline using GitHub Actions
  
  -Demonstrate cloud architecture design principles
  
  -Deliver a scalable, low-maintenance AI solution

---

## 🧰 Technologies Used

### ☁️ Cloud Services 
| Service                      | Purpose                           |
| ---------------------------- | --------------------------------- |
| **Amazon S3**                | Hosts the frontend static website |
| **Amazon CloudFront**        | CDN for fast global delivery      |
| **AWS Lambda**               | Backend processing logic          |
| **Amazon API Gateway**       | Exposes the REST API              |
| **AWS Rekognition**          | Image label detection             |
| **Amazon Bedrock (Mistral)** | AI description generation         |
| **AWS IAM**                  | Role and permission management    |

### ⚙️ DevOps & Infrastructure
| Tool               | Purpose                |
| ------------------ | ---------------------- |
| **Terraform**      | Infrastructure as Code |
| **GitHub Actions** | CI/CD automation       |
| **Git**            | Version control        |

### 💻 Programming & Frontend
| Technology                  | Purpose                        |
| --------------------------- | ------------------------------ |
| **Python**                  | Lambda backend                 |
| **HTML / CSS / JavaScript** | Web interface                  |
| **JSON API**                | Frontend–backend communication |

---

## 🏗️ Architecture Diagram
Below is the system architecture illustrating how the application processes images and generates AI insights.

![Architecture Diagram](images/Architecture-AWS_image_analyzer.png)

---

## 🔄 System Workflow

1. **User Uploads Image**
   
The user uploads an image through the web application hosted on **Amazon S3**.

3. **CloudFront Delivers Frontend**  

CloudFront provides:
 
  -global CDN delivery

   -HTTPS support

   -improved frontend performance

4. **API Gateway Receives Request**

The frontend sends the image as a base64 payload to **POST /analyze**. 

5. **Lambda Processes Image**

Lambda performs:

  -Base64 decoding

   -Image processing

   -Rekognition API calls

   -Bedrock LLM prompt generation
 
7. **Rekognition Detects Labels**

Example detected labels:

  -**Face**

   -**Head**

   -**Person**

   -**Surprised**

   -**Baby**


9. **Bedrock Generates Description**

Using the labels, Bedrock generates a natural-language description:

  **The surprised baby's face is the main focus of the image, showing their entire head as part of a full person shot.**

10. **Results Returned to Frontend**  

The Lambda function returns:
    **{
      "labels": [...],
      "description": "..."
    }**
   
![Output](images/Output1.png)

---

## ⚙️ Infrastructure as Code (Terraform)

All infrastructure resources are created using Terraform.

Terraform provisions:

  -IAM roles & policies
  
  -Lambda function deployment
  
  -API Gateway REST API
  
  -Lambda permissions
  
  -S3 static website hosting
  
  -CloudFront CDN
  
  -Terraform outputs for endpoints

Example IaC flow:

![Terraform](images/AWS_Terraform.png)

This ensures:

  -reproducible infrastructure
  
  -automated deployments
  
  -version-controlled cloud resources

## 🔄 CI/CD Pipeline (GitHub Actions)

The project includes a GitHub Actions workflow that automatically deploys infrastructure.

Pipeline workflow:
          Developer Push              
                │
                ▼
          GitHub Actions Trigger
                │
                ▼
          Terraform Init
                │
                ▼
          Terraform Validate
                │
                ▼
          Terraform Plan
                │
                ▼
          Terraform Apply
                │
                ▼
          AWS Infrastructure Updated

Benefits:
  
  -automated infrastructure deployment
  
  -reproducible environments
  
  -DevOps best practices
  
  -secure secret management

⭐ If you find this project interesting, feel free to star the repository or connect with me to discuss cloud, AI, and data engineering solutions.
