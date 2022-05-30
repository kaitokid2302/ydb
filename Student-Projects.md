Below is the list of tasks that are good for student projects (course or graduate work).

## SDK
### Support for Coordination service in Go SDK
YDB has a Coordination Service which allow your client application to elect a leader via distributed lock (similar to ZooKeeper). The task is to add support for Coordination Service to Go SDK.

Mentor: Aleksei Miasnikov 

### Support for sqlx.StructScan() in Go SDK
Add support for sqlx.StructScan() from github.com/jmoiron/sqlx to Go SDK.

Mentor: Aleksei Miasnikov

### Implement Plugin Mechanism in C++ SDK
Add capability of loading plugins implemented via so/dll into C++ SDK.

Example: YDB supports different authorisation mechanisms, it's a good idea to implement them as plugins to keep code dependancies clear.

Mentor:Daniil Cherednik

### Extend C++ SDK Monitoring
Out of the box monitoring for you client application is awesome. We have some ideas how to extend C++ SDK Monitoring facilities.

**TODO: detailed description**

Mentor:Daniil Cherednik

### Safe Shutdown in C++ SDK
**TODO: detailed description**

Mentor:Daniil Cherednik

## YDB CLI (Command Line Interface)
### Implement Interactive CLI
Currently YDB CLI (https://ydb.tech/en/docs/getting_started/cli) doesn't support interactive mode. Interactive mode means that you can run the `ydb` program and it will provide you a way to write queries and get responses something like the `psql` program does.

Mentor: Nikolay Perfilov

## Extend `ydb import file` Capabilities
**TODO: detailed description**

Mentor: Artem Zuikov

## YDB Core (C++)
### Optimize TEvVPut/TEvVGet message serialization
If you want to dive into YDB's core, this is the task you are looking for. Writing and reading from/to YDB Distributed Storage (DS) effectively is very important. For every write to DS YDB's component dsproxy generates several messages TEvVPut (https://github.com/ydb-platform/ydb/blob/main/ydb/core/blobstorage/vdisk/common/vdisk_events.h#L504) because we write multiple replicas or erasure parts. TEvVPut message is serialised to go into the wire. The task is to optimize TEvVPut serialization. Currently we use Google protobuf for message serialization, but options are:
1. Use google protobuf for metadata serialization only, but don't put opaque data into proto message. Put it next after protobuf message;
2. Use flat buffers;
3. Use custom protocol.
We expect that you think propose some solutions, implement them and compare performance via benchmark.

Mentor: Aleksey Stankevichus

### Add Traces to YDB Core
YDB uses lwtrace library for tracing events in the system and to debug issues.

**TODO: 1. add traces to components; 2. add support for open telemetry.**

Mentor: Aleksey Stankevichus


