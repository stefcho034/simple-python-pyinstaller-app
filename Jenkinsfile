pipeline {
    agent none 
    stages {
        stage('Build') { 
            agent {
                docker {
                    image 'zoluma/py2-onbuild' 
                }
            }
            steps {
                sh 'python -m py_compile sources/add2vals.py sources/calc.py' 
                stash(name: 'compiled-results', includes: 'sources/*.py*') 
            }
        }
    }
}