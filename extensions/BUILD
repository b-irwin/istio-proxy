# Copyright 2019 Istio Authors. All Rights Reserved.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#    http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#
################################################################################
#

load(
    "@envoy//bazel/wasm:wasm.bzl",
    "wasm_cc_binary",
)
load(
    "@envoy//bazel:envoy_build_system.bzl",
    "envoy_package",
)

envoy_package()

wasm_cc_binary(
    name = "stats.wasm",
    srcs = [
        "//extensions/common:context.cc",
        "//extensions/common:context.h",
        "//extensions/common:util.cc",
        "//extensions/common:util.h",
        "//extensions/stats:plugin.cc",
        "//extensions/stats:plugin.h",
    ],
    copts = ["-UNULL_PLUGIN"],
    deps = [
        "//extensions/common:json_util_wasm",
        "//extensions/common:node_info_fb_cc",
        "//external:abseil_strings",
        "//external:abseil_time",
        "@proxy_wasm_cpp_sdk//:proxy_wasm_intrinsics",
        "@proxy_wasm_cpp_sdk//contrib:contrib_lib",
    ],
)

wasm_cc_binary(
    name = "metadata_exchange.wasm",
    srcs = [
        "//extensions/common:context.cc",
        "//extensions/common:context.h",
        "//extensions/common:proto_util.cc",
        "//extensions/common:proto_util.h",
        "//extensions/common:util.cc",
        "//extensions/common:util.h",
        "//extensions/metadata_exchange:base64.h",
        "//extensions/metadata_exchange:plugin.cc",
        "//extensions/metadata_exchange:plugin.h",
    ],
    copts = ["-UNULL_PLUGIN"],
    deps = [
        "//extensions/common:json_util_wasm",
        "//extensions/common:node_info_fb_cc",
        "//extensions/metadata_exchange:declare_property_proto_cc",
        "//external:abseil_strings",
        "//external:abseil_time",
        "@proxy_wasm_cpp_sdk//:proxy_wasm_intrinsics_full",
        "@proxy_wasm_cpp_sdk//contrib:contrib_lib",
    ],
)

wasm_cc_binary(
    name = "attributegen.wasm",
    srcs = [
        "//extensions/attributegen:plugin.cc",
        "//extensions/attributegen:plugin.h",
        "//extensions/common:context.cc",
        "//extensions/common:context.h",
        "//extensions/common:util.cc",
        "//extensions/common:util.h",
    ],
    copts = ["-UNULL_PLUGIN"],
    deps = [
        "//extensions/attributegen:config_cc_proto",
        "//extensions/common:json_util_wasm",
        "//extensions/common:node_info_fb_cc",
        "//external:abseil_strings",
        "//external:abseil_time",
        "@proxy_wasm_cpp_sdk//:proxy_wasm_intrinsics_full",
        "@proxy_wasm_cpp_sdk//contrib:contrib_lib",
    ],
)