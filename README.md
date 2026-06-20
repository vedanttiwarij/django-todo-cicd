# 🚀 Django Todo App — CI/CD Pipeline

![Jenkins](https://img.shields.io/badge/Jenkins-D24939?style=for-the-badge&logo=jenkins&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2CA5E0?style=for-the-badge&logo=docker&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white)
![Django](https://img.shields.io/badge/Django-092E20?style=for-the-badge&logo=django&logoColor=white)

> A production-style CI/CD pipeline that automatically 
> builds and deploys a Django app on AWS EC2 
> every time code is pushed to GitHub.

---

## 🔄 How The Pipeline Works

GitHub Push → Jenkins Detects → 
Docker Build → Deploy on EC2 → 
App Live in 60 seconds

---

## 🏗️ Architecture

<img width="2720" height="2080" alt="django_cicd_architecture" src="https://github.com/user-attachments/assets/e4c3a9fd-e990-4258-8c74-a79ebbc2e2ac" />

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| Django | Web application |
| Docker | Containerization |
| Jenkins | CI/CD automation |
| AWS EC2 | Cloud server |
| GitHub | Source control |

---

## ⚡ Pipeline Stages

| Stage | What Happens |
|-------|-------------|
| Clone | Jenkins pulls latest code |
| Build | Docker image created |
| Deploy | Container live on EC2 |

---

## 📸 Screenshots

### Jenkins Pipeline — Green ✅
<img width="1920" height="1080" alt="Screenshot (391)" src="https://github.com/user-attachments/assets/8a6e2b6c-60f5-4b79-9964-10e69ba4dc82" />


### Live App on AWS ✅
<img width="1920" height="1080" alt="Screenshot (390)" src="https://github.com/user-attachments/assets/f30846e8-db74-4dfc-a5f7-10583634024e" />



---

## 🔗 Live Demo

App URL: http://98.81.131.42:8000/todos/

---

## 🧠 What I Learned

- Setting up Jenkins inside Docker on EC2
- Writing Jenkinsfile with declarative pipeline
- Solving real errors: port conflicts, 
  memory issues, container naming conflicts
- Adding SWAP memory to optimize EC2
- Production-grade Docker deployment

---

## 👨‍💻 Author

**Vedant Tiwari**
DevOps Engineer | AWS | Docker | Jenkins
[LinkedIn](www.linkedin.com/in/
vedanttiwarij

) | [GitHub](https://github.com/vedanttiwarij)
