pipeline {
    agent any
    stages{
        stage('build'){           
            steps{

                sh 'echo Hello World'
                sh 'docker run -i -d --name python_alpine -v "C:\\Users\\julim\\Desktop\\Courses\\Jenkins\\simple-python-pyinstaller-app:/build" python:2-alpine'
                sh 'docker exec python_alpine python -m py_compile sources/add2vals.py sources/calc.py' 
                sh 'docker stop python_alpine'
                sh 'docker rm python_alpine'
            }
        }
    }
}