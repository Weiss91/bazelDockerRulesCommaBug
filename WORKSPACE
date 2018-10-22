workspace(name = "test_env")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "io_bazel_rules_go",
    sha256 = "083bf2cd860225a5cc434a3297aad8d9035fc8b0db606498b49ade276fcd5582",
    strip_prefix = "rules_go-0.15.0",
    url = "https://github.com/bazelbuild/rules_go/archive/0.15.0.zip",
)

http_archive(
    name = "bazel_gazelle",
    sha256 = "d9cb7e3cbaea8efd7bd1c9e27d6aaed335acfbd27e4590bb344baa35032ec612",
    strip_prefix = "bazel-gazelle-0.14.0",
    url = "https://github.com/bazelbuild/bazel-gazelle/archive/0.14.0.zip",
)

http_archive(
    name = "io_bazel_rules_docker",
    sha256 = "b174fe76efb2dfbd0517d700f280ac8b14ea36aaa1342ac3cfa01ebb66d44ddf",
    strip_prefix = "rules_docker-0.5.1",
    url = "https://github.com/bazelbuild/rules_docker/archive/v0.5.1.zip",
)

load("@io_bazel_rules_go//go:def.bzl", "go_register_toolchains", "go_rules_dependencies")

go_rules_dependencies()

go_register_toolchains()

load("@io_bazel_rules_docker//go:image.bzl", go_image_repositories = "repositories")

go_image_repositories()

load("@bazel_gazelle//:deps.bzl", "gazelle_dependencies", "go_repository")

gazelle_dependencies()