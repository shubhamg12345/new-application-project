pipeline {
	agent {
		label {
					label 'built-in'
		}		
	}
	stages {
		stage ('install-apache'){
					steps{	
							sh 'yum remove httpd* -y'	
							sh 'sleep 5'
							sh 'yum install httpd -y'
							sh 'service httpd start'
					}			
		}
		stage ('copy-html'){
					steps {
							sh 'cp -r index.html /var/www/html'
							sh 'cp -r qa.html /var/www/html'
							sh 'cp -r dev.html /var/www/html'
							sh 'sudo chmod -R 777 /var'		
					}		
		}
	}
}
