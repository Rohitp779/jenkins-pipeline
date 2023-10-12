pipeline {
    agent { node { label 'linux-rohit' } }
    parameters {
                    string(name: 'PERSON', defaultValue: 'Mr ROHIT PATIL', description: 'I have created web project deploy pipeline.')
    }
    stages {
        stage('SCM-Checkout') {
            steps {
                dir('/home/ec2-user/') {
                    sh 'rm -rf game-of-life'
                    sh 'git clone https://github.com/Dee601/game-of-life.git'
                    echo 'SCM Checkout Sucessfully'
                }
            }
        }
        stage('Build') {
            steps {
                dir('/home/ec2-user/workspace/New-jenkins-pipeline/game-of-life/') {
                    sh 'mvn clean install'
                    echo 'Build Successfully'
                }
            }
        }
       stage('Test') {
            steps {
                dir('/home/ec2-user/workspace/New-jenkins-pipeline/game-of-life/') {
                    sh 'mvn test'
                    echo 'Test Successfully'
                }
            }
        }
        stage('Deploy') {
            steps {
                dir('/home/ec2-user/workspace/New-jenkins-pipeline/game-of-life/gameoflife-web/target/') {
                    sh 'cp gameoflife.war /mnt/apache-tomcat-9.0.81/webapps/'
                    echo 'Deployment  Successfully'
                }
            }
        }
    }
}
