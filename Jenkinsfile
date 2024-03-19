pipeline {
    agent any
    
  /*  tools{
        maven "MAVEN"
    }
*/
    
    stages {
        stage('Checkout') {
            steps {
                
                git credentialsId: 'github-cred', url: 'https://github.com/JijendranP/docker-tomcat-tutorial.git'
            }
        }

     /*   stage('Build'){
            steps{
                sh "mvn clean install"
            }
        }
    */

        stage('DOCKER'){
            steps{
                sh '''
                whoami
                pwd
                whomami
                docker build -t applicationimage .
                docker images
                docker run -itd --name applicationcontainer -p 80:81 .
                docker ps
                 '''
            }
        }
        
        
    }
}
