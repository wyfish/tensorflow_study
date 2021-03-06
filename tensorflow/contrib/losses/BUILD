# Description:
#   contains parts of TensorFlow that are experimental or unstable and which are not supported.

load("//tensorflow:tensorflow.bzl", "py_test")

package(
    default_visibility = ["//tensorflow:__subpackages__"],
    licenses = ["notice"],  # Apache 2.0
)

exports_files(["LICENSE"])

py_library(
    name = "losses_py",
    srcs = [
        "__init__.py",
        "python/losses/__init__.py",
        "python/losses/loss_ops.py",
        "python/metric_learning/metric_loss_ops.py",
    ],
    srcs_version = "PY2AND3",
    deps = [
        ":metric_learning_py",
        "//tensorflow/contrib/framework:framework_py",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:control_flow_ops",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:logging_ops",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:nn",
        "//tensorflow/python:nn_ops",
        "//tensorflow/python:script_ops",
        "//tensorflow/python:sparse_ops",
        "//tensorflow/python:sparse_tensor",
        "//tensorflow/python:summary",
        "//tensorflow/python:util",
    ],
)

py_test(
    name = "loss_ops_test",
    srcs = glob(["python/losses/loss_ops_test.py"]),
    python_version = "PY2",
    srcs_version = "PY2AND3",
    deps = [
        ":losses_py",
        "//tensorflow/contrib/framework:framework_py",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:errors",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:init_ops",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:random_ops",
        "//tensorflow/python:random_seed",
        "//tensorflow/python:training",
        "//tensorflow/python:variable_scope",
        "//tensorflow/python:variables",
        "//third_party/py/numpy",
    ],
)

py_library(
    name = "metric_learning_py",
    srcs = [
        "python/metric_learning/__init__.py",
        "python/metric_learning/metric_loss_ops.py",
    ],
    srcs_version = "PY2AND3",
    deps = [
        "//tensorflow/python:array_ops",
        "//tensorflow/python:control_flow_ops",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:logging_ops",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:nn",
        "//tensorflow/python:script_ops",
        "//tensorflow/python:sparse_ops",
        "//tensorflow/python:sparse_tensor",
        "//tensorflow/python:summary",
        "//tensorflow/python:util",
    ],
)

py_test(
    name = "metric_loss_ops_test",
    size = "medium",
    srcs = [
        "python/metric_learning/metric_loss_ops_test.py",
    ],
    python_version = "PY2",
    shard_count = 4,
    srcs_version = "PY2AND3",
    deps = [
        ":metric_learning_py",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:nn",
        "//tensorflow/python:sparse_tensor",
        "//third_party/py/numpy",
    ],
)
