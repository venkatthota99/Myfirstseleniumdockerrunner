pipeline{
	agent any
	stages{
		stage("pull Latest Image"){
			steps{
				sh "docker pull thotavenkatdocker/seleniumdocker"
			}
		}
		stage("Start Grid"){
			steps{
				sh "docker-compose up -d hub chrome firefox"
			}
		}
		stage("Run Test"){
			steps{
				sh "docker-compose up Searchpagestestng  testng"
			}
		}
	}
	post{
		always{
			archiveArtifacts artifacts: 'output/**'
			sh "docker-compose down"
		}
	}
}
