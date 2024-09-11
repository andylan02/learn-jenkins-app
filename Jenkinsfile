pipeline {
    agent any

    stages {
     
        
        stage('Build') {

            steps {
                sh '''
                    ls -la
                    /opt/tool/node/bin/node --version
                    /opt/tool/node/bin/npm --version
                    /opt/tool/node/bin/npm ci
                    /opt/tool/node/bin/npm run build
                    ls -la
                '''
            }
        }
       

        stage('Test') {

            
            steps {
                sh '''
                    #test -f build/index.html
                    /opt/tool/node/bin/npm test
                '''
            }
        }
    }

    post {
        always {
            junit 'test-results/junit.xml'
        }
    }
}