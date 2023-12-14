pipeline {
    agent any
    environment {
        SSHCRED = credentials('SSH_PRIVATE_KEY_ID')
    }

    stages {
        stage('performing dryrun') {
            steps {
                script {
                    if (SSHCRED != null) {
                        withCredentials([sshUserPrivateKey(credentialsId: 'SSH_PRIVATE_KEY_ID', keyFileVariable: 'SSH_KEY', passphraseVariable: 'SSH_PASSPHRASE', usernameVariable: 'SSH_USERNAME')]) {
                            sh '''
                            ansible-playbook robo-dryrun.yml -e ENV=dev -e COMPONENT=redis --private-key="${SSH_KEY}" --user="${SSH_USERNAME}"
                            '''
                        }
                    } else {
                        error 'Failed to retrieve SSH private key credentials.'
                    }
                }
            }
        }
    }
}
