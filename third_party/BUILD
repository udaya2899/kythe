package(default_visibility = ["//visibility:public"])

# This filegroup should include all licenses of third_party libraries
# distributed in Kythe binary releases.
# Note: many of the licenses are vendored for external repo deps; double-check
# %workspace%/external.bzl to ensure that any license deleted is actually
# unused.
filegroup(
    name = "licenses",
    srcs = ["README"] + [
        "//third_party/absl:LICENSE",
        "//third_party/auto:LICENSE.txt",
        "//third_party/bazel:license",
        "//third_party/boringssl:LICENSE",
        "//third_party/errorprone:COPYING",
        "//third_party/gflags:COPYING.txt",
        "//third_party/glog:COPYING",
        "//third_party/go:licenses",
        "//third_party/guava:COPYING",
        "//third_party/jcommander:license.txt",
        "//third_party/jsr250_api:LICENSE",
        "//third_party/jsr305:LICENSE",
        "//third_party/libmemcached:COPYING",
        "//third_party/libuuid:COPYING",
        "//third_party/llvm:license",
        "//third_party/ow2-asm:LICENSE.txt",
        "//third_party/re2:LICENSE",
        "//third_party/re2j:LICENSE",
        "//third_party/riegeli:LICENSE",
        "//third_party/safe_html_types:LICENSE",
        "//third_party/truth:LICENSE",
        "//third_party/zlib:README",
        "@com_github_google_leveldb//:license",
        "@com_github_google_snappy//:license",
        "@com_github_tencent_rapidjson//:license",
        "@com_google_protobuf//:LICENSE",
        "@org_brotli//:LICENSE",
    ],
)

cc_library(
    name = "libuuid",
    srcs = ["empty.cc"],
    linkopts = select({
        "@bazel_tools//src/conditions:darwin": [],
        "//conditions:default": ["-luuid"],
    }),
)

exports_files(["libmemcached.mem_config.h"])

alias(
    name = "gtest",
    actual = "@com_google_googletest//:gtest",
)

alias(
    name = "gtest_main",
    actual = "@com_google_googletest//:gtest_main",
)

alias(
    name = "gmock",
    actual = "@com_google_googletest//:gtest",
)

alias(
    name = "gmock_main",
    actual = "@com_google_googletest//:gtest_main",
)

alias(
    name = "vnames_config",
    actual = "@io_kythe//kythe/data:vnames_config",
)

alias(
    name = "libuuid",
    actual = "@io_kythe//third_party:libuuid",
)

alias(
    name = "libmemcached",
    actual = "@org_libmemcached_libmemcached//:libmemcached",
)

alias(
    name = "guava",  # required by @com_google_protobuf
    actual = "@io_kythe//third_party/guava",
)

alias(
    name = "gson",  # required by @com_google_protobuf
    actual = "@maven//:com_google_code_gson_gson",
)

alias(
    name = "zlib",  # required by @com_google_protobuf
    actual = "@net_zlib//:zlib",
)

# This binding is needed for protobuf. See https://github.com/protocolbuffers/protobuf/pull/5811
alias(
    name = "error_prone_annotations",
    actual = "@maven//:com_google_errorprone_error_prone_annotations",
)
