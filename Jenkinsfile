pipeline 
{
    agent any
    stages 
    {
        stage('Pull latest code from GitHub repository') 
        {
            steps 
            {
               git 'https://github.com/22120429/MMTNC_Project_2.git'
            }
        }

        stage('Build and push Docker image to Docker Hub') 
        {
            steps 
            {
                withDockerRegistry(credentialsId: 'dockerhub', url: 'https://index.docker.io/v1/') 
                {
                    // Build the Docker image 
                    bat 'docker build -t 22120429/mmtnc .'
                    // Push the image to Docker Hub
                    bat 'docker push 22120429/mmtnc'
                }
            }
        }
    }
}