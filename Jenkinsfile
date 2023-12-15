pipeline {
    agent any
    environment{
        SSH_CRED =credentials('SSH_CRED')
        // PATH = "/home/ec2-user/.local/bin/ansible" // Add Ansible path
    }
    // parameters{        
    //     string(name: 'COMPONENT', defaultValue: 'mongodb', description: 'who should i say hello co' )
    //     choice(name: 'CHOICE', choices: ['one','two','three' ], description: 'pick something')
    // }
    
    stages {
        stage('performing dryrun') {
            steps{
                sh '''
                env
                ansible-playbook robo-dryrun.yml -e ENV=dev -e COMPONENT=redis -e ansible_user=${PASSWORD_USR} -e ansible_password=${PASSWORD_PSD} 
                '''
            }

        }

    }

}