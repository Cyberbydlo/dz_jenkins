pipeline {
    agent any
    parameters {
  string defaultValue: 'Borodin Andrey', name: 'NAME_STR'
}
    stages {
        stage('Build') {
            steps {
                // Устанавливаем зависимости
                sh 'yum install -y python3-pip'
                sh 'pip install -r requirements.txt'
            }
        }
     stages {
        stage('Run') {
            steps {
                sh 'python3 hello.py -n "${NAME_STR}" > result.txt'
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
}
