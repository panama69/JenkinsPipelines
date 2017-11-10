pipeline {
    //agent any
    //agent none
    agent { label 'nimbusserver' }
    stages {
        stage('Build/Test') {
            //agent { label 'nimbusserver' }
            steps {
                //sh 'make check'
                git 'ssh://root@nimbusserver:9022/GitRepo/Octane_Gherkin'
                //sh 'mvn clean test'
                //sh 'mvn clean install -Dmaven.test.failure.ignore=true'
            }

            //build job: 'AOS_Web_Regression_Test'
            //post {
            //    always {
            //        echo "Post build stuff here"
            //        //junit '**/target/*.xml'
            //        //hp-application-automation-tools-plugin
            //        //archive '**/RunResults/run*'
            //        //archive '**/README.md'
            //    }
            //}
        }
        stage ('Archive'){
            steps {
                archive '**/README.md'
                archive '**/RunResults/run*'
            }
        }
        stage ('Publish To Octane'){
            steps {
                echo "Publish stuff to Octane"
                //junit '**/target/*.xml'
                //hp-application-automation-tools-plugin
            }
        }
    }
}
