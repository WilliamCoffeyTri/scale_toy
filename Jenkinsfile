pipeline {
  agent any
  stages {
    stage('build arr36') {
      parallel {
        stage('build arr36') {
          steps {
            sh 'echo gcc -o arr36-c-false-1.o src/ARR36-C/arr36-c-false-1.c'
            sh 'echo gcc -o arr36-c-true-1.o src/ARR36-C/arr36-c-true-1.c'
          }
        }

        stage('build dcl31') {
          steps {
            sh 'echo gcc -o dcl31-c-false-1.o src/DCL31-C/dcl31-c-true-1.c'
          }
        }

        stage('build exp33') {
          steps {
            sh 'echo gcc -o exp33-c-false-1.o src/EXP33-C/exp33-c-false-1.c'
            sh 'echo gcc -o exp33-c-true-1.o src/EXP33-C/exp33-c-true-1.c'
          }
        }

        stage('build exp34') {
          steps {
            sh 'echo gcc -o exp34-c-false-1.o src/EXP34-C/exp34-c-false-1.c'
            sh 'echo gcc -o exp34-c-true-1.o src/EXP34-C/exp34-c-true-1.c'
          }
        }

        stage('build exp36') {
          steps {
            sh 'echo gcc -o exp36-c-false-1.o src/EXP36-C/exp36-c-false-1.c'
            sh 'echo gcc -o exp36-c-true-1.o src/EXP36-C/exp36-c-true-1.c'
          }
        }

        stage('build int31') {
          steps {
            sh 'echo gcc -o int31-c-false-1.o src/INT31-C/int31-c-false-1.c'
            sh 'echo gcc -o int31-c-true-1.o src/INT31-C/int31-c-true-1.c'
          }
        }

        stage('build int33') {
          steps {
            sh 'echo gcc -o int33-c-false-1.o src/INT33-C/int33-c-false-1.c'
            sh 'echo gcc -o int33-c-true-1.o src/INT33-C/int33-c-true-1.c'
          }
        }

        stage('build str31') {
          steps {
            sh 'echo gcc -o str31-c-false-1.o src/STR31-C/str31-c-false-1.c'
            sh 'echo gcc -o str31-c-true-1.o src/STR31-C/str31-c-true-1.c'
          }
        }

      }
    }

    stage('error') {
      steps {
        input 'Approve'
        sh 'pwd; docker run -v jenkins_home:/var/jenkins_home  ghcr.io/cmu-sei/cert-rosecheckers/rosebud:latest sh -c "rosecheckers \\$(find $(pwd) -name \\"*.c\\") 2>&1" > rosecheckers.txt'
      }
    }

    stage('Post') {
      steps {
        sh 'pwd; cat rosecheckers.txt; /var/jenkins_home/post_to_scaife.sh $GIT_COMMIT'
      }
    }

  }
}