pipeline { 
    environment { 
        registry = "nandishaggarwal1999/capstoneproject" 
        registryCredential = 'dockerhub_id' 
        dockerImage = '' 
    }
    agent any 
    stages { 
        stage('Cloning our Git') { 
            steps { 
                git 'https://github.com/Nandishaggarwal/capstone-project.git' 
                echo "Cloned"

            }
        } 
        stage('Building our image') { 
            steps { 
                sh "docker-compose build"
                echo "Image Build"
            } 
        }
        stage('Deploy our image') { 
            steps { 
                sh "docker-compose up -d"
                echo "Image Deployed"
            }
        } 
        
        stage('Cleaning up') { 
            steps { 
                sh "docker-compose down --rmi all" 
                echo "Cleanup complete"
            }
        } 
        
    }
}
