node {
    stage ("Checkout VulabMicroservice"){
        git branch: 'main', url: ' https://github.com/foxwas/vulab-microservice-maven.git'
    }
    
    stage ("Maven Build - VulabMicroservice") {
	
        sh 'mvn compile'

    }
    
    stage ("Package - VulabMicroservice") {
        sh  'mvn package'
    }
    
    stage ("API Tests- VulabMicroservice") {
        sh  'mvn test'
    }
    
    stage('User Acceptance Test - VulabMicroservice') {
	
	  def response= input message: 'Is this build good to go?',
	   parameters: [choice(choices: 'Yes\nNo', 
	   description: '', name: 'Pass')]
	
	  if(response=="Yes") {

	    stage('Release- VulabMicroservice') {
	     sh 'echo VulabMicroservice is ready to release!'

	    }
	  }
    }
}