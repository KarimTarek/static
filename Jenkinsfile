pipeline {
	agent any
	stages {
		stage ('Lint HTML') {
			tidy -q -e *.html
		}
		
		stage ('Upload to AWS') {
			steps {
				withAWS(credentials:'aws-static') {
					s3Upload(file:'index.html', bucket:'karim-nano-degree-jenkins-project-3', path:'index.html')
				}
			}
		}
	}
}