pipeline {
    agent any

    parameters {
      string(name: 'COMMIT_HASH', defaultValue: '')
      string(name: 'RSTUDIO_VERSION',  defaultValue: '2024.12.0', description: 'Posit Workbench calendar version')
      string(name: 'SLACK_CHANNEL', defaultValue: '#ide-builds', description: 'Slack channel to publish build message.')
      string(name: 'FLAVOR_FILTER', defaultValue: 'all', description: 'Pattern to limit builds by matching FLAVOR')
      booleanParam(name: 'FORCE_BUILD_DOCKER', defaultValue: false, description: 'Force Docker image rebuild, even if were no changes to the Dockerfile or the version/RELEASE file. Defaults to false')
      booleanParam(name: 'PUBLISH', defaultValue: false, description: 'If TRUE uploads the documents, otherwise only builds. Defaults to false')
      booleanParam(name: 'RELEASE', defaultValue: false, description: 'If TRUE, these docs will be copied to the default unversioned release URLs. Defaults to false')
    }

    stages {
        stage('promote docs') {
            steps {
                echo "COMMIT_HASH: ${params.COMMIT_HASH}"
                echo "RSTUDIO_VERSION: ${params.RSTUDIO_VERSION}"
                echo "SLACK_CHANNEL: ${params.SLACK_CHANNEL}"
                echo "FLAVOR_FILTER: ${params.FLAVOR_FILTER}"
                echo "FORCE_BUILD_DOCKER: ${params.FORCE_BUILD_DOCKER}"
                echo "PUBLISH: ${params.PUBLISH}"
                echo "RELEASE: ${params.RELEASE}"
            }
        }
    }
}
