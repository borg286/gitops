load("@com_adobe_rules_gitops//gitops:defs.bzl", "k8s_deploy")

CLUSTER = "k3d-k3s-default"
USER = "admin@k3d-k3s-default"

k8s_deploy(
    name = "bazel-remote",
    cluster = CLUSTER,
    manifests = [
        "deployment.yaml",
        "service.yaml",
    ],
    gitops = False,
    user = USER,
    namespace = "default",
)