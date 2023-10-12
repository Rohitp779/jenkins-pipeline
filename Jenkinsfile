pipeline {
    agent { node { label 'built-in' } }
    parameters {
                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
    }
    stages {
        stage('Hello') {
            steps {
                dir('/home/ec2-user/') {
                    sh 'pwd'
                    sh 'cd .'
                    echo 'Hello World'
                }
            }
        }
        stage('Build') {
            steps {
                dir('/mnt/') {
                    sh 'pwd'
                    sh 'java -version'
                    echo 'Build Successfully'
                }
            }
        }
        stage('Deploy') {
            steps {
                dir('/var/') {
                    sh 'pwd'
                    sh 'sudo mvn -version'
                    sh 'cd .'
                    echo 'Build Successfully'
                }
            }
        }
    }
}
