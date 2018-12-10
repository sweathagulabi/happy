pipeline{
     agent any
          stages{
	     stage('one'){
	              steps{
		         echo "hi this is swetha"
			   }
			  }
	    stage('two'){
	              steps{
		         input('do u want to proceed?')
			   }
			 }
	   stage('three'){
	             when{
		          not{ 
			     branch "master"
			     }
			  }
			steps{
			 echo "hello"
			 }
			}
           stage('four'){
	              parallel{
		        stage('unit testing'){
			              steps{
				         echo "unit testing"
					   }
					   }
			stage('integration testing'){
			                  agent{
					       docker{
					            reuseNode false
						    image 'ubuntu'
						    }
						} 
					steps{
					  echo "sucess"
					     }
					     }
					    }

                                 }

			         }
				 }
			   
	
	          

	         
