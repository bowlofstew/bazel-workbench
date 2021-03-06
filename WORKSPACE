http_archive(
    name = "com_github_nelhage_boost",
    strip_prefix = "rules_boost-ead0110ff90d5d90d2eb67e7e78f34f42d8486a1",
    type = "tar.gz",
    urls = [
        "https://github.com/nelhage/rules_boost/archive/ead0110ff90d5d90d2eb67e7e78f34f42d8486a1.tar.gz"
    ],
)

load("@com_github_nelhage_boost//:boost/boost.bzl", "boost_deps")
boost_deps()

new_http_archive(
    name = "docker_alpinelinux",
    url = "https://nl.alpinelinux.org/alpine/v3.5/releases/x86_64/alpine-minirootfs-3.5.1-x86_64.tar.gz",
    build_file = "alpinelinux.BUILD",
    sha256 = "fa17f25ded0b29d94d8cc2d9aabb6f737f4b987c42fe8a6d11e05cfe2c52a64c",
)

rules_scala_version="d916599d38de29085e5ca9eae167716c4f150a02"

http_archive(
             name = "io_bazel_rules_scala",
             url = "https://github.com/bazelbuild/rules_scala/archive/%s.zip"%rules_scala_version,
             type = "zip",
             strip_prefix= "rules_scala-%s" % rules_scala_version
             )

load("@io_bazel_rules_scala//scala:scala.bzl", "scala_repositories")
scala_repositories()

git_repository(
    name = "io_bazel_rules_pex",
    remote = "https://github.com/tanin47/bazel_rules_pex.git",
    tag = "0.3.0",
)

load('//python:pypi.bzl', 'pip', 'pip_requirements')
load("//python:requirements.bzl", "requirements")
load("@io_bazel_rules_pex//pex:pex_rules.bzl", "pex_repositories")

pex_repositories()
pip()

pip_requirements(
    name='requirements',
    packages=requirements
)

git_repository(
  name = "org_pubref_rules_protobuf",
  remote = "https://github.com/pubref/rules_protobuf",
  tag = "v0.7.1",
  #commit = "..." # alternatively, latest commit on master
)

load("@org_pubref_rules_protobuf//java:rules.bzl", "java_proto_repositories")
java_proto_repositories()

load("@org_pubref_rules_protobuf//cpp:rules.bzl", "cpp_proto_repositories")
cpp_proto_repositories()

# Guava

maven_jar(
    name = "guava_maven",
    artifact = "com.google.guava:guava:19.0",
)

bind(
  name = "guava",
  actual = "@guava_maven//jar"
)

# JUnit

maven_jar(
    name = "junit_maven",
    artifact = "junit:junit:4.12",
)

bind(
  name = "junit",
  actual = "@junit_maven//jar"
)

# Apache Commons

maven_jar(
  name = "apache_commons_lang3_maven",
  artifact = "org.apache.commons:commons-lang3:3.4"
)

bind(
  name = "apache_commons_lang3",
  actual = "@apache_commons_lang3_maven//jar"
)

bind(
  name = "benchmark",
  actual = "//thirdparty/benchmark",
)