pipeline {
	agent none  stages {
  	stage('centos Install') {
      	docker {
        	image 'centos:latest'
        }
      }
//       steps {
//       	sh 'mvn clean install'
//       }
    }
    stage('Docker Build') {
    	agent any
      steps {
      	sh 'docker build -t raghav/firstimage:latest .'
      }
    }
    stage('Docker Push') {
    	agent any
      steps {
      	withCredentials([usernamePassword(credentialsId: 'dockerHub', passwordVariable: 'raghav1212', usernameVariable: 'raghavagarwal9660')]) {
        	sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPassword}"
          sh 'docker push raghav/firstimage:latest'
        }
      }
    }
  }
