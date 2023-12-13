pipeline {
    agent any
    environment{
        SSHCRED =credentials('SSHCRED')
        // PATH = "/home/ec2-user/.local/bin/ansible" // Add Ansible path
    }
    parameters{        
        string(name: 'COMPONENT', defaultValue: 'mongodb', description: 'who should i say hello co' )
        choice(name: 'CHOICE', choices: ['one','two','three' ], description: 'pick something')
    }
    
    stages {
        stage('performing dryrun') {
            steps{
                sh '''
                ansible-playbook robo-dryrun.yml
                '''
            }

        }

    }

}