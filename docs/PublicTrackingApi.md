# PublicTrackingApi

All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**track**](PublicTrackingApi.md#track) | **GET** /delivery/v1/public/track/{trackingNumber} | Track a delivery by tracking number |


<a id="track"></a>
# **track**
> PublicTrackingResponse track(trackingNumber, acceptLanguage)

Track a delivery by tracking number

Returns public tracking information for a delivery. No authentication required.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.PublicTrackingApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    PublicTrackingApi apiInstance = new PublicTrackingApi(defaultClient);
    String trackingNumber = "trackingNumber_example"; // String | Delivery tracking number (e.g. ZIPPERGUDWXJNXTTJ17)
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      PublicTrackingResponse result = apiInstance.track(trackingNumber, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling PublicTrackingApi#track");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **trackingNumber** | **String**| Delivery tracking number (e.g. ZIPPERGUDWXJNXTTJ17) | |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**PublicTrackingResponse**](PublicTrackingResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Tracking information returned |  -  |
| **404** | Delivery not found |  -  |
| **429** | Rate limit exceeded |  -  |

