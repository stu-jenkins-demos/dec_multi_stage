
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
        stage('Stage1') {
            steps {
                container('maven') {
                    sh 'mvn -v'
                }
            }
        }
        stage('Stage2') {
            when {
                expression {
                    return false
                }
                beforeAgent true
            }
            agent {
                kubernetes {
                    label 'pl_declarative_full_example_build_image_2'
                    containerTemplate {
                        name 'mavenjdk11'
                        image 'maven:3-jdk-11-slim'
                        ttyEnabled true
                        command 'cat'
                    }
                }
            }
            steps {
                container('mavenjdk11') {
                    sh 'mvn -v'
                }
            }
        }
    }
}
