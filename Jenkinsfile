pipeline {
         agent any
         environment {
        z_cred = credentials('MainframeID')
         }
         stages {
                 stage('BIND') {
                 steps {
                     echo 'Dhinesh Testing for bind'
                     //echo $(env.USER)
                      bat "C://Users/ADMINISTRATOR//AppData//Roaming//npm//zowe zos-jobs submit data-set cbs.zcon.jcl(bind) --vasc --host 192.86.33.94 --port 10443 --user $z_cred_USR --pass $z_cred_PSW"
                       }
                 }
                 stage('CICS INSTALL') {
                 steps {
                     echo 'Dhinesh Testing for cics'
                      //bat "C://Users/ADMINISTRATOR//AppData//Roaming//npm//zowe cics install program cgbmsrg cbsgrp --region-name cicsts54"
                     //bat "C://Users/ADMINISTRATOR//AppData//Roaming//npm//zowe zos-jobs submit data-set cbs.zcon.jcl(bind) --vasc --host 192.86.33.94 --port 10443 --user ibmuser --pass tcs2047"
                       }
                 }
           }
         }
