pipeline {
    agent any
    environment {
        GCP_PROJECT_ID = 'nyc3-prod-ss-roundtable'
        GCP_STAGING_DIRECTORY = "g-juggernaut-test/staging"
        GCP_OUTPUT_DIRECTORY = "g-juggernaut-test/output"
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh '''
                mvn compile exec:java \
                -Dexec.mainClass=com.example.WordCount\
                -Dexec.args="--project=$GCP_PROJECT_ID \
                    --stagingLocation=gs://$GCP_STAGING_DIRECTORY \
                    --runner=BlockingDataflowPipelineRunner \
                    --output=gs://$GCP_OUTPUT_DIRECTORY"
                '''
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}