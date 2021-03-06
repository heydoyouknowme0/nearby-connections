# Copyright 2020 Google LLC
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     https://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

cc_library(
    name = "internal",
    srcs = [
        "base_endpoint_channel.cc",
        "base_pcp_handler.cc",
        "ble_advertisement.cc",
        "ble_endpoint_channel.cc",
        "bluetooth_device_name.cc",
        "bluetooth_endpoint_channel.cc",
        "client_proxy.cc",
        "encryption_runner.cc",
        "endpoint_channel_manager.cc",
        "endpoint_manager.cc",
        "internal_payload.cc",
        "internal_payload_factory.cc",
        "offline_frames.cc",
        "offline_service_controller.cc",
        "p2p_cluster_pcp_handler.cc",
        "p2p_point_to_point_pcp_handler.cc",
        "p2p_star_pcp_handler.cc",
        "payload_manager.cc",
        "pcp_manager.cc",
        "service_controller_router.cc",
        "webrtc_endpoint_channel.cc",
        "wifi_lan_endpoint_channel.cc",
        "wifi_lan_service_info.cc",
    ],
    hdrs = [
        "base_endpoint_channel.h",
        "base_pcp_handler.h",
        "ble_advertisement.h",
        "ble_endpoint_channel.h",
        "bluetooth_device_name.h",
        "bluetooth_endpoint_channel.h",
        "client_proxy.h",
        "encryption_runner.h",
        "endpoint_channel.h",
        "endpoint_channel_manager.h",
        "endpoint_manager.h",
        "internal_payload.h",
        "internal_payload_factory.h",
        "offline_frames.h",
        "offline_service_controller.h",
        "p2p_cluster_pcp_handler.h",
        "p2p_point_to_point_pcp_handler.h",
        "p2p_star_pcp_handler.h",
        "payload_manager.h",
        "pcp.h",
        "pcp_handler.h",
        "pcp_manager.h",
        "service_controller.h",
        "service_controller_router.h",
        "webrtc_endpoint_channel.h",
        "wifi_lan_endpoint_channel.h",
        "wifi_lan_service_info.h",
    ],
    visibility = [
        "//core_v2:__pkg__",
    ],
    deps = [
        "//core/internal:message_lite",
        "//core_v2:core_types",
        "//core_v2/internal/mediums",
        "//core_v2/internal/mediums:utils",
        "//core_v2/internal/mediums/webrtc",
        "//proto/connections:offline_wire_formats_portable_proto",
        "//platform_v2/base",
        "//platform_v2/base:util",
        "//platform_v2/public:comm",
        "//platform_v2/public:logging",
        "//platform_v2/public:types",
        "//proto:connections_enums_portable_proto",
        "//securegcm:ukey2",
        "//absl/base:core_headers",
        "//absl/container:btree",
        "//absl/container:flat_hash_map",
        "//absl/container:flat_hash_set",
        "//absl/functional:bind_front",
        "//absl/memory",
        "//absl/strings",
        "//absl/time",
        "//absl/types:span",
    ],
)

cc_library(
    name = "internal_test",
    testonly = True,
    srcs = [
        "offline_simulation_user.cc",
        "simulation_user.cc",
    ],
    hdrs = [
        "mock_service_controller.h",
        "offline_simulation_user.h",
        "simulation_user.h",
    ],
    visibility = [
        "//core_v2:__subpackages__",
    ],
    deps = [
        ":internal",
        "//core_v2:core_types",
        "//platform_v2/base",
        "//platform_v2/base:test_util",
        "//platform_v2/public:types",
        "//testing/base/public:gunit",
        "//absl/functional:bind_front",
        "//absl/strings",
    ],
)

cc_test(
    name = "core_v2_internal_test",
    size = "small",
    timeout = "moderate",
    srcs = [
        "base_endpoint_channel_test.cc",
        "base_pcp_handler_test.cc",
        "ble_advertisement_test.cc",
        "bluetooth_device_name_test.cc",
        "client_proxy_test.cc",
        "encryption_runner_test.cc",
        "endpoint_channel_manager_test.cc",
        "endpoint_manager_test.cc",
        "internal_payload_factory_test.cc",
        "offline_frames_test.cc",
        "offline_service_controller_test.cc",
        "p2p_cluster_pcp_handler_test.cc",
        "payload_manager_test.cc",
        "pcp_manager_test.cc",
        "service_controller_router_test.cc",
        "wifi_lan_service_info_test.cc",
    ],
    shard_count = 16,
    deps = [
        ":internal",
        ":internal_test",
        "//core_v2:core_types",
        "//proto/connections:offline_wire_formats_portable_proto",
        "//platform_v2/base",
        "//platform_v2/base:test_util",
        "//platform_v2/impl/g3",  # build_cleaner: keep
        "//platform_v2/public:logging",
        "//platform_v2/public:types",
        "//proto:connections_enums_portable_proto",
        "//securegcm:ukey2",
        "//testing/base/public:gunit",
        "//testing/base/public:gunit_main",
        "//absl/container:flat_hash_set",
        "//absl/strings",
        "//absl/synchronization",
        "//absl/time",
        "//absl/types:span",
    ],
)
