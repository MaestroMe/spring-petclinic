node {
  git url: 'https://github.com/MaestroMe/spring-petclinic.git'
  def mvnHome = tool 'M3'
  cmd "${mvnHome}/bin/mvn -Dmaven.test.failure.ignore clean package"
  step([$class: 'ArtifactArchiver', artifacts: '**/target/*.jar', fingerprint: true])
  step([$class: 'JUnitResultArchiver', testResults: '**/target/surefire-reports/TEST-*.xml'])
}