@Library(['github.com/indigo-dc/jenkins-pipeline-library@fix/tox_builder_143']) _

def projectConfig

pipeline {
    agent any

    stages {
        stage('SQA baseline dynamic stages') {
            steps {
                script {
                    projectConfig = pipelineConfig(
                        configFile: '.sqa/config.yml',
                        scmConfigs: [ localBranch: true ]
                    )
                    buildStages(projectConfig)
                }
            }
            post {
                cleanup {
                    cleanWs()
                }
            }
        }
    }
}
