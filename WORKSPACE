workspace(name = "TRTorch")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")

#git_repository(
#    name = "rules_python",
#    remote = "https://github.com/bazelbuild/rules_python.git",
#    commit = "4fcc24fd8a850bdab2ef2e078b1de337eea751a6",
#    shallow_since = "1589292086 -0400"
#)

#load("@rules_python//python:repositories.bzl", "py_repositories")
#py_repositories()

#load("@rules_python//python:pip.bzl", "pip_repositories", "pip3_import")
#pip_repositories()

http_archive(
    name = "rules_pkg",
    url = "https://github.com/bazelbuild/rules_pkg/releases/download/0.2.4/rules_pkg-0.2.4.tar.gz",
    sha256 = "4ba8f4ab0ff85f2484287ab06c0d871dcb31cc54d439457d28fd4ae14b18450a",
)

load("@rules_pkg//:deps.bzl", "rules_pkg_dependencies")
rules_pkg_dependencies()

# CUDA should be installed on the system locally
new_local_repository(
    name = "cuda",
    path = "/usr/local/cuda-10.2/targets/aarch64-linux/",
    build_file = "@//third_party/cuda:BUILD",
)

#http_archive(
#    name = "libtorch_pre_cxx11_abi",
#    build_file = "@//third_party/libtorch:BUILD",
#    strip_prefix = "libtorch",
#    sha256 = "ea8de17c5f70015583f3a7a43c7a5cdf91a1d4bd19a6a7bc11f074ef6cd69e27",
#    urls = ["https://download.pytorch.org/libtorch/cu102/libtorch-shared-with-deps-1.5.0.zip"],
#)

#http_archive(
#    name = "libtorch",
#    build_file = "@//third_party/libtorch:BUILD",
#    strip_prefix = "libtorch",
#    urls = ["https://download.pytorch.org/libtorch/cu102/libtorch-cxx11-abi-shared-with-deps-1.5.0.zip"],
#    sha256 = "0efdd4e709ab11088fa75f0501c19b0e294404231442bab1d1fb953924feb6b5"
#)

#pip3_import(
#    name = "trtorch_py_deps",
#    requirements = "//py:requirements.txt"
#)
#
#load("@trtorch_py_deps//:requirements.bzl", "pip_install")
#pip_install()

#pip3_import(
#    name = "py_test_deps",
#    requirements = "//tests/py:requirements.txt"
#)

#load("@py_test_deps//:requirements.bzl", "pip_install")
#pip_install()

# Locally installed dependencies
new_local_repository(
   name = "libtorch",
   path = "/home/jetson-nano/.local/lib/python3.6/site-packages/torch/",
   build_file = "@//third_party/libtorch:BUILD"
)


new_local_repository(
    name = "cudnn",
    path = "/usr/",
    build_file = "@//third_party/cudnn/local:BUILD"
)

new_local_repository(
   name = "tensorrt",
   path = "/usr/",
   build_file = "@//third_party/tensorrt/local:BUILD"
)

git_repository(
    name = "googletest",
    remote = "https://github.com/google/googletest",
    commit = "703bd9caab50b139428cea1aaff9974ebee5742e",
    shallow_since = "1570114335 -0400"
)
