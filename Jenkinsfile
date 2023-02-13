pipeline{
    
agent any

stages{
    stage('checkout'){
     steps{
        git 'https://github.com/devillierscbe/hello.git'
       }
    }
   stage('Build'){
       steps{
           cmakeBuild buildDir: './', buildType: 'Debug', cleanBuild: true, installation: 'Cmake', label: 'C++', sourceDir: './', steps: [[withCmake: true]]
        }
   }
    stage('Cppcheck'){
     steps{
     sh "cppcheck --enable=all --inconclusive --xml --xml-version=2 ./ 2> cppcheck.xml"
       }
    }
 }
}
