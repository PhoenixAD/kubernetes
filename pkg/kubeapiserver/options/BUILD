package(default_visibility = ["//visibility:public"])

load(
    "@io_bazel_rules_go//go:def.bzl",
    "go_library",
    "go_test",
)

go_library(
    name = "go_default_library",
    srcs = [
        "api_enablement.go",
        "authentication.go",
        "authorization.go",
        "cloudprovider.go",
        "options.go",
        "serving.go",
        "storage_versions.go",
    ],
    importpath = "k8s.io/kubernetes/pkg/kubeapiserver/options",
    deps = [
        "//pkg/api/legacyscheme:go_default_library",
        "//pkg/client/informers/informers_generated/internalversion:go_default_library",
        "//pkg/kubeapiserver/authenticator:go_default_library",
        "//pkg/kubeapiserver/authorizer:go_default_library",
        "//pkg/kubeapiserver/authorizer/modes:go_default_library",
        "//pkg/kubeapiserver/server:go_default_library",
        "//vendor/github.com/golang/glog:go_default_library",
        "//vendor/github.com/pborman/uuid:go_default_library",
        "//vendor/github.com/spf13/pflag:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/runtime/schema:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/util/net:go_default_library",
        "//vendor/k8s.io/apiserver/pkg/server:go_default_library",
        "//vendor/k8s.io/apiserver/pkg/server/options:go_default_library",
        "//vendor/k8s.io/apiserver/pkg/util/flag:go_default_library",
        "//vendor/k8s.io/client-go/informers:go_default_library",
    ],
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [":package-srcs"],
    tags = ["automanaged"],
)

go_test(
    name = "go_default_test",
    srcs = ["storage_versions_test.go"],
    embed = [":go_default_library"],
    importpath = "k8s.io/kubernetes/pkg/kubeapiserver/options",
    deps = ["//vendor/k8s.io/apimachinery/pkg/runtime/schema:go_default_library"],
)
