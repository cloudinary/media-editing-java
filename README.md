Cloudinary Media Editing SDK
=========================
## About
The Cloudinary Media Editing SDK allows you to quickly and easily integrate your application with Cloudinary.
Effortlessly edit and deliver your cloud's assets.

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

# APIS
### Media Delivery API
* [CacheApi](https://github.com/cloudinary/media-delivery-api-java/blob/main/docs/CacheApi.md)
* [DeliveryProfileApi](https://github.com/cloudinary/media-delivery-api-java/blob/docs/DeliveryProfileApi.md)
* [MappingFunctionApi](https://github.com/cloudinary/media-delivery-api-java/blob/main/docs/MappingFunctionApi.md)
* [MediaSourceApi](https://github.com/cloudinary/media-delivery-api-java/blob/main/docs/MediaSourceApi.md)
* [MediaTargetApi](https://github.com/cloudinary/media-delivery-api-java/blob/main/docs/MediaTargetApi.md)

### Media Editing API
* [TransformApi](https://github.com/cloudinary/media-editing-api-java/blob/main/docs/TransformApi.md)

## Get Help
If you run into an issue or have a question, you can either:
- Issues related to the SDK: [Open a Github issue](https://github.com/cloudinary/media-editing-java/issues)
- Issues related to your account: [Open a support ticket](https://cloudinary.com/contact)

## License
Released under the MIT license See the [LICENSE](https://github.com/cloudinary/media-editing-java/blob/main/LICENSE) file for details.