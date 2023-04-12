workspace(name = "maven_springboot")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "rules_jvm_external",
    sha256 = "f36441aa876c4f6427bfb2d1f2d723b48e9d930b62662bf723ddfb8fc80f0140",
    strip_prefix = "rules_jvm_external-4.1",
    url = "https://github.com/bazelbuild/rules_jvm_external/archive/4.1.zip",
)

load("@rules_jvm_external//:defs.bzl", "artifact", "maven_install")
load("@rules_jvm_external//:specs.bzl", "maven")

rules_kotlin_version = "1.7.1"
rules_kotlin_sha = "fd92a98bd8a8f0e1cdcb490b93f5acef1f1727ed992571232d33de42395ca9b3"
http_archive(
    name = "io_bazel_rules_kotlin",
    urls = ["https://github.com/bazelbuild/rules_kotlin/releases/download/v%s/rules_kotlin_release.tgz" % rules_kotlin_version],
    sha256 = rules_kotlin_sha,
)

load("@io_bazel_rules_kotlin//kotlin:repositories.bzl", "kotlin_repositories")
kotlin_repositories()

load("@io_bazel_rules_kotlin//kotlin:core.bzl", "kt_register_toolchains")
kt_register_toolchains()

http_archive(
    name = "rules_java",
    sha256 = "ccf00372878d141f7d5568cedc4c42ad4811ba367ea3e26bc7c43445bbc52895",
    strip_prefix = "rules_java-d7bf804c8731edd232cb061cb2a9fe003a85d8ee",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/rules_java/archive/d7bf804c8731edd232cb061cb2a9fe003a85d8ee.tar.gz",
        "https://github.com/bazelbuild/rules_java/archive/d7bf804c8731edd232cb061cb2a9fe003a85d8ee.tar.gz",
    ],
)

load("@rules_java//java:repositories.bzl", "rules_java_dependencies", "rules_java_toolchains")

rules_java_dependencies()

rules_java_toolchains()

http_archive(
    name = "rules_proto",
    sha256 = "602e7161d9195e50246177e7c55b2f39950a9cf7366f74ed5f22fd45750cd208",
    strip_prefix = "rules_proto-97d8af4dc474595af3900dd85cb3a29ad28cc313",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/rules_proto/archive/97d8af4dc474595af3900dd85cb3a29ad28cc313.tar.gz",
        "https://github.com/bazelbuild/rules_proto/archive/97d8af4dc474595af3900dd85cb3a29ad28cc313.tar.gz",
    ],
)

load("@rules_proto//proto:repositories.bzl", "rules_proto_dependencies", "rules_proto_toolchains")

rules_proto_dependencies()

rules_proto_toolchains()

http_archive(
    name = "com_google_protobuf",
    sha256 = "c96e8f755b278dc885fad43ec6afcb6e8345d2b5eb823ea717229076c17ca779",
    strip_prefix = "protobuf-3.14.x",
    url = "https://github.com/protocolbuffers/protobuf/archive/3.14.x.zip",
)

load("@com_google_protobuf//:protobuf_deps.bzl", "protobuf_deps")

protobuf_deps()

http_archive(
    name = "rules_spring",
    sha256 = "7495e33261e4e69777a611e42c2e7a4f45021f6a8bb1eae1b064ca5653a61835",
    urls = [
        "https://github.com/salesforce/rules_spring/releases/download/2.2.2/rules-spring-2.2.2.zip",
    ],
)

maven_install(
    name = "maven",

    artifacts = [
        maven.artifact("ch.qos.logback", "logback-classic", "1.2.11"),
        maven.artifact("ch.qos.logback", "logback-core", "1.2.11"),
        maven.artifact("com.fasterxml.jackson.core", "jackson-annotations", "2.13.4"),
        maven.artifact("com.fasterxml.jackson.core", "jackson-core", "2.13.4"),
        maven.artifact("com.fasterxml.jackson.core", "jackson-databind", "2.13.4.2"),
        maven.artifact("com.fasterxml.jackson.datatype", "jackson-datatype-jdk8", "2.13.4"),
        maven.artifact("com.fasterxml.jackson.datatype", "jackson-datatype-jsr310", "2.13.4"),
        maven.artifact("com.fasterxml.jackson.module", "jackson-module-parameter-names", "2.13.4"),
        maven.artifact("com.jayway.jsonpath", "json-path", "2.6.0"),
        maven.artifact("com.vaadin.external.google", "android-json", "0.0.20131108.vaadin1"),
        maven.artifact("jakarta.activation", "jakarta.activation-api", "1.2.2"),
        maven.artifact("jakarta.annotation", "jakarta.annotation-api", "1.3.5"),
        maven.artifact("jakarta.xml.bind", "jakarta.xml.bind-api", "2.3.3"),
        maven.artifact("net.bytebuddy", "byte-buddy", "1.11.22"),
        maven.artifact("net.bytebuddy", "byte-buddy-agent", "1.11.22"),
        maven.artifact("net.minidev", "accessors-smart", "2.4.8"),
        maven.artifact("net.minidev", "json-smart", "2.4.8"),
        maven.artifact("org.apache.logging.log4j", "log4j-api", "2.17.2"),
        maven.artifact("org.apache.logging.log4j", "log4j-to-slf4j", "2.17.2"),
        maven.artifact("org.apache.tomcat.embed", "tomcat-embed-core", "9.0.68"),
        maven.artifact("org.apache.tomcat.embed", "tomcat-embed-el", "9.0.68"),
        maven.artifact("org.apache.tomcat.embed", "tomcat-embed-websocket", "9.0.68"),
        maven.artifact("org.apiguardian", "apiguardian-api", "1.1.2"),
        maven.artifact("org.assertj", "assertj-core", "3.21.0"),
        maven.artifact("org.hamcrest", "hamcrest", "2.2"),
        maven.artifact("org.junit.jupiter", "junit-jupiter", "5.8.2"),
        maven.artifact("org.junit.jupiter", "junit-jupiter-api", "5.8.2"),
        maven.artifact("org.junit.jupiter", "junit-jupiter-engine", "5.8.2"),
        maven.artifact("org.junit.jupiter", "junit-jupiter-params", "5.8.2"),
        maven.artifact("org.junit.platform", "junit-platform-commons", "1.8.2"),
        maven.artifact("org.junit.platform", "junit-platform-engine", "1.8.2"),
        maven.artifact("org.mockito", "mockito-core", "4.0.0"),
        maven.artifact("org.mockito", "mockito-junit-jupiter", "4.0.0"),
        maven.artifact("org.objenesis", "objenesis", "3.2"),
        maven.artifact("org.opentest4j", "opentest4j", "1.2.0"),
        maven.artifact("org.ow2.asm", "asm", "9.1"),
        maven.artifact("org.skyscreamer", "jsonassert", "1.5.1"),
        maven.artifact("org.slf4j", "jul-to-slf4j", "1.7.36"),
        maven.artifact("org.slf4j", "slf4j-api", "1.7.36"),
        maven.artifact("org.springframework", "spring-aop", "5.3.23"),
        maven.artifact("org.springframework", "spring-beans", "5.3.23"),
        maven.artifact("org.springframework", "spring-context", "5.3.23"),
        maven.artifact("org.springframework", "spring-core", "5.3.23"),
        maven.artifact("org.springframework", "spring-expression", "5.3.23"),
        maven.artifact("org.springframework", "spring-jcl", "5.3.23"),
        maven.artifact("org.springframework", "spring-test", "5.3.23"),
        maven.artifact("org.springframework", "spring-web", "5.3.23"),
        maven.artifact("org.springframework", "spring-webmvc", "5.3.23"),
        maven.artifact("org.springframework.boot", "spring-boot", "2.6.13"),
        maven.artifact("org.springframework.boot", "spring-boot-autoconfigure", "2.6.13"),
        maven.artifact("org.springframework.boot", "spring-boot-loader", "2.6.13"),
        maven.artifact("org.springframework.boot", "spring-boot-starter", "2.6.13"),
        maven.artifact("org.springframework.boot", "spring-boot-starter-json", "2.6.13"),
        maven.artifact("org.springframework.boot", "spring-boot-starter-logging", "2.6.13"),
        maven.artifact("org.springframework.boot", "spring-boot-starter-test", "2.6.13"),
        maven.artifact("org.springframework.boot", "spring-boot-starter-tomcat", "2.6.13"),
        maven.artifact("org.springframework.boot", "spring-boot-starter-web", "2.6.13"),
        maven.artifact("org.springframework.boot", "spring-boot-test", "2.6.13"),
        maven.artifact("org.springframework.boot", "spring-boot-test-autoconfigure", "2.6.13"),
        maven.artifact("org.xmlunit", "xmlunit-core", "2.8.4"),
        maven.artifact("org.yaml", "snakeyaml", "1.29"),

        "org.jetbrains.kotlin:kotlin-reflect:1.6.21",
        "org.jetbrains.kotlin:kotlin-stdlib-common:1.6.21",
        "org.jetbrains.kotlin:kotlin-stdlib:1.6.21",
        "org.jetbrains.kotlin:kotlin-test-annotations-common:1.6.21",
        "org.jetbrains.kotlin:kotlin-test-junit:1.6.21",
        "org.jetbrains.kotlin:kotlin-test:1.6.21",
        "org.jetbrains.kotlinx:kotlinx-coroutines-core:1.6.1",
        "org.jetbrains.kotlinx:kotlinx-coroutines-slf4j:1.6.1",
        "org.jetbrains.kotlinx:kotlinx-coroutines-test:1.6.1",
        "org.jetbrains.kotlinx:kotlinx-serialization-core-jvm:1.5.0",
        "org.jetbrains.kotlinx:kotlinx-serialization-json-jvm:1.5.0",
        "org.jetbrains:annotations:24.0.0",
    ],
    repositories = [
        "https://repo1.maven.org/maven2/",
    ],
    use_unsafe_shared_cache = True,
)
