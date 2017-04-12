# DevOpsProblem
The above script sets up tomcat , apache  , mod_jk, proxy , mysql on the defined hosts. It starts tomcat to initalize listeners on specified ports and also sets apache httpd loadbalancer to balance load on the ports specified.

The below script also setups a sample petstore project so the it can be used for testing the above setup

Step by Step guide to run this ansible script 
	- Update the hosts on which you want to run the script in hosts file 
     
    Example : 
          54.133.33.323
          56.22.563.33
  
  - Update ports on which you want to start tomcat in group_vars/all/conf.yml file 
  
      Example : 
          ports: ["8080", "8081" , "5638" ...]
                
  - Run the script using below command :
  
         ansible-playbook --user ubuntu -i hosts --ask-pass site.yml -vvvv --ask-become-pass
         
  - To Test the above setup use below url 
 
       http://{{ hostname  }}/petstore
       
       Example: 
              http://54.144.48.88/petstore
       
         
   
