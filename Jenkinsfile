pipeline {agent any
     
     stages {
        stage('Run schemachange') {
        agent  any
       # docker { 
          #  image "python:3.8"
         #   args '--user 0:0'
        #} 

    
            steps {
                sh "pip install schemachange --upgrade"
                sh "schemachange -f migrations -a ${SF_ACCOUNT} -u ${SF_USERNAME} -r ${SF_ROLE} -w ${SF_WAREHOUSE} -d ${SF_DATABASE} -c ${SF_DATABASE}.SCHEMACHANGE.CHANGE_HISTORY --create-change-history-table"
            }
        }
    }
}