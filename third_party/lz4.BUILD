licenses(["notice"])  # BSD 2-clause

exports_files(["LICENSE"])

cc_library(
    name = "lz4",
    srcs = glob(["lib/*.c"]),
    hdrs = glob(["lib/*.h"]),
    strip_include_prefix = "lib",
    textual_hdrs = ["lib/lz4.c"],
    visibility = ["//visibility:public"],
)
