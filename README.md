\#  Flask CI/CD Pipeline using Jenkins \& GitHub Actions



\##  Project Overview



This project demonstrates a complete CI/CD pipeline for a Python Flask application using:



\* Jenkins (CI/CD pipeline)

\* GitHub (source control)

\* Pytest (testing framework)



\---



\##  Tech Stack



\* Python 3.x

\* Flask

\* Pytest

\* Jenkins (Pipeline)

\* GitHub



\---



\## Project Structure

```

flask-jenkins-app/

│── app.py

│── requirements.txt

│── test\_app.py

│── Jenkinsfile

│── README.md

```



\---



\##  Jenkins Pipeline Setup



\### 1. Create Pipeline Job



\* Open Jenkins

\* Click \*\*New Item\*\*

\* Select \*\*Pipeline\*\*

\* Choose \*\*Pipeline script from SCM\*\*

\* Add GitHub repository URL



\---



\### 2. Jenkinsfile Stages



The pipeline includes:



\### 🔹 Build Stage



\* Installs dependencies using pip



\### 🔹 Test Stage



\* Runs test cases using pytest



\### 🔹 Deploy Stage



\* Simulates deployment



\---



\## 📜 Jenkinsfile



```groovy

pipeline {

&#x20;   agent any



&#x20;   stages {



&#x20;       stage('Build') {

&#x20;           steps {

&#x20;               sh '''

&#x20;               python3 --version

&#x20;               curl -sS https://bootstrap.pypa.io/get-pip.py -o get-pip.py

&#x20;               python3 get-pip.py --user --break-system-packages



&#x20;               export PATH=$HOME/.local/bin:$PATH



&#x20;               pip3 install --upgrade pip --break-system-packages

&#x20;               pip3 install -r requirements.txt --break-system-packages

&#x20;               '''

&#x20;           }

&#x20;       }



&#x20;       stage('Test') {

&#x20;           steps {

&#x20;               sh '''

&#x20;               export PATH=$HOME/.local/bin:$PATH

&#x20;               pytest

&#x20;               '''

&#x20;           }

&#x20;       }



&#x20;       stage('Deploy') {

&#x20;           steps {

&#x20;               sh 'echo Deployment successful!'

&#x20;           }

&#x20;       }

&#x20;   }

}

```



\---



CI/CD Flow



1\. Developer pushes code to GitHub

2\. GitHub webhook triggers Jenkins

3\. Jenkins pipeline runs:



&#x20;  \* Build

&#x20;  \* Test

&#x20;  \* Deploy

4\. Results are shown in Jenkins dashboard



\---





```



\### Content Type:



```

application/json

```



\### Event:



```

Just the push event

```



\---



\## 🧪 Running Tests



```bash

pytest

```



\---



\## Output



\* Build Success ✔

\* Test Passed ✔

\* Deployment Successful ✔



\---





\---



\##  Conclusion



This project demonstrates:



\* CI/CD pipeline automation

\* Integration of Jenkins with GitHub

\* Automated testing using pytest

\* Deployment simulation



\---



\##  Repository Link



Add your GitHub repo link here:



```

https://github.com/shivanisaurabh/flask-jenkins-app

```



