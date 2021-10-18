pipeline {
    agent {
    kubernetes {
        label 'pl_declarative_full_example_build_image_1'
        containerTemplate {
            name 'maven'
            image 'maven:3.3.9-jdk-8-alpine'
            ttyEnabled true
            command 'cat'
        }
    }
                    }
    stages {
        parallel {
      stage('Building Image 1') {  
        steps {
          echo 'building image 1 '
          echo '''doing lots of work on b
          image
          1
          '''
                        
        }
      }
      stage('Building Image 1') {  
        steps {
          echo 'building image 1 '
          echo '''doing lots of work on b
          image
          1
          '''
                        
        }
      }
     }
    }      
