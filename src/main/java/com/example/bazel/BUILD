load("@rules_jvm_external//:defs.bzl","maven_install", "artifact")
package(
default_visibility = ["//src:__subpackages__"],
)
android_library(
name = "greeter_activity",
srcs = [
"Greeter.java",
"MainActivity.java",
],
manifest = "AndroidManifest.xml",
resource_files = glob(["res/**"]),
)
android_library(
    name = "external_deps",
    deps= [
        "@maven//:com_google_android_material_material",
        "@maven//androidx_lifecycle_lifecycle_viewmodel",
        "@maven//:androidx_test_espresso_espresso_core",
                ],
)
android_local_test(
    name = "greeter_activity_test",
    srcs = ["GreeterTest.java"],
    manifest = "TestManifest.xml",
    test_class = "com.example.bazel.GreeterTest",
    deps = [
        ":greeter_activity",
        "@maven//:org_robolectric_robolectric",
        "@robolectric//bazel:android-all",
    ],
)


