pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                script {
                    // Checkout du code depuis GitHub
                    checkout([$class: 'GitSCM', branches: [[name: '*/main']], userRemoteConfigs: [[url: 'https://github.com/MastourEya/ProjetDevops-Spring.git', credentialsId: 'eya']]])
                }
            }
        }
        stage('Envoyer un e-mail') {
            steps {
                emailext body: "Veuillez trouver ci-dessous le contenu du README.md :\n\n${readFile('README.md')}",
                subject: "Nouveau commit sur GitHub",
                to: 'eyamastour22@gmail.com'
            }
        }
    }
}
