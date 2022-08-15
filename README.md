Cloudinary Media Editing SDK
============================

## About
The Cloudinary Media Editing SDK allows you to quickly and easily integrate your application with Cloudinary.
Effortlessly edit and deliver your cloud's assets.

### Additional documentation
This Readme provides basic installation and usage information.
For the complete documentation, see the [Media Editing SDK Guide](https://cloudinary.com/documentation).

## Table of Contents
- [Key Features](#key-features)
- [Version Support](#Version-Support)
- [Installation](#installation)
- [Usage](#usage)
    - [Setup](#Setup)

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