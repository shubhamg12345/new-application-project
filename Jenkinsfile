pipeline {
	agent {
		label {
					label 'built-in'
					customWorkspace '/mnt'
		}		
	}
	stages {
		stage ('install-apache'){
					steps{	
							sh 'sudo service httpd stop'
							sh 'sudo yum remove httpd -y'	
							sh 'sudo sleep 5'
							sh 'sudo yum install httpd -y'
							sh 'sudo service httpd start'
					}			
		}
		stage ('copy-html'){
					steps {
					dir ('/mnt/new-application'){
							sh 'cp -r index.html /var/www/html'
							sh 'cp -r qa.html /var/www/html'
							sh 'cp -r dev.html /var/www/html'
							sh 'sudo chmod -R /var'					
					}
					}		
		}
	}
}
