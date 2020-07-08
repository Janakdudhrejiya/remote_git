pipeline {
    agent any

    stages {
        stage('Git CheckOut') {
            steps {
                git 'https://github.com/Janakdudhrejiya/remote_git.git'
            }
        }
        stage('Build') {
            steps {
                echo 'Building'
                sh "mvn package"
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying'
                sh 'cp sample.war /var/tomcat/webapps'
                sh "chmod 755 webapps"
                sh "chown tomcat.tomcat webapps"
                sh "service tomcat restart"
                            }
        }
    }
}
