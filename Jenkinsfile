pipeline {
    agent any

    stages {
        stage('Merge') {
            steps {
                sh '''
                cd D:/franchis/Desktop/test_jenkins
                git fetch
                git checkout develop
                git pull origin develop
                git merge origin/workingbranch
                git push origin develop
                '''
            }
        }
    }

    post {
        failure {
            echo 'El merge ha fallado, posiblemente debido a conflictos'
        }
        success {
            echo 'Merge completado satisfactoriamente'
        }
    }
}