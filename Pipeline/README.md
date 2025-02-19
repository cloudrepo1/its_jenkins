# Simple-declarative pipeline 👇

Declarative is a more recent and advanced implementation of a pipeline as a code.

### jenkins-file

```
pipeline {
     agent any

     stages {
         stage('Jenkins for DevOps') {
             steps {
                 echo 'Hello World'
             }
         }
     }
 }

```

# steps :

1. Navigate to the Jenkins home page. Create a new Job and select Pipeline.
2. Now configure the project with valid description.
3. Now, navigate to the Pipeline section to write the groovy pipeline code(jenkinsfile)
4. Click on Save and then build now.
5. Let's see the output.

===================END====================================


# Docker-jenkins-declarative-pipeline😎👇

# steps :

1. Install & connect jenkins on your ubuntu system
2. Install docker on your ubuntu system

```
sudo apt install docker.io -y
docker --version
```

3. Apply docker permission

```
sudo usermod -aG docker jenkins
sudo systemctl restart docker
sudo systemctl restart jenkins
```
   
4. start Project
   
    - Go to jenkins dashboard
    - Create new item = myproject
    - Select pipeline project
    - Mention github project section = your github repo url
    - Pipeline = use jenkinsfile
    - Build now✌️✌️✌️✌️


### Jenkins file :- docker deploy


```
pipeline {
    agent any

    stages {
        stage('code clone') {
            steps {
                echo "code cloning hogya repo se"
                git url: "https://github.com/cloudrepo1/jenkins-project-repo.git"
            }
        }
        stage('code build') {
            steps {
                echo "code build v karliye"
                sh "docker build . -t myappimg:latest"
            }
        }
        stage('code test') {
            steps {
                echo "code testing hogya"
            }
        }
        stage('code deploy') {
            steps {
                echo "deploying v hogya h container k andar"
                sh "docker run -itd -p 8000:8000 myappimg:latest"
            }
        }
    }
}

```
=====================END=============================
