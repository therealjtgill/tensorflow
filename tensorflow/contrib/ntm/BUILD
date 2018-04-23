# Description:
#   Contains ops to train linear models on top of TensorFlow.
#   APIs here are meant to evolve over time.

licenses(["notice"])  # Apache 2.0

exports_files(["LICENSE"])

package(default_visibility = ["//tensorflow:__subpackages__"])

# Need to include custom op library because this is a new op
load("//tensorflow:tensorflow.bzl", "tf_custom_op_py_library")
load("//tensorflow:tensorflow.bzl", "tf_py_test")

# Name the op-to-be-loaded
tf_custom_op_py_library(
    name = "ntm_py",
    srcs = ["__init__.py"] + glob(["python/ops/*.py"]),
    # Shared object files; I have none
    dso = [
#        ":python/ops/_gru_ops.so",
#        ":python/ops/_lstm_ops.so",
    ],
    # tensorflow.bzl says that is is an unused argument...
    kernels = [
#        ":all_ops",
#        ":all_kernels",
    ],
    srcs_version = "PY2AND3",
    visibility = ["//visibility:public"],
    # Need to weed through these?
    deps = [
#        ":benchmarking",
#        ":gru_ops",
#        ":lstm_ops",
#        "//tensorflow/contrib/compiler:compiler_py",
#        "//tensorflow/contrib/layers:layers_py",
#        "//tensorflow/contrib/util:util_py",
#        "//tensorflow/core:protos_all_py",
        "//tensorflow/python:array_ops",
#        "//tensorflow/python:clip_ops",
#        "//tensorflow/python:embedding_ops",
#        "//tensorflow/python:framework_for_generated_wrappers",
#        "//tensorflow/python:init_ops",
        "//tensorflow/python:gen_math_ops",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:nn_ops",
#        "//tensorflow/python:platform",
#        "//tensorflow/python:pywrap_tensorflow",
#        "//tensorflow/python:random_ops",
        "//tensorflow/python:rnn",
        "//tensorflow/python:rnn_cell",
        "//tensorflow/python:rnn_cell_impl",        
#        "//tensorflow/python:session",
#        "//tensorflow/python:training",
#        "//tensorflow/python:util",
        "//tensorflow/python:variable_scope",
        "//tensorflow/python:variables",
    ],
)

tf_py_test(
    name = "fused_rnn_cell_test",
    size = "small",
    srcs = ["python/kernel_tests/fused_rnn_cell_test.py"],
    additional_deps = [
        ":rnn_py",
        "//third_party/py/numpy",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:gradients",
        "//tensorflow/python:init_ops",
        "//tensorflow/python:platform_test",
        "//tensorflow/python:rnn",
        "//tensorflow/python:rnn_cell",
        "//tensorflow/python:variable_scope",
        "//tensorflow/python:variables",
    ],
)
