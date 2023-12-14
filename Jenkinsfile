pipeline {
    agent any
    environment{
        PASSWORD =credentials('PASSWORD')
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
                ansible-playbook robo-dryrun.yml -e ENV=dev -e COMPONENT=redis -e ansible_user=${SSH_CRED_USER} -e ansible_password=${SSH_CRED_PWD} 
                '''
            }

        }

    }

}