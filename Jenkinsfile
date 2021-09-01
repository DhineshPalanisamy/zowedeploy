pipeline {
         agent  { 
                label 'WindowsAgent'
                }
         environment {
        z_cred = credentials('MianframeIBMUSER')
        //PATH="C://Users//Administrator//AppData//Roaming//npm//node_modules//newman//bin//newman:$PATH"
         }
         stages {
                 stage('BIND Test region') {
                 steps {
                     echo 'bind in test region'                    
                      bat "C://Users/ADMINISTRATOR//AppData//Roaming//npm//zowe zos-jobs submit data-set cbs.zcon.jcl.srce(bind2) --vasc --host 192.86.33.94 --port 10443 --user $z_cred_USR --pass $z_cred_PSW --ru false"
                       }
                 }
                 stage('CICS INSTALL in test region') {
                 steps {
                     echo 'installing programs in cics'
                       bat "C://Users/ADMINISTRATOR//AppData//Roaming//npm//zowe cics install program cbsrgdbb cbsgrp --region-name cicsts54"                    
                       }
                 }
                 stage('API TESTING in test region') {
                 steps {
                     echo 'Testing for API'
                       //bat 'C://Users//Administrator//AppData//Roaming//npm//newman.cmd run --disable-unicode https://www.getpostman.com/collections/35a2bc7d0fd3c6ae5992 --insecure'
                       }
                 }
	        stage('WAZI VPT Test Playback for API Service') {
                 steps {
                     echo 'Playback for cics'
                       //bat "C://Users/ADMINISTRATOR//AppData//Roaming//npm//zowe zos-jobs submit data-set cbs.zcon.jcl.srce(bzuzplay) --vasc --host 192.86.33.94 --port 10443 --user $z_cred_USR --pass $z_cred_PSW --ru false"
                       }
                 }
	       stage('WAZI VPT Test Playback for Batch') {
                 steps {
                     echo 'Playback for Batch'            
                      //bat "C://Users/ADMINISTRATOR//AppData//Roaming//npm//zowe zos-jobs submit data-set cbs.zcon.jcl(bzsbatp) --vasc"
                       }
                 }
                 stage('COPY DATASET to PROD') {
                 steps {
                     echo 'Copying to prod hlq'
                       bat "C://Users/ADMINISTRATOR//AppData//Roaming//npm//zowe zos-jobs submit data-set cbs.zcon.jcl(copypds) --vasc --host 192.86.33.94 --port 10443 --user $z_cred_USR --pass $z_cred_PSW"
                       }
                 }
           }
         }
