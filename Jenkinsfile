pipeline {
    agent any
environment {
        LC_ALL = 'en_US.UTF-8'
        LANG    = 'en_US.UTF-8'
        LANGUAGE = 'en_US.UTF-8'
       
        
    }

    stages {
        stage('Git Pull') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/krishnapriya99/flutter.git'


            }

          
        }
        
        stage('Flutter Build iOS') {
              steps {
                  sh 'flutter build ios  --release --no-codesign'
              }
        }
        stage('fastlane build'){
            steps{
                 dir(path: 'ios') {

            sh 'fastlane custom_lane'
        }
               
        }
    }
}
}