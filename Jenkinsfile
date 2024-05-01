pipeline {
    agent { 
        any { 
            image "python:3.8"
            args '--user 0:0'
            label 'uma'
        } 

    }
    stages {
        stage('Run schemachange') {
            steps {
                sh "schemachange -f migrations -a ${SF_ACCOUNT} -u ${SF_USERNAME} -r ${SF_ROLE} -w ${SF_WAREHOUSE} -d ${SF_DATABASE} -c ${SF_DATABASE}.SCHEMACHANGE.CHANGE_HISTORY --create-change-history-table"
            }
        }
    }
}