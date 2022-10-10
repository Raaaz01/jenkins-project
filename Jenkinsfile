pipeline{
    //Directives
    agent any
    tools {
        maven 'maven'
    }
  
    stages {
        // Specify various stage with in stages

        // stage 1. Build
        stage ('Build'){
            steps {
                sh 'mvn clean install package'
            }
        }

        // Stage2 : Testing
        stage ('Test'){
            steps {
                echo ' testing.........'

            }
        }
        
        // Stage3: Publish to Nexus
        stage ('Publish to Nexus'){
            steps {
                nexusArtifactUploader artifacts: [[artifactId: 'DevopsLab', classifier: '', file: 'target/DevopsLab-0.0.14-SNAPSHOT.war', type: 'war']], credentialsId: '', groupId: 'com.devopslab', nexusUrl: '107.21.62.8', nexusVersion: 'nexus3', protocol: 'http', repository: 'raju', version: '0.0.14-SNAPSHOT'
            }
        }

       // Stage4 : Deploying
        stage ('Deploy'){
            steps {
                echo ' Deploying......'

            }
        }


//stages
    }

}
