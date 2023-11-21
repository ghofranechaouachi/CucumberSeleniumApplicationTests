pipline {
    agent any
    tools {
        maven 'maven'
    }
    stages{
        stage('Build'){
            steps {
                sh 'mvn -B compile'
            }    

        }
        stage('Test'){
            steps {
                sh 'mvn -B clean install'
                cucumber failedFeaturesNumber: -1, failedScenariosNumber: -1, failedStepsNumber: -1, fileIncludePattern: '**/*.json',
                pendingStepsNumber: -1, skippedStepsNumber: -1, sortingMethod: 'ALPHABETICAL', undefinedStepsNumber: -1
                
            }

        }
        stage('Archive'){
            steps{
                archiveArtifacts 'target/*.jar'
            }

        }



  
    }


}
