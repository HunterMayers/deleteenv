pipeline {
  agent any
  
  stages {
    stage('provision env') {
      steps {
        sh '''
          branch=`echo $BRANCH_NAME | awk '{print tolower($0)}'`
          job=`echo $JOB_NAME | cut -d/ -f1 | awk '{print tolower($0)}'`
          oc new-project $job-$branch
          oc adm policy add-role-to-user admin HunterMayers -n $job-$branch
        '''
      }
    }
  }

}
