#!/usr/bin/env groovy
@Library('pipeline-library-demo')
import com.packages.*
//import com.packages.GlobalClass
//import com.packages.GlobalClass2
def gc = new GlobalClass2()
 stage('Function') {
     echo 'Hello world'
     sayHello 'uzzal'

 }
 stage('Variables') {
  echo 'Library Variables Class Implement'
  println GlobalClass.foo
 
 }

stage('Multi Funtion') {
  echo 'Multifunction Library Implement'
  gc.function1('function1')
  gc.function2('function2')
  gc.function3('function3')

 }
