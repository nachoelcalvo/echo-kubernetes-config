pipeline {
    triggers {
        pollSCM('* * * * *')
    }

    environment {
        PATH = "$OC_TOOL:$PATH"
        ocProject = 'cicd'
        ocBuildConfig = 'echo'
        ocDeploymentConfig = 'echo'
    }

    agent  any

    stages {
        stage('Deploy') {
            steps {
                openshiftDeploy(namespace: "${ocProject}", deploymentConfig: "${ocDeploymentConfig}")
            }
        }
    }
}
