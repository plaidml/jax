load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")

# To update TensorFlow to a new revision,
# a) update URL and strip_prefix to the new git commit hash
# b) get the sha256 hash of the commit by running:
#    curl -L https://github.com/tensorflow/tensorflow/archive/<git hash>.tar.gz | sha256sum
#    and update the sha256 with the result.
#http_archive(
#    name = "org_tensorflow",
#    sha256 = "6b14b66a74728736359afcb491820fa3e713ea4a74bff0defe920f3453a3a0f0",
#    strip_prefix = "tensorflow-b5b1ff47ad250c3e38dcadef5f6bc414b0a533ee",
#    urls = [
#        "https://github.com/tensorflow/tensorflow/archive/b5b1ff47ad250c3e38dcadef5f6bc414b0a533ee.tar.gz",
#    ],
#)

git_repository(
    name = "org_tensorflow",
    branch = "nhasabni/tf-xla-plaidml-llvm_commit_4c1023b4b",
    remote = "https://github.com/plaidml/tensorflow.git",
)

# For development, one can use a local TF repository instead.
# local_repository(
#    name = "org_tensorflow",
#    path = "tensorflow",
# )

load("//third_party/pocketfft:workspace.bzl", pocketfft = "repo")
pocketfft()

# Initialize TensorFlow's external dependencies.
load("@org_tensorflow//tensorflow:workspace3.bzl", "tf_workspace3")
tf_workspace3()

load("@org_tensorflow//tensorflow:workspace2.bzl", "tf_workspace2")
tf_workspace2()

load("@org_tensorflow//tensorflow:workspace1.bzl", "tf_workspace1")
tf_workspace1()

load("@org_tensorflow//tensorflow:workspace0.bzl", "tf_workspace0")
tf_workspace0()
