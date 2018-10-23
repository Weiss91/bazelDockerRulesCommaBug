# bazelDockerRulesCommaBug
Minimal working example for rules_docker env bug

To see the bug, run `bazel build image_test_bug`

output: 
```$ bazel build image_test_bug
INFO: Analysed target //:image_test_bug (1 packages loaded).
INFO: Found 1 target...
ERROR: /mnt/c/Users/matthias.weiss/go/src/github.com/weiss91/bazelDockerEnvBug/BUILD.bazel:21:1: ImageConfig image_test_bug.0.config failed (Exit 1)
Traceback (most recent call last):
  File "/home/matthias/.cache/bazel/_bazel_matthias/876a68a91054abbeffa7e92ef6acf28e/sandbox/processwrapper-sandbox/1/execroot/test_env/bazel-out/host/bin/external/io_bazel_rules_docker/container/create_image_config.runfiles/io_bazel_rules_docker/container/create_image_config.py", line 208, in <module>
    main()
  File "/home/matthias/.cache/bazel/_bazel_matthias/876a68a91054abbeffa7e92ef6acf28e/sandbox/processwrapper-sandbox/1/execroot/test_env/bazel-out/host/bin/external/io_bazel_rules_docker/container/create_image_config.runfiles/io_bazel_rules_docker/container/create_image_config.py", line 184, in main
    for (k, v) in six.iteritems(KeyValueToDict(args.env))
  File "/home/matthias/.cache/bazel/_bazel_matthias/876a68a91054abbeffa7e92ef6acf28e/sandbox/processwrapper-sandbox/1/execroot/test_env/bazel-out/host/bin/external/io_bazel_rules_docker/container/create_image_config.runfiles/io_bazel_rules_docker/container/create_image_config.py", line 95, in KeyValueToDict
    (k, v) = kv.split('=', 1)
ValueError: need more than 1 value to unpack
Target //:image_test_bug failed to build
Use --verbose_failures to see the command lines of failed build steps.
INFO: Elapsed time: 2.517s, Critical Path: 0.79s
INFO: 0 processes.
FAILED: Build did NOT complete successfully```
