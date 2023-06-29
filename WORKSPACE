load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

RULES_JVM_EXTERNAL_TAG = "4.3"
RULES_JVM_EXTERNAL_SHA = "6274687f6fc5783b589f56a2f1ed60de3ce1f99bc4e8f9edef3de43bdf7c6e74"

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# rules_cc defines rules for generating C++ code from Protocol Buffers.
http_archive(
    name = "rules_cc",
    sha256 = "35f2fb4ea0b3e61ad64a369de284e4fbbdcdba71836a5555abb5e194cf119509",
    strip_prefix = "rules_cc-624b5d59dfb45672d4239422fa1e3de1822ee110",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/rules_cc/archive/624b5d59dfb45672d4239422fa1e3de1822ee110.tar.gz",
        "https://github.com/bazelbuild/rules_cc/archive/624b5d59dfb45672d4239422fa1e3de1822ee110.tar.gz",
    ],
)

# rules_java defines rules for generating Java code from Protocol Buffers.
http_archive(
    name = "rules_java",
    sha256 = "ccf00372878d141f7d5568cedc4c42ad4811ba367ea3e26bc7c43445bbc52895",
    strip_prefix = "rules_java-d7bf804c8731edd232cb061cb2a9fe003a85d8ee",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/rules_java/archive/d7bf804c8731edd232cb061cb2a9fe003a85d8ee.tar.gz",
        "https://github.com/bazelbuild/rules_java/archive/d7bf804c8731edd232cb061cb2a9fe003a85d8ee.tar.gz",
    ],
)

# rules_proto defines abstract rules for building Protocol Buffers.
http_archive(
    name = "rules_proto",
    sha256 = "2490dca4f249b8a9a3ab07bd1ba6eca085aaf8e45a734af92aad0c42d9dc7aaf",
    strip_prefix = "rules_proto-218ffa7dfa5408492dc86c01ee637614f8695c45",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/rules_proto/archive/218ffa7dfa5408492dc86c01ee637614f8695c45.tar.gz",
        "https://github.com/bazelbuild/rules_proto/archive/218ffa7dfa5408492dc86c01ee637614f8695c45.tar.gz",
    ],
)

load("@rules_cc//cc:repositories.bzl", "rules_cc_dependencies")
rules_cc_dependencies()

load("@rules_java//java:repositories.bzl", "rules_java_dependencies", "rules_java_toolchains")
rules_java_dependencies()
rules_java_toolchains()

load("@rules_proto//proto:repositories.bzl", "rules_proto_dependencies", "rules_proto_toolchains")
rules_proto_dependencies()
rules_proto_toolchains()

http_archive(
  name = "rules_jvm_external",
  sha256 = RULES_JVM_EXTERNAL_SHA,
  strip_prefix = "rules_jvm_external-%s" % RULES_JVM_EXTERNAL_TAG,
  url = "https://github.com/bazelbuild/rules_jvm_external/archive/%s.zip" % RULES_JVM_EXTERNAL_TAG,
)

load("@rules_jvm_external//:defs.bzl", "maven_install")

maven_install(
  artifacts = [
    "junit:junit:4.12",
    "com.google.guava:guava:28.0-jre",
    "org.projectlombok:lombok:1.18.22",

    "org.springframework.boot:spring-boot-starter-web:2.3.8.RELEASE",
    "org.springframework.boot:spring-boot-starter-jdbc:2.3.8.RELEASE",
    "org.springframework.boot:spring-boot-starter-test:2.3.8.RELEASE",
    "org.springframework.boot:spring-boot:2.3.8.RELEASE",
    "org.springframework.boot:spring-boot-devtools:2.3.8.RELEASE",

    "com.alibaba:druid-spring-boot-starter:1.1.21",
    "org.mybatis.spring.boot:mybatis-spring-boot-starter:1.3.2",

    "mysql:mysql-connector-java:8.0.11",
    "org.mybatis:mybatis:3.4.1",
    "org.apache.directory.studio:org.apache.commons.codec:1.8",
    "com.alibaba:fastjson:1.2.70",
    "com.alibaba.cloud:spring-cloud-starter-alibaba-nacos-config:2.2.7.RELEASE",
    "com.alibaba.cloud:spring-cloud-starter-alibaba-nacos-discovery:2.2.7.RELEASE",
    "org.springframework.cloud:spring-cloud-starter-openfeign:2.2.7.RELEASE",

    "com.baomidou:mybatis-plus-boot-starter:3.4.3.4",
    "org.xerial:sqlite-jdbc:3.41.2.1",
    "net.devh:grpc-spring-boot-starter:2.13.1.RELEASE",
  ],
  fetch_sources = True,
  repositories = [
    "http://uk.maven.org/maven2",
    "https://jcenter.bintray.com/",
  ],
)