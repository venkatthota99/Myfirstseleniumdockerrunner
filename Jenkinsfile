pipeline{
	agent any
	stages{
		stage("pull Latest Image"){
			steps{
				bat "docker pull thotavenkat/seleniumdocker"
			}
		}
		stage("Start Grid"){
			steps{
				bat "docker-compose up -d hub chrome firefox"
			}
		}
		stage("Run Test"){
			steps{
				bat "docker-compose up Searchpagestestng  testng"
			}
		}
	}
	post{
		always{
			archiveArtifacts artifacts: 'output/**'
			bat "docker-compose down"
		}
	}
}
