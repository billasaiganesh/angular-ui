pipeline {
      agent {
        label 'slave node'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Build'
                sh 'npm run build'
            }
        }

        stage('Push') {
            steps {
                echo 'Push the dist folder to the s3 bucket'
                sh "aws s3 sync /dist/angular-demo s3://demo-ui-angular"
            }
        }
        stage('Deploy'){
            step{
                echo "Deployed"
            }
        }
    }
}