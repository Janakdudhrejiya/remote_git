pipeline {
    agent any

    stages {
        stage('Git CheckOut') {
            steps {
                git 'https://github.com/Janakdudhrejiya/remote_git.git'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying'
                sh 'cp sample.war /var/tomcat/webapps'
                sh "chmod -R 755 webapps"
                sh "chown -R tomcat.tomcat webapps"
                sh "service tomcat restart"
                            }
        }
    }
}
