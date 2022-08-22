Cloudinary Media Editing SDK
============================

## About
The Cloudinary Media Editing SDK allows you to quickly and easily integrate your application with Cloudinary.
Effortlessly edit and deliver your cloud's assets.

### Additional documentation
This Readme provides basic installation and usage information.
For the complete documentation, see the [Media Editing SDK Guide](https://cloudinary.com/documentation/media_editing_api).


## Table of Contents
- [Key Features](#key-features)
- [Version Support](#Version-Support)
- [Installation](#installation)
- [Usage](#usage)
    - [Setup](#Setup)
    - [Create Media Source](#Create Media Source)

# Key Features
### Media Delivery API
-[CacheApi](https://github.com/cloudinary/media-delivery-api-java/blob/main/docs/CacheApi.md)
-[DeliveryProfileApi](https://github.com/cloudinary/media-delivery-api-java/blob/docs/DeliveryProfileApi.md)
-[MappingFunctionApi](https://github.com/cloudinary/media-delivery-api-java/blob/main/docs/MappingFunctionApi.md)
-[MediaSourceApi](https://github.com/cloudinary/media-delivery-api-java/blob/main/docs/MediaSourceApi.md)
-[MediaTargetApi](https://github.com/cloudinary/media-delivery-api-java/blob/main/docs/MediaTargetApi.md)

### Media Editing API
-[TransformApi](https://github.com/cloudinary/media-editing-api-java/blob/main/docs/TransformApi.md)

## Version Support
| SDK Version | Java 6+ |
|-------------|---------|
| 0.1.+       | V       |

## Installation
### Gradle
```groovy
implementation 'com.cloudinary:media-editing-java:0.1.2-beta'
```
### Maven
```xml
<dependency>
    <groupId>com.cloudinary</groupId>
    <artifactId>media-editing-java</artifactId>
    <version>0.1.2-beta</version>
</dependency>
```
# Usage
### Setup
```java
// import the Cloudinary library
import com.cloudinary.ApiClient;
class SampleApp {
    ApiClient apiClient = Configuration.getDefaultApiClient();
    apiClient.setCloudinaryUrl("cloudinary://API_KEY:API_SECRET@CLOUD_NAME");
}
```
### Create Media Source
The following example shows how to add a new media source:
```java
    MediaSourceCreatePayload mediaSourceCreatePayload = new MediaSourceCreatePayload();
    mediaSourceCreatePayload.setDisplayName("my_media_source");
    mediaSourceCreatePayload.setSourceType(MediaSourceCreatePayload.SourceTypeEnum.S3);

    MediaSourceConfig config = new MediaSourceConfig();
    config.setS3BucketName("my_bucket");
    config.setS3BucketFolder("my_bucket_folder");
    config.setS3AccessKey("123456789");
    config.setS3SecretKey("123456789");
    config.setS3UriTemplate("s3://my_bucket/images/{{vars.signature}}/{{fwd_key}}");
    mediaSourceCreatePayload.setConfig(config);

    try {
        MediaSource result = apiInstance.createMediaSource(mediaSourceCreatePayload);
        System.out.println(result);
    } catch (ApiException e) {
       System.out.println(e.getMessage());
    }
```

### Transform and Store
Example of how to perform transform and store:
```java
    TransformationDescriptor transformationDescriptor = new TransformationDescriptor();
    transformationDescriptor.setCanonicalTransformation("w_500,c_scale");
    MediaConnectorInstance mediaConnectorInstance = new MediaConnectorInstance();
    mediaConnectorInstance.setId("123456789");
    mediaConnectorInstance.setFwdKey("sample");
    MediaConnectorInstance mediaTargetConnectionInstance = new MediaConnectorInstance();
    mediaTargetConnectionInstance.setId("987654321");
    mediaTargetConnectionInstance.setFwdKey("new");
    TransformRequest request = new TransformRequest();
    request.setInputType(TransformRequest.InputTypeEnum.MEDIA_SOURCE);
    request.setMediaTarget(mediaTargetConnectionInstance);
    request.setMediaSource(mediaConnectorInstance);
    request.setResourceType(TransformRequest.ResourceTypeEnum.IMAGE);
    request.setTransformationDescriptor(transformationDescriptor);
    try {
        TransformResult response = new TransformAndStoreApi().transformAndStore(request);
        System.out.println(response);
    } catch (ApiException e) {
        System.out.println(e.getMessage());
    }
```

### Cache warmup
Example of how perform cache warmup:
```java
    CacheWarmupRequestPayload cacheWarmupRequestPayload = new CacheWarmupRequestPayload();
    cacheWarmupRequestPayload.setUrl("<your url>");
    //cacheWarmupRequestPayload.setUrl("https://<cloud_name>.cloudinary.net/image/upload/c_scale,w_500/sample");
      try {
          CacheWarmupSuccessResponse response = new CacheApi().warmup(cacheWarmupRequestPayload);
          System.out.println(response);
      } catch (ApiException e) {
          System.out.println(e.getMessage());
      }
```


## Contributions
- Ensure tests run locally
- Open a PR and ensure Travis tests pass

## Get Help
- [Open a Github issue](https://github.com/CloudinaryLtd/media-editing-java/issues) (for issues related to the SDK)
- [Open a support ticket](https://cloudinary.com/contact) (for issues related to your account)

## About Cloudinary
Cloudinary is a powerful media API for websites and mobile apps alike, Cloudinary enables developers to efficiently manage, transform, optimize, and deliver images and videos through multiple CDNs. Ultimately, viewers enjoy responsive and personalized visual-media experiences—irrespective of the viewing device.

## Additional Resources
- [Cloudinary Transformation and REST API References](https://cloudinary.com/documentation/cloudinary_references): Comprehensive references, including syntax and examples for all SDKs.
- [MediaJams.dev](https://mediajams.dev/): Bite-size use-case tutorials written by and for Cloudinary Developers
- [DevJams](https://www.youtube.com/playlist?list=PL8dVGjLA2oMr09amgERARsZyrOz_sPvqw): Cloudinary developer podcasts on YouTube.
- [Cloudinary Academy](https://training.cloudinary.com/): Free self-paced courses, instructor-led virtual courses, and on-site courses.
- [Code Explorers and Feature Demos](https://cloudinary.com/documentation/code_explorers_demos_index): A one-stop shop for all code explorers, Postman collections, and feature demos found in the docs.
- [Cloudinary Roadmap](https://cloudinary.com/roadmap): Your chance to follow, vote, or suggest what Cloudinary should develop next.
- [Cloudinary Facebook Community](https://www.facebook.com/groups/CloudinaryCommunity): Learn from and offer help to other Cloudinary developers.
- [Cloudinary Account Registration](https://cloudinary.com/users/register/free): Free Cloudinary account registration.
- [Cloudinary Website](https://cloudinary.com)

## License
Released under the MIT license See the [LICENSE](https://github.com/cloudinary/media-editing-java/blob/main/LICENSE) file for details.