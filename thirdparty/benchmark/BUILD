package(default_visibility = ["//visibility:public"])

cc_library(
    name = "benchmark",
    srcs = [
        "upstream/src/arraysize.h",
        "upstream/src/benchmark_api_internal.h",
        "upstream/src/benchmark.cc",
        "upstream/src/benchmark_register.cc",
        "upstream/src/check.h",
        "upstream/src/colorprint.cc",
        "upstream/src/colorprint.h",
        "upstream/src/commandlineflags.cc",
        "upstream/src/commandlineflags.h",
        "upstream/src/complexity.cc",
        "upstream/src/complexity.h",
        "upstream/src/console_reporter.cc",
        "upstream/src/csv_reporter.cc",
        "upstream/src/cycleclock.h",
        "upstream/src/internal_macros.h",
        "upstream/src/json_reporter.cc",
        "upstream/src/log.h",
        "upstream/src/mutex.h",
        "upstream/src/re.h",
        "upstream/src/reporter.cc",
        "upstream/src/sleep.cc",
        "upstream/src/sleep.h",
        "upstream/src/stat.h",
        "upstream/src/string_util.cc",
        "upstream/src/string_util.h",
        "upstream/src/sysinfo.cc",
        "upstream/src/sysinfo.h",
        "upstream/src/timers.cc",
        "upstream/src/timers.h",
        "upstream/src/counter.cc",
        "upstream/src/counter.h"
    ],
    hdrs = [
        "upstream/include/benchmark/benchmark.h",
        "upstream/include/benchmark/benchmark_api.h",
        "upstream/include/benchmark/macros.h",
        "upstream/include/benchmark/reporter.h",
    ],
    defines = ["HAVE_POSIX_REGEX"],
    includes = [
                "upstream/include"
                ],
    linkopts = ["-pthread"],
)