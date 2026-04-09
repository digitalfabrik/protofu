# ProtoFu-Builder
This is a fork of https://github.com/jtmcdole/protofu
The ProtoFu builder can be used within a flutter/dart build runner of your project.

## Example
```
pubspec.yaml:
  dev_dependencies:
    build_runner: ^2.13.1
    protofu:
      git:
        url: https://github.com/digitalfabrik/protofu_builder.git
    protoc_plugin: ^21.1.2
```

```
  build.yaml:
      builders:
        protofu:
          options:
            protobuf_version: "27.5"
            use_protoc_plugin_from_pubspec: true
            root_dir: "proto/"
            proto_paths:
              - "proto/"
            out_dir: "lib/proto"
            grpc: false
            precompile_protoc_plugin: true
```

# ProtoFu - let me compile that for you

ProtoFu exists to make working with protobufs easier. Gone are the days of downloading
`protoc` and the dart `protoc_plugin`. We make it easier to download and depend, compile,
and keeping track of other proto repositories (`googleapis` as an example).

**Note**: This is not an officially supported Google product

ProtoFu will (through `protobuf.yaml` configuration)

* Download the version of `protoc` you define or a sensible version.
* Download the version of `protoc_plugin`.
* Clone protobufs libraries from github - assuming you have git installed.
* Reference protobuf libraries in relative or absolute paths.
* Process your protobufs to discover their transitive dependencies.
* Compile all the protobufs into a configurable `lib/src/generated` folder.

At least, that's the hope.

Example runs:
[![asciicast](https://asciinema.org/a/512092.svg)](https://asciinema.org/a/512092)

Check out [protofu.yaml](example/protofu.yaml) for template yaml.

Eventual goal:

[x] `dart pub global activate protofu`
[x] `protofu` then helps you.



