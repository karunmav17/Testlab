node {
    // Clean workspace before doing anything
    deleteDir()

    try {
        stage ('Clone') {
            checkout scm
        }
        stage ('Build') {
            bat "echo 'shell scripts to build project...'"
        }
        stage ('Tests') {
            parallel 'static': {
                bat "echo 'shell scripts to run static tests...'"
            },
            'unit': {
                bat "echo 'shell scripts to run unit tests...'"
            },
            'integration': {
                bat "echo 'shell scripts to run integration tests...'"
            }
        }
        stage('UI E2E Tests [Dev]') {
                    when {
                        anyOf {
                            branch 'develop'
                            branch 'master'
                        }
                    }
        stage ('Deploy') {
            bat "echo 'shell scripts to deploy to server...'"
        }
    } catch (err) {
        currentBuild.result = 'FAILED'
        throw err
    }
}
