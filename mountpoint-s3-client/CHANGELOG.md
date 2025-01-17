## v0.4.0 (September 26, 2023)

### Breaking changes

* The crate has been reorganized to avoid exposing every type at the top level. See the [crate documentation](https://docs.rs/mountpoint-s3-client/) for more details. ([#511](https://github.com/awslabs/mountpoint-s3/pull/511))
* Some errors, notably `403 Forbidden`, that were previously handled by individual requests are now handled by shared logic, and may be returned differently ([#413](https://github.com/awslabs/mountpoint-s3/pull/413))
* `ListObjectsResult` no longer includes the `bucket` field ([#470](https://github.com/awslabs/mountpoint-s3/pull/470))

### Other changes

* `list_objects` and `head_object` results now include the storage class and restore status of an object if available ([#406](https://github.com/awslabs/mountpoint-s3/pull/406), [#467](https://github.com/awslabs/mountpoint-s3/pull/467))
* `put_object` now supports configuring trailing checksums ([#320](https://github.com/awslabs/mountpoint-s3/pull/320))
* A new `review_and_complete` method on `PutObjectRequest` can be used to inspect the parts of a multi-part upload before completing it ([#367](https://github.com/awslabs/mountpoint-s3/pull/367))

## v0.3.0 (June 20, 2023)

Breaking changes:

* Use CRT's new asynchronous streaming APIs for `put_object` requests ([#282](https://github.com/awslabs/mountpoint-s3/pull/298), [#295](https://github.com/awslabs/mountpoint-s3/pull/295)). This change modifies the `put_object` API.

Other changes:

* Avoid using CRT auto-ranged-get infrastructure for small requests ([#285](https://github.com/awslabs/mountpoint-s3/pull/285))
* Add `NoSuchBucket` error for `head_object` requests ([#273](https://github.com/awslabs/mountpoint-s3/pull/273))
* Fix a bug in computing time-to-first-byte for per-request telemetry ([#275](https://github.com/awslabs/mountpoint-s3/pull/275))

## v0.2.2 (May 31, 2023)

* Fix a build failure when consuming this crate from outside a Git repository ([(#269](https://github.com/awslabs/mountpoint-s3/pull/269))
* Include `mountpoint-s3-client` version in `User-agent` strings ([#266](https://github.com/awslabs/mountpoint-s3/pull/266))
* Integrate per-request telemetry for S3 requests ([#261](https://github.com/awslabs/mountpoint-s3/pull/261))

## v0.2.1 (May 26, 2023)

Initial release.