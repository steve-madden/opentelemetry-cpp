package(default_visibility = ["//visibility:public"])

cc_library(
    name = "etw_exporter",
    hdrs = glob([
        "include/opentelemetry/exporters/etw/*.h",
    ]),
    includes = ["include"],
    local_defines = [
        "HAVE_MSGPACK",
    ],
    deps = [
        "//api",
        "//sdk/src/trace",
        "@github_nlohmann_json//:json",
    ],
)

cc_test(
    name = "etw_provider_test",
    srcs = ["test/etw_provider_test.cc"],
    local_defines = [
        "HAVE_MSGPACK",
    ],
    deps = [
        ":etw_exporter",
        "@com_google_googletest//:gtest_main",
        "@github_nlohmann_json//:json",
    ],
)

cc_test(
    name = "etw_tracer_test",
    srcs = ["test/etw_tracer_test.cc"],
    local_defines = [
        "HAVE_MSGPACK",
    ],
    deps = [
        ":etw_exporter",
        "@com_google_googletest//:gtest_main",
        "@github_nlohmann_json//:json",
    ],
)
