load("@bazel_tools//tools/build_defs/docker:docker.bzl", "docker_build")

cc_inc_library(
    name = "hello_inc",
    hdrs = ["inc/library.hpp"]
)

cc_binary(
  name = "hello",
  srcs = ["src/main.cc"],
  deps = [
    "@boost//:algorithm",
    ":hello_inc"
  ]
)

cc_test(
  name = "performance",
  srcs = ["test/performance.cc"],
  deps = [
  	"//thirdparty/benchmark",
    ":hello_inc"
  ]
)

cc_test(
    name = "googletest-example",
    srcs = ["test/googletest-example.cc"],
    copts = ["-Iexternal/gtest"],
    deps = [
      "//thirdparty/gtest:gtest_main",
    ]
)

cc_binary(
    name = "client",
    srcs = ["src/hello-client-main.cc"],
    deps = [":clientlib"],
)

cc_library(
    name = "clientlib",
    srcs = ["src/hello-client.cc"],
    hdrs = ["src/hello-client.h"],
    deps = ["//protos:cpp"],
)

cc_binary(
    name = "server",
    srcs = ["src/hello-server.cc"],
    deps = ["//protos:cpp"],
)

docker_build(
    name = "hello_docker",
    base = "@docker_alpinelinux//:35",
    files = [":hello"]
)