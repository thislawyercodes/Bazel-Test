package(
default_visibility = ["//src:__subpackages__"],
)
android_binary(
    name = "app",
    manifest = "AndroidManifest.xml",
    deps = ["//src/main/java/com/example/bazel:greeter_activity",
            "@maven//:com_google_android_material_material",
            "@maven//:org_robolectric_robolectric",
            "@maven//:androidx_test_espresso_espresso_core",
            ]
)

