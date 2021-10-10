pipeline {
  agent any
  stages {
    stage('Create Src1') {
      parallel {
        stage('Create Src1') {
          steps {
            sh '''echo "abc1" > Src1
echo "def1" >> Src1
echo "def2" >> Src1'''
          }
        }

        stage('Create Src2') {
          steps {
            sh '''echo "abc1" > Src2
echo "def2" >> Src2
echo "ghi3" >> Src2'''
          }
        }

      }
    }

    stage('Grep1') {
      parallel {
        stage('Grep1') {
          steps {
            sh 'grep "abc" * >> Grp'
          }
        }

        stage('Grep2') {
          steps {
            sh 'grep "2" * >> Grp'
          }
        }

      }
    }

    stage('Check7') {
      steps {
        sh '''cat Grp | wc -l 
echo "-----------------------------------"
grep "abc" *
echo "-----------------------------------"
grep "2" * >> Grp'''
      }
    }

  }
}