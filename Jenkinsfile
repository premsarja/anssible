pipeline {
    agent any
    environment{
        PASSWORD =credentials('PASSWORD')
    }
    parameters{        
        string(name: 'COMPONENT', defaultValue: 'mongodb', description: 'who should i say hello co' )
        choice(name: 'CHOICE', choices: ['one','two','three' ], description: 'pick something')
    }
    
    stages {
        stage('performing dryrun') {
            steps{
                sh '''
                ansible-playbook robo-dryrun.yml  -e ENV=dev -e COMPONENT=mongodb -e ansible_user=${SSH_CRED_USR} -e ansible_password=${SSH_CRED_PSW} 
 
                '''
            }

        }

    }

}