load("@com_adobe_rules_gitops//gitops:defs.bzl", "k8s_deploy")

package(default_visibility = ["//visibility:public"])

CLUSTER = "k3d-k3s-default"
USER = "admin@k3d-k3s-default"

k8s_deploy(
    name = "mynamespace",
    cluster = CLUSTER,
    manifests = [
        "namespace.yaml",
    ],
    namespace = "{BUILD_USER}",
    user = USER,
)
