licenses(["notice"])

package(default_visibility = ["//visibility:public"])

cc_library(
    name = "bundle_to_seqex_converter",
    srcs = ["bundle_to_seqex_converter.cc"],
    hdrs = ["bundle_to_seqex_converter.h"],
    strip_include_prefix = "//cc/",
    deps = [
        ":example_key",
        ":feature_keys",
        ":resource_to_example",
        "//cc/google/fhir/status",
        "//cc/google/fhir/status:statusor",
        "//cc/google/fhir/stu3:bundle_to_versioned_resources_converter",
        "//cc/google/fhir/stu3:util",
        "//cc/google/fhir/systems",
        "//proto/stu3:annotations_cc_proto",
        "//proto/stu3:codes_cc_proto",
        "//proto/stu3:datatypes_cc_proto",
        "//proto/stu3:extensions_cc_proto",
        "//proto/stu3:resources_cc_proto",
        "//proto/stu3:version_config_cc_proto",
        "@com_google_absl//absl/strings",
        "@com_google_absl//absl/time",
        "@org_tensorflow//tensorflow/core:lib",
        "@org_tensorflow//tensorflow/core:protos_all_cc",
        "@protobuf_archive//:protobuf",
    ],
)

cc_test(
    name = "bundle_to_seqex_converter_test",
    srcs = ["bundle_to_seqex_converter_test.cc"],
    data = [
        "//proto/stu3:version_config.textproto",
    ],
    deps = [
        ":bundle_to_seqex_converter",
        ":example_key",
        "//cc/google/fhir/testutil:proto_matchers",
        "//proto/stu3:extensions_cc_proto",
        "//proto/stu3:resources_cc_proto",
        "@com_google_absl//absl/strings",
        "@com_google_googletest//:gtest_main",
        "@org_tensorflow//tensorflow/core:lib",
        "@org_tensorflow//tensorflow/core:protos_all_cc",
        "@protobuf_archive//:protobuf",
    ],
)

cc_library(
    name = "bundle_to_seqex_util",
    srcs = ["bundle_to_seqex_util.cc"],
    hdrs = ["bundle_to_seqex_util.h"],
    strip_include_prefix = "//cc/",
    deps = [
        "//cc/google/fhir/seqex:bundle_to_seqex_converter",
        "//cc/google/fhir/status:statusor",
        "//cc/google/fhir/stu3:extensions",
        "//cc/google/fhir/stu3:util",
        "//proto/stu3:datatypes_cc_proto",
        "//proto/stu3:extensions_cc_proto",
        "//proto/stu3:resources_cc_proto",
        "@com_google_absl//absl/time",
        "@org_tensorflow//tensorflow/core:lib",
        "@protobuf_archive//:protobuf",
    ],
)

cc_test(
    name = "bundle_to_seqex_util_test",
    srcs = ["bundle_to_seqex_util_test.cc"],
    deps = [
        ":bundle_to_seqex_util",
        "//cc/google/fhir/testutil:proto_matchers",
        "//proto/stu3:datatypes_cc_proto",
        "//proto/stu3:extensions_cc_proto",
        "@com_google_googletest//:gtest_main",
        "@protobuf_archive//:protobuf",
    ],
)

cc_library(
    name = "example_key",
    srcs = ["example_key.cc"],
    hdrs = ["example_key.h"],
    strip_include_prefix = "//cc/",
    deps = [
        "@com_google_absl//absl/memory",
        "@com_google_absl//absl/strings",
        "@com_google_absl//absl/time",
        "@com_googlesource_code_re2//:re2",
        "@org_tensorflow//tensorflow/core:lib",
    ],
)

cc_test(
    name = "example_key_test",
    srcs = ["example_key_test.cc"],
    deps = [
        ":example_key",
        "@com_google_googletest//:gtest_main",
    ],
)

cc_library(
    name = "feature_keys",
    srcs = ["feature_keys.cc"],
    hdrs = ["feature_keys.h"],
    strip_include_prefix = "//cc/",
)

cc_library(
    name = "resource_to_example",
    srcs = ["resource_to_example.cc"],
    hdrs = ["resource_to_example.h"],
    strip_include_prefix = "//cc/",
    deps = [
        ":text_tokenizer",
        "//cc/google/fhir/status",
        "//cc/google/fhir/stu3:util",
        "//cc/google/fhir/systems",
        "//proto/stu3:annotations_cc_proto",
        "//proto/stu3:datatypes_cc_proto",
        "@com_github_gflags_gflags//:gflags",
        "@com_google_absl//absl/algorithm:container",
        "@com_google_absl//absl/memory",
        "@com_google_absl//absl/strings",
        "@com_google_absl//absl/time",
        "@com_googlesource_code_re2//:re2",
        "@org_tensorflow//tensorflow/core:lib",
        "@org_tensorflow//tensorflow/core:protos_all_cc",
        "@protobuf_archive//:protobuf",
    ],
)

cc_test(
    name = "resource_to_example_test",
    srcs = ["resource_to_example_test.cc"],
    deps = [
        ":resource_to_example",
        "//cc/google/fhir/stu3:test_helper",
        "//cc/google/fhir/testutil:proto_matchers",
        "//proto/stu3:resources_cc_proto",
        "@com_github_gflags_gflags//:gflags",
        "@com_google_googletest//:gtest_main",
        "@org_tensorflow//tensorflow/core:lib",
        "@org_tensorflow//tensorflow/core:protos_all_cc",
        "@protobuf_archive//:protobuf",
    ],
)

cc_library(
    name = "text_tokenizer",
    srcs = ["text_tokenizer.cc"],
    hdrs = ["text_tokenizer.h"],
    strip_include_prefix = "//cc/",
    deps = [
        "@com_google_absl//absl/strings",
        "@com_googlesource_code_re2//:re2",
        "@org_tensorflow//tensorflow/core:lib",
    ],
)

cc_test(
    name = "text_tokenizer_test",
    srcs = ["text_tokenizer_test.cc"],
    deps = [
        ":text_tokenizer",
        "@com_google_absl//absl/strings",
        "@com_google_googletest//:gtest_main",
    ],
)
