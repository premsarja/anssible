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
                
                ansible-playbook robo-dryrun.yml -e ENV=${dev} -e COMPONENT=${COMPONENT} -e ansible_user=${PASS_USR} -e ansible_password=${PASS_PWD}
                
                '''
            }

        }

    }

}