pipeline {
    agent {
        docker { image 'node:16.13.1-alpine' }
    }
    
    
    stages{
      stage('Build') { 
            steps { 
                script{
                app = docker.build("node:16.13.1-alpine")
                }
            }
       }
//      stage('run) {
//            steps {
//                script{
//                    bat "docker run -d node:16.13.1-alpine"
//                }
//            }
//        }     
            
}
}

