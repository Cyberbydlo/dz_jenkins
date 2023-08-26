pipeline {
    agent any
    parameters {
  string defaultValue: 'Borodin Andrey', name: 'MY_STRING'
}
    stages {
        stage('Build') {
            steps {
                // Устанавливаем зависимости
                sh 'yum install -y python3-pip'
                sh 'pip install -r requirements.txt'
            }
        }
        stage('Run') {
            steps {
                sh 'python3 hello.py -n "${MY_STRING}" > result.txt'
            }
         }   
     stage('Save Result') {
            steps {
                // Артефакт сборки - файл result.txt
                archiveArtifacts artifacts: 'result.txt'
            }
        }
    }
}
