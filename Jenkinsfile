pipeline{
          agent any
          stages{
            
               stage("Pull Latest Image"){
               
                 	steps{
                   
                    		 bat "docker pull srinivas111/selenium-docker"
                  
                   
                   }
               }

      			stage("Start Grid"){
               
               		steps{
                   
                    		 bat "docker-compose -f docker-compose-v3.yml up -d selenium-hub chrome firefox"
                   
                   
                   }
               }
               
                stage("Run Test"){
               
               		steps{
                   
                     		 bat "docker-compose -f docker-compose-v3.yml up search-module"
                   
                   
                   }
               }
			 }  
               
         post{
               
              always{
               		archiveArtifacts artifacts: 'output/**'
                   
                    bat "docker-compose -f docker-compose-v3.yml down"
                   
                   
                   }
              
               }      
                                 
                                   
        }
          



    

