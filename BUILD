load("//tools/bzl:plugin.bzl", "gerrit_plugin", "PLUGIN_DEPS", "PLUGIN_TEST_DEPS")
load("//tools/bzl:junit.bzl", "junit_tests")

gerrit_plugin(
    name = "automerge-plugin",
    srcs = glob(["src/main/java/**/*.java"]),
    manifest_entries = [
        "Gerrit-PluginName: automerge-plugin",
        "Gerrit-Module: com.criteo.gerrit.plugins.automerge.AutomergeModule",
    ],
    resources = glob(["src/main/resources/*"]),
)

junit_tests(
    name = "test",
    testonly = 1,
    srcs = glob(["src/test/java/**/*.java"]),
    deps = PLUGIN_DEPS + PLUGIN_TEST_DEPS + [
        ":automerge-plugin",
    ],
)
