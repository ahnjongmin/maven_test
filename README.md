# maven_test

1). dependency 추출하여 저장

dependency:copy-dependencies 실행하며, target 경로 아래에 dependency라는 폴더에 사용된던 라이브러리를 추출하여 저장한다.


명령어: mvn dependency:copy-dependencies

 

2). dependency 포함하여 Jar 파일 생성

 

pom.xml 파일에 아래와 같이 Assembly 플러그인 내용을 추가

 

<project>
  <build>
    <plugins>
      <plugin>
        <groupId>org.apache.maven.plugins</groupId>
        <artifactId>maven-assembly-plugin</artifactId>
        <version>2.2.1</version>
        <configuration>
          <descriptorRefs>
            <descriptorRef>jar-with-dependencies</descriptorRef>
          </descriptorRefs>
        </configuration>
      </plugin>
    </plugins>
  </build>
</project>


명령어: mvn assembly:assembly

 

-jar-with-dependencies 이름으로 생성된 파일이 dependency가 포함된 Jar  파일이다.
