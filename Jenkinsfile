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
        
     //   stage('build')
        
    //    {
        	//steps{
        	//        script{
        	//        sh "ansible-playbook ansible/build.yml -i ansible/inventory/host.yml"	
        
     //   }
   //     }
      //  }
        stage('ng Build') {
             steps{
                script{
                    sh "sudo ng build"
                }
            }
        }
        stage('Docker') {
             steps{
                script{
                    sh "sudo ansible-playbook ansible/docker.yml -i ansible/inventory/host.yml"
                }
            }
        }	        
        }
        }

