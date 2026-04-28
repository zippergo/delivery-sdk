# EchoApi

All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**echoV1**](EchoApi.md#echoV1) | **GET** /delivery/v1/echo | Echo a message back |


<a id="echoV1"></a>
# **echoV1**
> EchoResponse echoV1(message, acceptLanguage)

Echo a message back

Returns the provided message along with the API version. Useful for connectivity checks.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.EchoApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    EchoApi apiInstance = new EchoApi(defaultClient);
    String message = "hello"; // String | Message to echo back
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      EchoResponse result = apiInstance.echoV1(message, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling EchoApi#echoV1");
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
| **message** | **String**| Message to echo back | [optional] [default to hello] |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**EchoResponse**](EchoResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Echo response returned successfully |  -  |
| **403** | Forbidden — insufficient permissions |  -  |
| **500** | Internal server error |  -  |

