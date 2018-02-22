pipeline {
    agent any
    stages {
        stage('Install') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh 'npm test'
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
              env.approve = input message: "Test de non regression ok ?"
              ok: 'approve'
              sh 'npm ${approve}'
            }
        }
    }
}
