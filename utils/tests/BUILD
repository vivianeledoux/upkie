# -*- python -*-
#
# Copyright 2023 Inria

load("//tools/lint:lint.bzl", "add_lint_tests")
load("@pip_upkie//:requirements.bzl", "requirement")

package(default_visibility = ["//visibility:public"])

cc_test(
    name = "tests",
    srcs = glob([
        "*.cpp",
        "*.h",
    ]),
    deps = [
        "//utils:cpp",
        "@eigen",
        "@googletest//:main",
    ],
)

py_test(
    name = "clamp_test",
    srcs = ["clamp_test.py"],
    deps = [
        "//utils:clamp",
    ],
)

py_test(
    name = "pinocchio_test",
    srcs = ["pinocchio_test.py"],
    deps = [
        "//utils:pinocchio",
    ],
)

add_lint_tests()
