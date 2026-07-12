pipeline {

    agent any

    parameters {

        string(
            name: 'VERSION',
            defaultValue: '1.0',
            description: 'Application Version'
        )

        choice(
            name: 'ENVIRONMENT',
            choices: ['DEV', 'QA', 'UAT', 'PROD'],
            description: 'Select Environment'
        )

        booleanParam(
            name: 'DEPLOY',
            defaultValue: false,
            description: 'Deploy Application?'
        )
    }

    stages {

        stage('Display Parameters') {
            steps {

                echo "Version      : ${params.VERSION}"
                echo "Environment  : ${params.ENVIRONMENT}"
                echo "Deploy       : ${params.DEPLOY}"

            }
        }

        stage('Build') {
            steps {
                echo "Building Version ${params.VERSION}"
            }
        }

        stage('Deploy') {

            when {
                expression {
                    params.DEPLOY == true
                }
            }

            steps {

                echo "Deploying to ${params.ENVIRONMENT}"

            }

        }

    }

}
