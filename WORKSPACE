load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

rules_python_version = "0.10.0" # Latest @2022-07-07
http_archive(
    name = "rules_python",
    sha256 = "56dc7569e5dd149e576941bdb67a57e19cd2a7a63cc352b62ac047732008d7e1",
    strip_prefix = "rules_python-{}".format(rules_python_version),
    url = "https://github.com/bazelbuild/rules_python/archive/{}.tar.gz".format(rules_python_version),
)

load("@rules_python//python:pip.bzl", "pip_install")
load("@rules_python//python:repositories.bzl", "python_register_toolchains")

python_register_toolchains(
    name = "python3_9",
    python_version = "3.9",
)

load("@python3_9//:defs.bzl", "interpreter")
load("@rules_python//python:pip.bzl", "pip_parse")
load("@rules_python//python:pip.bzl", "pip_install")

pip_install(
    name = "qkeras_deps",
    requirements = "//:requirements.txt",
)
