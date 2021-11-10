pipeline {
  agent any
    stages {
        stage('Pull') {
             steps{
                script{
                    checkout([$class: 'GitSCM', branches: [[name: '*/master']],
                        userRemoteConfigs: [[
                            credentialsId: 'c5d71fe3-c5c5-4e22-849e-4f0b3eaa1e59',
                            url: 'https://github.com/haifgh/Myapp.git']]])
                }
            }
        }
        stage('Install') {
             steps{
                script{
                    sh "sudo npm install"
                }
            }
        }
        stage('build')
        
        {
        	steps{
        	        script{
        	        sh "ansible-playbook Ansible/build.yml -i Ansible/inventory/host.yml"	
        
        }
        }
        }	        
        }
        }

