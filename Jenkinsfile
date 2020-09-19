#!/usr/bin/env groovy
@Library('pipeline-library-demo')
import com.packages.*
//import com.packages.GlobalClass
//import com.packages.MultiFunction

def gclass = new GlobalClass()
def gc = new MultiFunction()
 
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
 stage('Global Class Funtion') {
  echo 'Global CLass Library Implement'
  gclass.function1('Global CLass function1')
  

 }
