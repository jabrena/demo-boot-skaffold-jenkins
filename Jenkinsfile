pipeline {

    agent any

    stages {



        stage ('Deploy Stage') {
            steps {

                withCredentials([[$class          : 'UsernamePasswordMultiBinding',
                                  credentialsId   : 'PKS_USER',
                                  usernameVariable: 'USERNAME',
                                  passwordVariable: 'PASSWORD']]) {

                    sh '/usr/local/bin/pks login -a api.pks.nilanjan.in -u $USERNAME -p $PASSWORD -k'
                    sh '/usr/local/bin/pks get-credentials pks-workshop'
                    sh '/usr/local/bin/skaffold run'
                }
            }

        }

    }

}