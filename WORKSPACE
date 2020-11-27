workspace(name = "rules_foreign_cc_usage_example")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# Group the sources of the library so that CMake rule have access to it
all_content = """filegroup(name = "all", srcs = glob(["**"]), visibility = ["//visibility:public"])"""

# Rule repository
http_archive(
    name = "rules_foreign_cc",
    strip_prefix = "rules_foreign_cc-master",
    url = "https://github.com/bazelbuild/rules_foreign_cc/archive/master.tar.gz",
)

load("@rules_foreign_cc//:workspace_definitions.bzl", "rules_foreign_cc_dependencies")

rules_foreign_cc_dependencies()
#rules_foreign_cc_dependencies([
#    "@rules_foreign_cc//tools/build_defs:make_toolchain",
#    "@rules_foreign_cc//tools/build_defs:cmake_toolchain",
#    "@rules_foreign_cc//tools/build_defs:ninja_toolchain",
#])
