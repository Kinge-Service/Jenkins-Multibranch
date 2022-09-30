pipeline {
	agent any 
	stages{
		stage('git-clone'){
			steps{
				checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'Kinge-Service', url: 'https://github.com/Kinge-Service/Jenkins-Multibranch.git']]])
			}
		}
		stage('parallel stage'){
			parallel{
				stage('parallel-job1'){
					steps{
						sh 'ps -ef'
					}
				}
				stage('parallel-job2'){
					steps{
						sh 'sudo systemctl status jenkins'
					}
				}
				stage('user-check'){
					steps{
						sh 'cat /etc/passwd | grep jenkins'
					}
				}
			}
		}
		stage('system check'){
			steps{
				echo "Welcome to Etech"
			}
		}
	}
}