pipeline{
	agent any
	
	tools{
		mavne 'Maven'
	}
	stages{
		stage('Checkout'){
			steps{
				git branch: 'master',url:'https://github.com/dhruthi-am/GuavaExternal.git'
			}
		}
		stage('Build'){
			steps{
				sh'mvn clean package'
			}
		}
		stage('Test'){
			steps{
				sh'mvn test'
			}
		}
		stage('Run Application'){
			steps{
				sh'mvn exec:java -Dexec.mailClass="com.example.App"'
			}
		}
	}
	post{
		success{
			echo 'Build Success'
		}
		failure{
			echo 'Build Failure'
		}
	}
}
