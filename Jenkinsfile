pipeline {
    agent any
    stages{
        stage('build'){           
            steps{

                sh 'echo Building Python App'
                sh 'docker run -i -d --name python_alpine -v "C:\\Users\\julim\\Desktop\\Courses\\Jenkins\\simple-python-pyinstaller-app:/build" -w="//build" python:2-alpine'
                sh 'docker exec python_alpine python -m py_compile sources/add2vals.py sources/calc.py' 
                }
            post {
                   always { 
                        sh 'docker stop python_alpine'
                        sh 'docker rm python_alpine'
                }
            }
        }

        stage('Test'){           
            steps{

                sh 'echo Running Unit Tests'
                sh 'docker pull qnib/pytest'
                }            
        }
    }
}