# Copyright 2017 The Bazel Authors. All rights reserved.
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

http_archive(
    name = "bazel_skylib",
    sha256 = "b5f6abe419da897b7901f90cbab08af958b97a8f3575b0d3dd062ac7ce78541f",
    strip_prefix = "bazel-skylib-0.5.0",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/bazel-skylib/archive/0.5.0.tar.gz",
        "https://github.com/bazelbuild/bazel-skylib/archive/0.5.0.tar.gz",
    ],
)

git_repository(
    name = "com_github_bazelbuild_bazel_integration_testing",
    commit = "55a6a70dbcc2cc7699ee715746fb1452788f8d3c",
    remote = "https://github.com/bazelbuild/bazel-integration-testing",
)

load("@com_github_bazelbuild_bazel_integration_testing//tools:repositories.bzl", "bazel_binaries")

bazel_binaries()

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

rules_go_tag = "0.13.0"

http_archive(
    name = "io_bazel_rules_go",
    sha256 = "ba79c532ac400cefd1859cbc8a9829346aa69e3b99482cd5a54432092cbc3933",
    urls = ["https://github.com/bazelbuild/rules_go/releases/download/{tag}/rules_go-{tag}.tar.gz".format(tag = rules_go_tag)],
)

load("@io_bazel_rules_go//go:def.bzl", "go_register_toolchains", "go_rules_dependencies")

go_rules_dependencies()

go_register_toolchains()

load("@bazel_gazelle//:deps.bzl", "gazelle_dependencies")

gazelle_dependencies()

git_repository(
    name = "io_bazel_rules_webtesting",
    commit = "c11e47ad49b90956b20c5b64ec1addea9a443096",
    remote = "https://github.com/bazelbuild/rules_webtesting.git",
)

load(
    "@io_bazel_rules_webtesting//web:repositories.bzl",
    "browser_repositories",
    "web_test_repositories",
)

web_test_repositories()

# Load repositories for example browser definitions.
# You should create your own browser definitions and link
# to the specific browser versions you are interested in
# testing with.
browser_repositories(
    chromium = True,
    sauce = True,
)

load("@bazel_gazelle//:deps.bzl", "go_repository")

go_repository(
    name = "com_github_fsnotify_fsnotify",
    commit = "7d7316ed6e1ed2de075aab8dfc76de5d158d66e1",
    importpath = "github.com/fsnotify/fsnotify",
)

go_repository(
    name = "com_github_jaschaephraim_lrserver",
    commit = "50d19f603f71e0a914f23eea33124ba9717e7873",
    importpath = "github.com/jaschaephraim/lrserver",
)

go_repository(
    name = "com_github_gorilla_websocket",
    commit = "7ca4275b84a9d500f68971c8c4a97f0ec18eb889",
    importpath = "github.com/gorilla/websocket",
)

go_repository(
    name = "org_golang_x_sys",
    commit = "99f16d856c9836c42d24e7ab64ea72916925fa97",
    importpath = "golang.org/x/sys",
)

go_repository(
    name = "com_github_bazelbuild_rules_go",
    importpath = "github.com/bazelbuild/rules_go",
    tag = rules_go_tag,
)

go_repository(
    name = "com_github_golang_protobuf",
    commit = "130e6b02ab059e7b717a096f397c5b60111cae74",
    importpath = "github.com/golang/protobuf",
)

go_repository(
    name = "com_github_gorilla_websocket",
    commit = "c55883f97322b4bcbf48f734e23d6ab3af1ea488",
    importpath = "github.com/gorilla/websocket",
)

go_repository(
    name = "com_github_tebeka_selenium",
    commit = "4bc91b5ff036f1cd12f315fd6042ecff6d94e512",
    importpath = "github.com/tebeka/selenium",
)

go_repository(
    name = "com_github_bazelbuild_rules_webtesting",
    commit = "ca7b8062d9cf4ef2fde9193c7d37a0764c4262d7",
    importpath = "github.com/bazelbuild/rules_webtesting",
)
