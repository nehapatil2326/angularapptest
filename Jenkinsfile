pipeline{ 
	agent any
	stages {
		stage("checkout")
		{
			steps{
				checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/nehapatil2326/angularHelloworld']]])
			}
		}
	

		stage("docker build image")
		{
			steps{
					withCredentials([usernamePassword(credentialsId: 'dockerhub', passwordVariable: '', usernameVariable: '')]) {
						sh "docker build ."
					}
				}
		}
}
}
