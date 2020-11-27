load("@rules_foreign_cc//tools/build_defs:cmake.bzl", "cmake_external")

filegroup(
    name = "all",
    srcs = glob([
	"CMakeLists.txt", "cmake/**", "include/**", "source/**",
	"test/**"
    ]),
    visibility = ["//visibility:public"]
)

cmake_external(
    name = "libunifex",
    cmake_options = [
	"-GNinja", "-v",
	"-DBUILD_TESTING=off",
        "-DUNIFEX_BUILD_EXAMPLES=off",
    ],
    make_commands = [
	#"cmake --build .",
        "ninja",
	"make install",
    ],
    # Values to be passed as -Dkey=value on the CMake command line;
    # here are serving to provide some CMake script configuration options
    cache_entries = {
	#"BUILD_TESTING": "off",
        #"UNIFEX_BUILD_EXAMPLES": "off",
        #"NOFORTRAN": "on",
        #"BUILD_WITHOUT_LAPACK": "no",
    },
    lib_source = ":all",

    # We are selecting the resulting static library to be passed in C/C++ provider
    # as the result of the build;
    # However, the cmake_external dependants could use other artefacts provided by the build,
    # according to their CMake script
    static_libraries = ["libunifex.a"],
)
