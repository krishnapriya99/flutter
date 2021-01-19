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
        stage(' Flutter Build Android'){
                steps{
                    dir(path: 'android') {
                    sh 'flutter build apk'
                    }
                    }
                }                         
                         
                       
        stage('fastlane Android build'){
                steps{
                    dir(path: 'android') {
                    sh 'fastlane deploy'
                    }
            }
        } 
        stage('Flutter Build iOS') {
                    steps {
                        sh 'flutter build ios  --release --no-codesign'
             }
        }
         stage('fastlane build & deploy'){
                steps{
                    dir(path: 'ios') {

                sh 'fastlane custom_lane'
                }
                }
        }
       

       
        }
}
