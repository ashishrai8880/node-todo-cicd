@Library("Shared") _
pipeline{
    agent { label "vinod" }
    
    stages{
        
        stage("Code"){
            steps{
                script{
                    clone("https://github.com/ashishrai8880/node-todo-cicd.git" , "master")
                }
            }
        }
        stage("Build"){
            steps{
                script{
                    docker_build("node-todo")
                }
            }
        }
        stage("Test"){
            steps{
                echo "This is testing the code"
            }
        }
        stage("Push to DockerHub"){
            steps{
                script{
                    docker_push("node-todo")
                }
            }
        }
        stage("Deploy"){
            steps{
                echo "This is deployment the code"
                sh "docker compose up -d"
            }
        }
    }
    
}
