workspace(name = "multidim_image_augmentation")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# TensorFlow depends on "io_bazel_rules_closure" so we need this here.
# Needs to be kept in sync with the same target in TensorFlow's WORKSPACE file.
http_archive(
    name = "io_bazel_rules_closure",
    sha256 = "b29a8bc2cb10513c864cb1084d6f38613ef14a143797cea0af0f91cd385f5e8c",
    strip_prefix = "rules_closure-0.8.0",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/rules_closure/archive/0.8.0.tar.gz",
        "https://github.com/bazelbuild/rules_closure/archive/0.8.0.tar.gz",
    ],
)

# Tensorflow. If your project already builds Tensorflow source you should
# replace this with an appropriate local_archice() call.
# To update this to a newer TF version:
# 1/ curl -L https://github.com/tensorflow/tensorflow/archive/vX.Y.Z.tar | sha256sum
# 2/ Update `sha256`, `strip_prefix` and `urls` attributes appropriately.
# 3/ Update io_bazel_rules_closure above to match the version used by TF.
http_archive(
    name = "org_tensorflow",
    sha256 = "3c87b81e37d4ed7f3da6200474fa5e656ffd20d8811068572f43610cae97ca92",
    strip_prefix = "tensorflow-1.12.0",
    urls = [
        "https://mirror.bazel.build/github.com/tensorflow/tensorflow/archive/v1.12.0.tar.gz",
        "https://github.com/tensorflow/tensorflow/archive/v1.12.0.tar.gz",
    ],
)

# Please add all new multidim_image_augmentation dependencies in workspace.bzl.
load("//:workspace.bzl", "multidim_image_augmentation_workspace")

multidim_image_augmentation_workspace()

# Specify the minimum required bazel version.
load("@org_tensorflow//tensorflow:version_check.bzl", "check_bazel_version_at_least")

check_bazel_version_at_least("0.15.0")
