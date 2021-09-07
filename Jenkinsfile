pipeline {
  agent any
  stages {
    stage('build arr36') {
      parallel {
        stage('build arr36') {
          steps {
            sh 'gcc -o arr36-c-false-1.o src/ARR36-C/arr36-c-false-1.c'
            sh 'gcc -o arr36-c-true-1.o src/ARR36-C/arr36-c-true-1.c'
          }
        }

        stage('build dcl31') {
          steps {
            sh 'gcc -o dcl31-c-false-1.o src/DCL31-C/dcl31-c-true-1.c'
          }
        }

        stage('build exp33') {
          steps {
            sh 'gcc -o exp33-c-false-1.o src/EXP33-C/exp33-c-false-1.c'
            sh 'gcc -o exp33-c-true-1.o src/EXP33-C/exp33-c-true-1.c'
          }
        }

        stage('build exp34') {
          steps {
            sh 'gcc -o exp34-c-false-1.o src/EXP34-C/exp34-c-false-1.c'
            sh 'gcc -o exp34-c-true-1.o src/EXP34-C/exp34-c-true-1.c'
          }
        }

        stage('build exp36') {
          steps {
            sh 'gcc -o exp36-c-false-1.o src/EXP36-C/exp36-c-false-1.c'
            sh 'gcc -o exp36-c-true-1.o src/EXP36-C/exp36-c-true-1.c'
          }
        }

        stage('build int31') {
          steps {
            sh 'gcc -o int31-c-false-1.o src/INT31-C/int31-c-false-1.c'
            sh 'gcc -o int31-c-true-1.o src/INT31-C/int31-c-true-1.c'
          }
        }

        stage('build int33') {
          steps {
            sh 'gcc -o int33-c-false-1.o src/INT33-C/int33-c-false-1.c'
            sh 'gcc -o int33-c-true-1.o src/INT33-C/int33-c-true-1.c'
          }
        }

        stage('build str31') {
          steps {
            sh 'gcc -o str31-c-false-1.o src/STR31-C/str31-c-false-1.c'
            sh 'gcc -o str31-c-true-1.o src/STR31-C/str31-c-true-1.c'
          }
        }

      }
    }

    stage('error') {
      steps {
        input 'Approve'
        sh 'pwd'
        sh 'mkdir -r /home/jenkins/workspace/; cp -r $(pwd) /home/jenkins/workspace/scale_toy; cd /home/jenkins/workspace/scale_toy  '
        sh 'docker run -v $(pwd):/app ghcr.io/cmu-sei/cert-rosecheckers/rosebud:latest sh -c "ls /app/etc"'
        sh 'cat rosecheckers.txt'
      }
    }

  }
}