pipeline {
    agent any
    
    stages {

        stage("code"){
            steps{
                git url: "https://github.com/saparprayag/Node-todo-app.git", branch: "master"
                echo 'Code cloned successfully'
            }
        }
         stage("Build and test"){
            steps{
                sh "docker build -t node-todo-app ."
                echo 'Code building done'
            }
        }
        
        stage("scan image"){
            steps{
                echo 'Image Scanning done'
            }
        }
        
        stage("deploy"){
            steps{
                sh "docker-compose down && docker-compose up -d --force-recreate --no-deps --build web"
                echo 'Deployment Done'
            }
        }
    }
}
