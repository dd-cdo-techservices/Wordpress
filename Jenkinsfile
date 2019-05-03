pipeline {
  
  agent any  
  
  stages {
    stage('checkout') {
      steps {
        checkout scm
  	    }
    	}
    
    
    stage('Deploy App') {
      steps {
	echo 'Deploying Wordpress Application on AWS Node'
	sh 'ansible all -i targethost.ini -m ping -u ec2-user --private-key=/home/ec2-user/.ssh/id_rsa'
        sh 'ansible-playbook -i targethost.ini wordpress.yml -u ec2-user --private-key=/home/ec2-user/.ssh/id_rsa'
        cleanWs()
      }
    }
  }
}
