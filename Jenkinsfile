pipeline {
    agent any
    
   tools{
        maven "MAVEN"
    }

    
    stages {
        stage('Checkout') {
            steps {
                
                git credentialsId: 'github-cred', url: 'https://github.com/JijendranP/docker-tomcat-tutorial.git' // code+Dokerfile
            }
        }

       stage('Build'){
            steps{
                sh "mvn clean install"
            }
        }
    

        stage('DOCKER'){
            steps{
                sh '''
                whoami
                pwd
                whoami
                docker build -t applicationimage .							
                docker images									
                docker run -itd --name applicationcontainer -p 80:81 applicationimage	
                docker ps										
                 '''
            }
        }
        
        
    }
}

/*
docker build -t applicationimage .							// build the docker file
docker images									// check the list of docker images present
docker run -itd --name applicationcontainer -p 80:81 applicationimage	// create a container using docker image
docker ps										// checking the list of docker containers present
*/
