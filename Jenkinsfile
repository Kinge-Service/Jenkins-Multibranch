pipeline {
	agent any 
	stages{
		stage('git-clone'){
			steps{
				checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'Kinge-Service', url: 'https://github.com/Kinge-Service/Jenkins-Multibranch.git']]])
			}
		}
		stage('parallel-stage'){
			parallel{
				stage('parallel-job1'){
					steps{
						sh 'sudo systemctl status jenkins'
					}
				}
				stage('parallel-job2'){
					steps{
						echo "Welcome to Kinge Services"
					}
				}
			}
		}
		stage('parallel-stage2'){
			parallel{
				stage('parallel-job3'){
					steps{
						sh 'lscp && cat /etc/passwd | grep ubuntu'
					}
				}
				step('parallel-job4'){
					steps{
						echo " End of parallel"
					}
				}
			}
		}
		stage('Process check'){
			steps{
				sh ' sudo ps -ef'
			}
		}
	}
}
