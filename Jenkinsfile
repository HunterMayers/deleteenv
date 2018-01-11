pipeline {
  agent any
  
  stages {
    stage('provision env') {
      steps {
        sh '''
          branch=$BRANCH_NAME
          job=`echo $JOB_NAME | cut -d/ -f1`
          oc new-project $job-$branch
          oc adm policy add-role-to-user admin HunterMayers -n $job-$branch
        '''
      }
    }
  }

}
