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
         stage('Checkout Frontend') {
            steps {
                script {
                    // Checkout du code frontend depuis GitHub (remplacez l'URL par celle de votre référentiel Angular)
                    checkout([$class: 'GitSCM',  branches: [[name: '*/main']], userRemoteConfigs: [[url: 'https://github.com/MastourEya/ProjetDevops-Angular', credentialsId: 'eya']]) // Assurez-vous de remplacer URL_DU_REPO_ANGULAR.git par l'URL de votre référentiel Angular
                }
            }
        }
        stage('Build Frontend') {
            steps {
                script {
                    // Remplacez ces commandes par celles nécessaires pour construire votre projet Angular
                    sh 'npm install'  // Exemple : installer les dépendances
                    sh 'ng build --prod'  // Exemple : construire le projet Angular en mode production
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
