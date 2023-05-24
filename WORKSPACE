load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive", "http_file")

#############   GitOps   ###################


http_archive(
    name = "com_adobe_rules_gitops",
    sha256 = "83124a8056b1e0f555c97adeef77ec6dff387eb3f5bc58f212b376ba06d070dd",
    strip_prefix = "rules_gitops-0.17.2",
    urls = ["https://github.com/adobe/rules_gitops/archive/refs/tags/v0.17.2.tar.gz"],
)

http_archive(
    name = "io_bazel_rules_go",
    sha256 = "099a9fb96a376ccbbb7d291ed4ecbdfd42f6bc822ab77ae6f1b5cb9e914e94fa",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/rules_go/releases/download/v0.35.0/rules_go-v0.35.0.zip",
        "https://github.com/bazelbuild/rules_go/releases/download/v0.35.0/rules_go-v0.35.0.zip",
    ],
)

load("@io_bazel_rules_go//go:deps.bzl", "go_register_toolchains", "go_rules_dependencies")

go_rules_dependencies()

go_register_toolchains(version = "1.19.2")

load("@com_adobe_rules_gitops//gitops:deps.bzl", "rules_gitops_dependencies")

rules_gitops_dependencies()

load("@com_adobe_rules_gitops//gitops:repositories.bzl", "rules_gitops_repositories")

rules_gitops_repositories()

################   End GitOps    ################


#
# examples dependencies
#

load(
    "@io_bazel_rules_docker//go:image.bzl",
    go_image_repositories = "repositories",
)

go_image_repositories()


http_file(
    name = "bazel-remote-yaml",
    urls = ["https://raw.githubusercontent.com/buchgr/bazel-remote/master/examples/kubernetes.yml"],
)
