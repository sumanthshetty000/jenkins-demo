pipeline {
    agent any

    parameters {
        string(name: 'APP_NAME', defaultValue: 'demo-app')
        choice(name: 'ENV', choices: ['dev', 'test', 'prod'])
        booleanParam(name: 'RUN_TESTS', defaultValue: true)
    }

    stages {
        stage('Build') {
            steps {
                echo "Building ${APP_NAME}"
            }
        }

        stage('Test') {
            when {
                expression { RUN_TESTS }
            }
            steps {
                sh 'echo Running tests'
            }
        }

        stage('Deploy') {
    steps {
        sh '''
          chmod +x demo.sh
          ./demo.sh
        '''
    }
}
