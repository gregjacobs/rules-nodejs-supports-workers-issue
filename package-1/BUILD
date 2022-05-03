load("@npm//@bazel/typescript:index.bzl", "ts_project")

ts_project(
    name = "tsc",
    tsconfig = "tsconfig.json",
    srcs = ["index.ts"],
    source_map = True,
    declaration = True,
    supports_workers = True
)
