package(default_visibility = ["//visibility:public"])

proto_library(
    name = "metrics2_proto",
    srcs = ["src/proto/metrics2.proto"],
)

cc_proto_library(
    name = "metrics2_cc_proto",
    deps = [":metrics2_proto"],
)

cc_library(
    name = "seastar",
    srcs = glob(
        ["src/**/*.cc"],
        exclude = [
            "src/testing/*.cc",
        ],
    ) + glob(
        ["src/**/*.hh"],
    ),
    hdrs = glob(
        ["include/seastar/**/*.hh"],
        exclude = [
            "include/seastar/testing/*.hh",
        ],
    ) + [
        "include/seastar/http/request_parser.hh",
        "include/seastar/http/response_parser.hh",
    ],
    copts = [
        "-DNO_EXCEPTION_HACK",
        "-DNO_EXCEPTION_INTERCEPT",
        "-DDEFAULT_ALLOCATOR",
        "-DHAVE_NUMA",
    ],
    includes = [
        "src",
    ],
    linkopts = [
        "-ldl",
        "-lm",
        "-lrt",
        "-lstdc++fs",
    ],
    strip_include_prefix = "include",
    deps = [
        ":metrics2_cc_proto",
        "//third_party/xfs",
        "@boost//:asio",
        "@boost//:filesystem",
        "@boost//:fusion",
        "@boost//:lockfree",
        "@boost//:program_options",
        "@boost//:system",
        "@boost//:thread",
        "@boost//:variant",
        "@cares",
        "@cryptopp",
        "@fmtlib",
        "@gnutls",
        "@lz4",
        "@org_lzma_lzma//:lzma",
        "@sctp",
        "@systemtap-sdt",
        "@yaml-cpp",
    ],
)

genrule(
    name = "generate_http_request_parser",
    srcs = ["src/http/request_parser.rl"],
    outs = ["include/seastar/http/request_parser.hh"],
    cmd = "\n".join([
        "$(location @ragel//:ragelc) -G2 -o $@ $<",
        "sed -i -e '1h;2,$$H;$$!d;g' -re 's/static const char _nfa[^;]*;//g' $@",
    ]),
    tools = ["@ragel//:ragelc"],
)

genrule(
    name = "generate_http_response_parser",
    srcs = ["src/http/response_parser.rl"],
    outs = ["include/seastar/http/response_parser.hh"],
    cmd = "\n".join([
        "$(location @ragel//:ragelc) -G2 -o $@ $<",
        "sed -i -e '1h;2,$$H;$$!d;g' -re 's/static const char _nfa[^;]*;//g' $@",
    ]),
    tools = ["@ragel//:ragelc"],
)
