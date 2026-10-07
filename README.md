NVIDIA DeepStream SDK for Rust
=====

[LICENSE (MIT)](LICENSE)

## Notice

* WIP
* Currently, Target SDK Version is 6.2

## How to use

* Define in Cargo.toml

```toml
[dependencies]

nvidia-deepstream = { git="https://github.com/aosoft/nvidia-deepstream-rs", features = ["all"] }
```

### features

`nvidia-deepstream-sys` always links `nvbufsurface`. It uses `DEEPSTREAM_PATH`
(default `/opt/nvidia/deepstream/deepstream`) for both headers and the library
search path. The `surface` feature enables the Rust wrappers, not native linking.

| feature name      | header file          | linking dylib           |
|-------------------|----------------------|-------------------------|
| logger            | nvds_logger.h        | nvds_logger             |
| meta              | nvdsmeta.h           | nvdsgst_meta, nvds_meta |
| obj_encode        | nvds_obj_encode.h    | nvds_batch_jpegenc      |
| surface           | nvbufsurface.h       | nvbufsurface (always linked by sys) |
| surface_transform | nvbufsurftransform.h | nvbufsurftransform      |
| utils             | nvds_version.h       | nvds_utils              |
| yaml              | nvds_yml_parser.h    | nvds_yml_parser         |
