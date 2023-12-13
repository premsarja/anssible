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
                env
                /home/ec2-user/ansible-playbook robo-dryrun.yml -e ENV=dev -e COMPONENT=mongodb -e ansible_user= -e ansible_password=                '''
            }

        }

    }

}