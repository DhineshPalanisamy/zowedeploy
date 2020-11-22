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
                      bat "C://Users/ADMINISTRATOR//AppData//Roaming//npm//zowe cics install program cgbmsrg cbsgrp --region-name cicsts54"
                       }
                 }
                  stage('API Testing') {
                 steps {
                     echo 'Dhinesh Testing for APIs'
                        bat 'C://Users//Administrator//AppData//Roaming//npm//newman.cmd run --disable-unicode https://www.getpostman.com/collections/35a2bc7d0fd3c6ae5992 --insecure'
                       }
                 }
           }
         }
