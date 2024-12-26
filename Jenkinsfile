pipeline{
    agent{
        label 'vm-agent'
    }
    stages{
        stage('build'){
            steps{
                script{
                    sh 'docker build -t java-app .'
                }
            }
        }

        stage('push'){
            steps{
                script{
                   withCredentials([usernamePassword(credentialsId: 'dockerhub-pass', passwordVariable: 'password', usernameVariable: 'username')]) {
                    sh 'docker login --username $Username --password $Password'
                    sh 'docker tag java-app $Username/java-app'
                    sh 'docker push $Username/java-app'
                    }
                }
            }
        }

        stage('deploy'){
            steps{
                script{
                    sh 'docker run -d -p 80:80 --name my-javaweb molla2011/java-app'
                    
                    }
                }
            }
        }
    }
