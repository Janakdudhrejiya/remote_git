pipeline {
    agent any

    stages {
        stage('Git CheckOut') {
            steps {
                git 'git@github.com:Janakdudhrejiya/remote_git.git'
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
                sh cp */war /var/tomcat/webapps
                sh "chmod 755 webapps"
                sh "chown tomcat.tomcat webapps"
                sh "service tomcat restart"
            }
        }
    }
}
