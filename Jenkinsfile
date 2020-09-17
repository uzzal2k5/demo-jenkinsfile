#!/usr/bin/env groovy
@Library('pipeline-library-demo')
import com.packages.GlobalClass
def gc = new com.packages.GlobalClass()

 stage('Function') {
     echo 'Hello world'
     sayHello 'uzzal'

 }
 stage('Class') {
  echo 'Library Class Implement'
  println GlobalClass.foo
  gc.function1('DemoTest')
 }
