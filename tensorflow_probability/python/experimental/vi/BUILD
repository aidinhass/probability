# Copyright 2019 The TensorFlow Probability Authors.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
# ============================================================================
# Description:
#   Experimental methods and objectives for variational inference.

licenses(["notice"])

package(
    default_visibility = [
        "//tensorflow_probability:__subpackages__",
    ],
)

exports_files(["LICENSE"])

py_library(
    name = "vi",
    srcs = ["__init__.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":surrogate_posteriors",
        "//tensorflow_probability/python/internal:all_util",
    ],
)

py_library(
    name = "parameter_constraints",
    srcs = ["parameter_constraints.py"],
    srcs_version = "PY2AND3",
    deps = [
        # tensorflow dep,
        "//tensorflow_probability/python/bijectors",
    ],
)

py_library(
    name = "surrogate_posteriors",
    srcs = ["surrogate_posteriors.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":parameter_constraints",
        # numpy dep,
        # tensorflow dep,
        "//tensorflow_probability/python/distributions",
        "//tensorflow_probability/python/internal:nest_util",
        "//tensorflow_probability/python/internal:prefer_static",
        "//tensorflow_probability/python/monte_carlo",
    ],
)

py_test(
    name = "surrogate_posteriors_test",
    size = "large",
    srcs = ["surrogate_posteriors_test.py"],
    python_version = "PY3",
    shard_count = 5,
    srcs_version = "PY3",
    deps = [
        # absl/testing:parameterized dep,
        # numpy dep,
        # tensorflow dep,
        "//tensorflow_probability",
        "//tensorflow_probability/python/internal:test_util",
    ],
)
