pipeline {
    agent any
    stages {
        stage('Install') {
            steps {
                git 'https://github.com/Trauma/ui-test-urls.git'
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh 'npm run test'
                sh 'touch backstop_data/ci_report/xunit.xml'
                junit 'backstop_data/ci_report/xunit.xml'
            }
        }
        stage('Publish') {
            steps {
              publishHTML target: [
                 allowMissing: false,
                 alwaysLinkToLastBuild: false,
                 keepAll: true,
                 reportDir: 'backstop_data/html_report/',
                 reportFiles: 'index.html',
                 reportName: 'Rapports backstopJS'
               ]
            }
        }
        stage('Validation') {
            steps {
              input message: "Test de non regression ok ?"
              sh 'npm run approve'
            }
        }
    }
}
