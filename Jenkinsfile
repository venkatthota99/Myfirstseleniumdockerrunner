pipeline{
	agent any
	stages{
		stage("pull Latest Image"){
			steps{
				bat "docker pull thotavenkat/selenium-docker"
			}
		}
		stage("Start Grid"){
			steps{
				bat "docker-compose up -d hub chrome "
			}
		}
		stage("Run Test"){
			steps{
				bat "docker-compose up Searchpagestestng.xml"
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
