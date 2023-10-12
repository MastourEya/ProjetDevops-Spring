pipeline {
  agent any
  stages {
    stage('Envoyer un e-mail') {
      steps {
        email(
          subject: 'Nouveau commit',
          body: 'Le fichier README.txt a été mis à jour.',
          to: 'eya.mastour@esprit.com',
          attachments: 'README.txt'
        )
      }
    }
  }
}
