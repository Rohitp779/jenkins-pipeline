pipeline {
    agent { node { label 'built-in'
    customWorkspace '/var/jenkins_home/jenkins-cicd/' } //for jenkins docker work dir
    }
    stages {
        stage('Checkout') {
            steps {
                sh '''
                rm -rf game-of-life
                git clone https://github.com/Dee601/game-of-life.git
                cd game-of-life
                '''
                echo 'Checkout Successfully'
            }
        }
        stage('Build') {
            steps {
                sh '''
                cd /home/ec2-user/game-of-life
                mvn clean install
                '''
                echo 'Build Successfully'
            }
        }
        stage('Deploy') {
            steps {
                sh 'cp game-of-life/gameoflife-web/target/gameoflife.war /mnt/apache-tomcat-9.0.81/webapps'
                echo 'Build Successfully'
            }
        }
    }
}
