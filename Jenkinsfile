pipeline {
    agent any
     tools {
        maven 'Maven'
         jdk  'JDK'
         nodejs 'node'
    }

    stages {
     
        
        stage('Build') {

            steps {
                sh '''
                    ls -la
                    node --version
                    npm --version
                    npm ci
                    npm run build
                    ls -la
                '''
            }
        }
       

        stage('Test') {

            
            steps {
                sh '''
                    #test -f build/index.html
                    npm test
                '''
            }
        }
    }

    post {
        always {
            junit 'jest-results/junit.xml'
        }
    }
}