node {
    stage ("Checkout VulabMicroservice"){
        git branch: 'main', url: ' https://github.com/foxwas/vulab-microservice-maven.git'
    }
    
    stage ("Maven Build - VulabMicroservice") {
	
        'mvn compile'

    }
    
    stage ("Package - VulabMicroservice") {
         'mvn package'
    }
    
    stage ("API Tests- VulabMicroservice") {
         'mvn test'
    }
    
    stage('User Acceptance Test - VulabMicroservice') {
	
	  def response= input message: 'Is this build good to go?',
	   parameters: [choice(choices: 'Yes\nNo', 
	   description: '', name: 'Pass')]
	
	  if(response=="Yes") {

	    stage('Release- VulabMicroservice') {
	     'echo VulabMicroservice is ready to release!'

	    }
	  }
    }
}