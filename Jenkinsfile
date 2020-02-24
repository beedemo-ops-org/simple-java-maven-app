pipeline {
  agent { 
    kubernetes {
      label 'maven-alpine-pod'
       yamlFile 'mvn-pod.yaml'
     }
  }  
  stages {
    stage ('Build') {
      steps {
        container ('maven') {
          sh 'mvn -B -DskipTests clean package'
        }
      }
    }
    stage ('Test') {
      steps {
         container ('maven') {
           sh 'mvn test'
         }
      }
    }
  }
}