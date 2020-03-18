workspace(name = "tf_networking")

load("//third_party/tensorflow:tf_configure.bzl", "tf_configure")
load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
load("@bazel_tools//tools/build_defs/repo:utils.bzl", "maybe")
load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")

tf_configure(
    name = "local_config_tf",
)

maybe(
    http_archive,
    name = "bazel_skylib",
    sha256 = "1dde365491125a3db70731e25658dfdd3bc5dbdfd11b840b3e987ecf043c7ca0",
    url = "https://github.com/bazelbuild/bazel-skylib/releases/download/0.9.0/bazel_skylib-0.9.0.tar.gz",
)

load("@bazel_skylib//:workspace.bzl", "bazel_skylib_workspace")

bazel_skylib_workspace()

maybe(
    http_archive,
    name = "com_google_protobuf",
    sha256 = "b9e92f9af8819bbbc514e2902aec860415b70209f31dfc8c4fa72515a5df9d59",
    strip_prefix = "protobuf-310ba5ee72661c081129eb878c1bbcec936b20f0",
    urls = ["https://github.com/protocolbuffers/protobuf/archive/310ba5ee72661c081129eb878c1bbcec936b20f0.tar.gz"],
)

load("@com_google_protobuf//:protobuf_deps.bzl", "protobuf_deps")

protobuf_deps()

maybe(
    http_archive,
    name = "com_github_nelhage_rules_boost",
    sha256 = "f8c9653c1c49489c04f9f87ab1ee93d7b59bb26a39d9e30e9687fca3c6197c3f",
    strip_prefix = "rules_boost-9f9fb8b2f0213989247c9d5c0e814a8451d18d7f",
    urls = ["https://github.com/nelhage/rules_boost/archive/9f9fb8b2f0213989247c9d5c0e814a8451d18d7f.tar.gz"],
)

load("@com_github_nelhage_rules_boost//:boost/boost.bzl", "boost_deps")

boost_deps()

maybe(
    http_archive,
    name = "fmtlib",
    build_file = "//third_party:fmtlib.BUILD",
    sha256 = "3c812a18e9f72a88631ab4732a97ce9ef5bcbefb3235e9fd465f059ba204359b",
    strip_prefix = "fmt-5.2.1",
    urls = [
        "https://github.com/fmtlib/fmt/archive/5.2.1.tar.gz",
    ],
)

maybe(
    http_archive,
    name = "cares",
    build_file = "//third_party/cares:cares.BUILD",
    sha256 = "03f708f1b14a26ab26c38abd51137640cb444d3ec72380b21b20f1a8d2861da7",
    strip_prefix = "c-ares-1.13.0",
    urls = [
        "https://c-ares.haxx.se/download/c-ares-1.13.0.tar.gz",
    ],
)

maybe(
    http_archive,
    name = "yaml-cpp",
    build_file = "//third_party:yaml-cpp.BUILD",
    sha256 = "77ea1b90b3718aa0c324207cb29418f5bced2354c2e483a9523d98c3460af1ed",
    strip_prefix = "yaml-cpp-yaml-cpp-0.6.3",
    urls = [
        "https://github.com/jbeder/yaml-cpp/archive/yaml-cpp-0.6.3.tar.gz",
    ],
)

maybe(
    http_archive,
    name = "ragel",
    build_file = "//third_party:ragel.BUILD",
    sha256 = "5f156edb65d20b856d638dd9ee2dfb43285914d9aa2b6ec779dac0270cd56c3f",
    strip_prefix = "ragel-6.10",
    urls = [
        "http://www.colm.net/files/ragel/ragel-6.10.tar.gz",
    ],
)

maybe(
    http_archive,
    name = "cryptopp",
    build_file = "//third_party:cryptopp.BUILD",
    sha256 = "e3bcd48a62739ad179ad8064b523346abb53767bcbefc01fe37303412292343e",
    strip_prefix = "cryptopp-CRYPTOPP_8_2_0",
    urls = [
        "https://github.com/weidai11/cryptopp/archive/CRYPTOPP_8_2_0.tar.gz",
    ],
)

maybe(
    http_archive,
    name = "lz4",
    build_file = "//third_party:lz4.BUILD",
    sha256 = "658ba6191fa44c92280d4aa2c271b0f4fbc0e34d249578dd05e50e76d0e5efcc",
    strip_prefix = "lz4-1.9.2",
    urls = [
        "https://github.com/lz4/lz4/archive/v1.9.2.tar.gz",
    ],
)

maybe(
    http_archive,
    name = "sctp",
    build_file = "//third_party:sctp.BUILD",
    sha256 = "3e9ab5b3844a8b65fc8152633aafe85f406e6da463e53921583dfc4a443ff03a",
    strip_prefix = "lksctp-tools-1.0.18",
    urls = ["https://github.com/sctp/lksctp-tools/archive/v1.0.18.tar.gz"],
)

maybe(
    http_archive,
    name = "gnutls",
    build_file = "//third_party:gnutls.BUILD",
    sha256 = "bfacf16e342949ffd977a9232556092c47164bd26e166736cf3459a870506c4b",
    strip_prefix = "gnutls-3.6.12",
    urls = ["https://www.gnupg.org/ftp/gcrypt/gnutls/v3.6/gnutls-3.6.12.tar.xz"],
)

maybe(
    http_archive,
    name = "seastar",
    build_file = "//third_party:seastar.BUILD",
    sha256 = "27f1d42e77acfb8bcccd102e417fdaa81b3c8d589a8e7b009dd3312dcf6fbeef",
    strip_prefix = "seastar-seastar-19.06.0",
    urls = [
        "https://github.com/scylladb/seastar/archive/seastar-19.06.0.tar.gz",
    ],
)

maybe(
    http_archive,
    name = "concurrentqueue",
    build_file = "//third_party:concurrentqueue.BUILD",
    sha256 = "d723e784e4d54f7519208bd795f2aa799a449b873dbb7a1251f288e04be23465",
    strip_prefix = "concurrentqueue-1.0.0-beta",
    urls = [
        "https://github.com/cameron314/concurrentqueue/archive/v1.0.0-beta.tar.gz",
    ],
)

maybe(
    http_archive,
    name = "readerwriterqueue",
    build_file = "//third_party:readerwriterqueue.BUILD",
    sha256 = "67a761278457ab1f113086449c1938e501f272be7f0fd50be28887c1274fe580",
    strip_prefix = "readerwriterqueue-1.0.1",
    urls = [
        "https://github.com/cameron314/readerwriterqueue/archive/v1.0.1.tar.gz",
    ],
)
