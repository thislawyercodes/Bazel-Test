load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")


android_sdk_repository(
    name = "androidsdk",
    path = "/home/akal/Android/Sdk",
    api_level = 32,
    build_tools_version = "30.0.3"
    )

RULES_JVM_EXTERNAL_TAG = "4.5"
RULES_JVM_EXTERNAL_SHA = "b17d7388feb9bfa7f2fa09031b32707df529f26c91ab9e5d909eb1676badd9a6"
#http_archive(
#     name = "robolectric",
#    urls = ["https://github.com/robolectric/robolectric-bazel/archive/4.9.2.tar.gz"],
#     strip_prefix = "robolectric-bazel-<COMMIT>",
#     sha256 = "7e007fcfdca7b7228cb4de72707e8b317026ea95000f963e91d5ae365be52d0d ",
# )
#load("@robolectric//bazel:robolectric.bzl", "robolectric_repositories")
#robolectric_repositories()

http_archive(
    name = "rules_jvm_external",
    strip_prefix = "rules_jvm_external-%s" % RULES_JVM_EXTERNAL_TAG,
    sha256 = RULES_JVM_EXTERNAL_SHA,
    url = "https://github.com/bazelbuild/rules_jvm_external/archive/%s.zip" % RULES_JVM_EXTERNAL_TAG,
)



load("@rules_jvm_external//:repositories.bzl", "rules_jvm_external_deps")
rules_jvm_external_deps()
load("@rules_jvm_external//:setup.bzl", "rules_jvm_external_setup")
rules_jvm_external_setup()

load("@rules_jvm_external//:defs.bzl", "maven_install")

maven_install(
    artifacts = [
        'com.google.android.material:material:1.0.0-alpha1',
        "org.robolectric:robolectric:4.9.2",
        "junit:junit:4.12",
        "androidx.test.espresso:espresso-core:3.1.1",
        "org.hamcrest:hamcrest-library:1.3",
    ],
    repositories = [
        "https://maven.google.com",
        "https://repo1.maven.org/maven2",
    ],
)