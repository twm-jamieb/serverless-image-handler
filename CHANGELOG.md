# Change Log

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [6.2.4] - 2023-12-06

### Changed

- node 20.x Lambda runtimes
- cdk update to 2.111.0
- disable gzip compression in cloudfront cache option to improve cache hit ratio [#373](https://github.com/aws-solutions/serverless-image-handler/pull/373)
- requests for webp images supported for upper/lower case Accept header [#490](https://github.com/aws-solutions/serverless-image-handler/pull/490)
- changed axios version to 1.6.2 for github dependabot reported vulnerability CVE-2023-45857
- enabled thumbor filter chaining [#343](https://github.com/aws-solutions/serverless-image-handler/issues/343)

## [6.2.3] - 2023-10-20

### Fixed

- Fixing Security Vulnerabilities

### Changed

- Updated the versions of multiple dependencies

## [6.2.2] - 2023-09-29

### Changed

- Update package.json Author
- Modify some license headers to maintain consistency

### Security

- Upgraded sharp to v0.32.6 for vulnerability CVE-2023-4863
- Upgraded outdated NPM packages

## [6.2.1] - 2023-08-03

### Fixed

- Template fails to deploy unless demo UI is enabled [#499](https://github.com/aws-solutions/serverless-image-handler/issues/499)
- Thumbor requests of images without a file extension would fail
- CloudFormation template description was not being generated

### Changed

- Upgraded build requirement to Node 16

## [6.2.0] - 2023-08-01

### Added

- Add `cdk-helper` module to help with packaging cdk generated assets in solutions internal pipelines
- Use [DefaultStackSynthesizer](https://docs.aws.amazon.com/cdk/api/v2/docs/aws-cdk-lib.DefaultStackSynthesizer.html) with different configurations to generate template for `cdk deploy` and on internal solutions pipeline
- Add esbuild bundler for lambda functions using `NodejsFunction`, reference [aws_lambda_nodejs](https://docs.aws.amazon.com/cdk/api/v2/docs/aws-cdk-lib.aws_lambda_nodejs-readme.html)
- Refactor pipeline scripts
- Changes semver dependency version to 7.5.2 for github reported vulnerability CVE-2022-25883
- Changes word-wrap dependency version to aashutoshrathi/word-wrap for github reported vulnerability CVE-2023-26115

## [6.1.2] - 2023-04-14

### Changed

- added s3 bucket ownership control permission and ownership parameter to S3 logging bucket to account for [changes in S3 default behavior](https://docs.aws.amazon.com/AmazonS3/latest/userguide/create-bucket-faq.html)
- changed xml2js version to 0.5.0 for github dependabot reported vulnerability CVE-2023-0842

## [6.1.1] - 2023-02-09

### Added

- package-lock.json for all modules [#426](https://github.com/aws-solutions/serverless-image-handler/pull/426)
- github workflows for running unit test, eslint and prettier formatting, cdk nag, security scans [#402](https://github.com/aws-solutions/serverless-image-handler/pull/402)
- demo-ui unicode support [#416](https://github.com/aws-solutions/serverless-image-handler/issues/416)
- support for multiple cloudformation stack deployments in the same region [#438](https://github.com/aws-solutions/serverless-image-handler/pull/438)

### Changed

- axios version update to 1.2.3 [#425](https://github.com/aws-solutions/serverless-image-handler/pull/425)
- json5 version update to 1.0.2 [#428](https://github.com/aws-solutions/serverless-image-handler/pull/428)
- CodeQL advisory resolutions
- contributing guidelines

## [6.1.0] - 2022-11-10

### Added

- gif support
- tif support
- AWS Service Catalog AppRegistry

### Changed

- package version updates
- CDK v2 migration
- node 16.x Lambda runtimes

## [6.0.0] - 2021-12-21

### Changed

- **Note that** Version 6.0.0 does not support upgrading from previous versions due to the update that uses the AWS CDK to generate the AWS CloudFormation template.

### Added

- Crop feature in Thumbor URLs: [#202](https://github.com/aws-solutions/serverless-image-handler/pull/202)
- TypeScript typings: [#293](https://github.com/aws-solutions/serverless-image-handler/issues/293)
- Reduction effort support: [#289](https://github.com/aws-solutions/serverless-image-handler/issues/289)
- Allow custom requests for keys without file extensions: [#273](https://github.com/aws-solutions/serverless-image-handler/issues/273)

### Fixed

- Unexpected behavior after adding support for images without extension: [#307](https://github.com/aws-solutions/serverless-image-handler/issues/307)
- Quality filter does not work with format filter (thumbor): [#266](https://github.com/aws-solutions/serverless-image-handler/issues/266)
- Auto WebP activated, `Content-Type: image/webp` returned, but still it's JPG encoded: [#305](https://github.com/aws-solutions/serverless-image-handler/issues/305)
- `inferImageType` doesn't support binary/octet-stream but not application/octet-stream: [#306](https://github.com/aws-solutions/serverless-image-handler/issues/306)
- SmartCrop boundary exceeded: [#263](https://github.com/aws-solutions/serverless-image-handler/issues/263)
- Custom rewrite does not work without file extensions: [#268](https://github.com/aws-solutions/serverless-image-handler/issues/268)
- Secrets manager cost issue: [#291](https://github.com/aws-solutions/serverless-image-handler/issues/291)
- `inferImageType` is slow: [#303](https://github.com/aws-solutions/serverless-image-handler/issues/303)
- If the file name contain `()`，the API will return 404,NoSuchKey,The specified key does not exist: [#299](https://github.com/aws-solutions/serverless-image-handler/issues/299)
- `fit-in` segment in URL path generates 404: [#281](https://github.com/aws-solutions/serverless-image-handler/issues/281)
- `overlayWith` top/left return int after percent conversion: [#276](https://github.com/aws-solutions/serverless-image-handler/issues/276)

## [5.2.0] - 2021-01-29

### Added

- Support for ap-east-1 and me-south-1 regions: [#192](https://github.com/aws-solutions/serverless-image-handler/issues/192), [#228](https://github.com/aws-solutions/serverless-image-handler/issues/228), [#232](https://github.com/aws-solutions/serverless-image-handler/issues/232)
- Unit tests for custom-resource: `100%` coverage
- Cloudfront cache policy and origin request policy: [#229](https://github.com/aws-solutions/serverless-image-handler/issues/229)
- Circular cropping feature: [#214](https://github.com/aws-solutions/serverless-image-handler/issues/214), [#216](https://github.com/aws-solutions/serverless-image-handler/issues/216)
- Unit tests for image-handler: `100%` coverage
- Support for files without extension on thumbor requests: [#169](https://github.com/aws-solutions/serverless-image-handler/issues/169), [#188](https://github.com/aws-solutions/serverless-image-handler/issues/188)
- Inappropriate content detection feature: [#243](https://github.com/aws-solutions/serverless-image-handler/issues/243)
- Unit tests for image-request: `100%` coverage

### Fixed

- Graceful failure when no faces are detected using smartCrop and fail on resizing before smartCrop: [#132](https://github.com/aws-solutions/serverless-image-handler/issues/132), [#133](https://github.com/aws-solutions/serverless-image-handler/issues/133)
- Broken SVG returned if no edits specified and Auto-WebP enabled: [#247](https://github.com/aws-solutions/serverless-image-handler/issues/247)
- Removed "--recursive" from README.md: [#255](https://github.com/aws-solutions/serverless-image-handler/pull/255)
- fixed issue with failure on resize if width or height is float: [#254](https://github.com/aws-solutions/serverless-image-handler/issues/254)

### Changed

- Constructs test template for constructs unit test: `100%` coverage

## [5.1.0] - 2020-11-19

### Added

- Image URL signature: [#111](https://github.com/aws-solutions/serverless-image-handler/issues/111), [#203](https://github.com/aws-solutions/serverless-image-handler/issues/203), [#221](https://github.com/aws-solutions/serverless-image-handler/issues/221), [#227](https://github.com/aws-solutions/serverless-image-handler/pull/227)
- AWS Lambda `413` error handling. When the response payload is bigger than 6MB, it throws `TooLargeImageException`: [#35](https://github.com/aws-solutions/serverless-image-handler/issues/35), [#97](https://github.com/aws-solutions/serverless-image-handler/issues/97), [#193](https://github.com/aws-solutions/serverless-image-handler/issues/193), [#204](https://github.com/aws-solutions/serverless-image-handler/issues/204)
- Default fallback image: [#137](https://github.com/aws-solutions/serverless-image-handler/issues/137)
- Unit tests for custom resource: `100%` coverage
- Add `SVG` support. When any edits are used, the output would be automatically `PNG` unless the output format is specified: [#31](https://github.com/aws-solutions/serverless-image-handler/issues/31), [#234](https://github.com/aws-solutions/serverless-image-handler/issues/234)
- Custom headers: [#182](https://github.com/aws-solutions/serverless-image-handler/pull/182)
- Enabling ALB Support : [#201](https://github.com/aws-solutions/serverless-image-handler/pull/201)

### Fixed

- Thumbor paths broken if they include "-" and "100x100": [#208](https://github.com/aws-solutions/serverless-image-handler/issues/208)
- Rewrite doesn't seem to be working: [#121](https://github.com/aws-solutions/serverless-image-handler/issues/121)
- Correct EXIF: [#197](https://github.com/aws-solutions/serverless-image-handler/issues/197), [#220](https://github.com/aws-solutions/serverless-image-handler/issues/220), [#235](https://github.com/aws-solutions/serverless-image-handler/issues/235), [#236](https://github.com/aws-solutions/serverless-image-handler/issues/236), [#240](https://github.com/aws-solutions/serverless-image-handler/issues/240)
- Sub folder support in Thumbor `watermark` filter: [#231](https://github.com/aws-solutions/serverless-image-handler/issues/231)

### Changed

- AWS CDK and AWS Solutions Constructs version (from 1.57.0 to 1.64.1)
- sharp base version (from 0.25.4 to 0.26.1)
- Refactors the custom resource Lambda source code
- Migrate unit tests to use `jest`
- Move all `aws-sdk` in `ImageHandler` Lambda function to `index.js` for the best practice
- Enhance the default error message not to show empty JSON: [#206](https://github.com/aws-solutions/serverless-image-handler/issues/206)
- **Image URL Signature**: When image URL signature is enabled, all URLs including existing URLs should have `signature` query parameter.

### Removed

- Remove `manifest-generator`

## [5.0.0] - 2020-08-31

### Added

- AWS CDK and AWS Solutions Constructs to create AWS CloudFormation template

### Fixed

- Auto WebP does not work properly: [#195](https://github.com/aws-solutions/serverless-image-handler/pull/195), [#200](https://github.com/aws-solutions/serverless-image-handler/issues/200), [#205](https://github.com/aws-solutions/serverless-image-handler/issues/205)
- A bug where base64 encoding containing slash: [#194](https://github.com/aws-solutions/serverless-image-handler/pull/194)
- Thumbor issues:
  - `0` size support: [#183](https://github.com/aws-solutions/serverless-image-handler/issues/183)
  - `convolution` filter does not work: [#187](https://github.com/aws-solutions/serverless-image-handler/issues/187)
  - `fill` filter does not work: [#190](https://github.com/aws-solutions/serverless-image-handler/issues/190)
- **Note that** duplicated features has been merged gracefully.

### Removed

- AWS CloudFormation template: `serverless-image-handler.template`

### Changed

- sharp base version (from 0.23.4 to 0.25.4)
- Remove `Promise` to return since `async` functions return promises: [#189](https://github.com/aws-solutions/serverless-image-handler/issues/189)
- Unit test statement coverage improvement:
  - `image-handler.js`: `79.05%` to `100%`
  - `image-request.js`: `93.58%` to `100%`
  - `thumbor-mapping.js`: `99.29%` to `100%`
  - `overall`: `91.55%` to `100%`

## [4.2.0] - 2020-02-06

### Added

- Honor outputFormat Parameter from the pull request [#117](https://github.com/aws-solutions/serverless-image-handler/pull/117)
- Support serving images under s3 subdirectories, Fix to make /fit-in/ work; Fix for VipsJpeg: Invalid SOS error plus several other critical fixes from the pull request [#130](https://github.com/aws-solutions/serverless-image-handler/pull/130)
- Allow regex in SOURCE_BUCKETS for environment variable from the pull request [#138](https://github.com/aws-solutions/serverless-image-handler/pull/138)
- Fix build script on other platforms from the pull request [#139](https://github.com/aws-solutions/serverless-image-handler/pull/139)
- Add Cache-Control response header from the pull request [#151](https://github.com/aws-solutions/serverless-image-handler/pull/151)
- Add AUTO_WEBP option to automatically serve WebP if the client supports it from the pull request [#152](https://github.com/aws-solutions/serverless-image-handler/pull/152)
- Use HTTP 404 & forward Cache-Control, Content-Type, Expires, and Last-Modified headers from S3 from the pull request [#158](https://github.com/aws-solutions/serverless-image-handler/pull/158)
- fix: DeprecationWarning: Buffer() is deprecated from the pull request [#174](https://github.com/aws-solutions/serverless-image-handler/pull/174)
- Add hex color support for Thumbor `filters:background_color` and `filters:fill` [#154](https://github.com/aws-solutions/serverless-image-handler/issues/154)
- Add format and watermark support for Thumbor [#109](https://github.com/aws-solutions/serverless-image-handler/issues/109), [#131](https://github.com/aws-solutions/serverless-image-handler/issues/131), [#109](https://github.com/aws-solutions/serverless-image-handler/issues/142)
- **Note that** duplicated features has been merged gracefully.

### Changed

- sharp base version (from 0.23.3 to 0.23.4)
- Image handler Amazon CloudFront distribution `DefaultCacheBehavior.ForwardedValues.Header` to `["Origin", "Accept"]` for WebP
- Image resize process change for `filters:no_upscale()` handling by `withoutEnlargement` edit key [#144](https://github.com/aws-solutions/serverless-image-handler/issues/144)

### Fixed

- Add and fix Cache-control, Content-Type, Expires, and Last-Modified headers to response: [#103](https://github.com/aws-solutions/serverless-image-handler/issues/103), [#107](https://github.com/aws-solutions/serverless-image-handler/issues/107), [#120](https://github.com/aws-solutions/serverless-image-handler/issues/120)
- Fix Amazon S3 bucket subfolder issue: [#106](https://github.com/aws-solutions/serverless-image-handler/issues/106), [#112](https://github.com/aws-solutions/serverless-image-handler/issues/112), [#119](https://github.com/aws-solutions/serverless-image-handler/issues/119), [#123](https://github.com/aws-solutions/serverless-image-handler/issues/123), [#167](https://github.com/aws-solutions/serverless-image-handler/issues/167), [#175](https://github.com/aws-solutions/serverless-image-handler/issues/175)
- Fix HTTP status code for missing images from 500 to 404: [#159](https://github.com/aws-solutions/serverless-image-handler/issues/159)
- Fix European character in filename issue: [#149](https://github.com/aws-solutions/serverless-image-handler/issues/149)
- Fix image scaling issue for filename containing 'x' character: [#163](https://github.com/aws-solutions/serverless-image-handler/issues/163), [#176](https://github.com/aws-solutions/serverless-image-handler/issues/176)
- Fix regular expression issue: [#114](https://github.com/aws-solutions/serverless-image-handler/issues/114), [#121](https://github.com/aws-solutions/serverless-image-handler/issues/121), [#125](https://github.com/aws-solutions/serverless-image-handler/issues/125)
- Fix not working quality parameter: [#129](https://github.com/aws-solutions/serverless-image-handler/issues/129)

## [4.1.0] - 2019-12-31

### Added

- CHANGELOG file
- Access logging to API Gateway

### Changed

- Lambda functions runtime to nodejs12.x
- sharp version (from 0.21.3 to 0.23.3)
- Image handler function to use Composite API (<https://sharp.pixelplumbing.com/en/stable/api-composite/>)
- License to Apache-2.0

### Removed

- Reference to deprecated sharp function (overlayWith)
- Capability to resize images proportionally if width or height is set to 0 (sharp v0.23.1 and later check that the width and height - if present - are positive integers)
