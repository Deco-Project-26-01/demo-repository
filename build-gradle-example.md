# build.gradle 예시 (DB + Dependency 설정)

아래는 Spring Boot 기반 데모 프로젝트에서 DB 설정과 기본 의존성을 포함한 `build.gradle` 예시입니다.

```gradle
plugins {
    id 'java'
    id 'org.springframework.boot' version '3.2.5'
    id 'io.spring.dependency-management' version '1.1.4'
}

group = 'com.example'
version = '0.0.1-SNAPSHOT'

java {
    toolchain {
        languageVersion = JavaLanguageVersion.of(17)
    }
}

repositories {
    mavenCentral()
}

dependencies {
    // Spring Web
    implementation 'org.springframework.boot:spring-boot-starter-web'

    // Spring Data JPA
    implementation 'org.springframework.boot:spring-boot-starter-data-jpa'

    // DB Driver (예: PostgreSQL)
    runtimeOnly 'org.postgresql:postgresql'

    // Validation
    implementation 'org.springframework.boot:spring-boot-starter-validation'

    // Test
    testImplementation 'org.springframework.boot:spring-boot-starter-test'
}

tasks.named('test') {
    useJUnitPlatform()
}
```

### H2 (개발용 인메모리 DB)로 바꾸고 싶을 때
PostgreSQL 대신 아래처럼 교체해서 사용합니다.

```gradle
runtimeOnly 'com.h2database:h2'
```

### MySQL로 바꾸고 싶을 때
PostgreSQL 대신 아래처럼 교체해서 사용합니다.

```gradle
runtimeOnly 'com.mysql:mysql-connector-j'
```
