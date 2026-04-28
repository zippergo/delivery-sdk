# InternalPickupLocationsApi

All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getById**](InternalPickupLocationsApi.md#getById) | **GET** /delivery/v1/internal/pickup-locations/{id} | Get pickup location by external ID |


<a id="getById"></a>
# **getById**
> InternalPickupLocationDTO getById(id, acceptLanguage)

Get pickup location by external ID

Returns pickup location metadata. Used for service-to-service validation.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.InternalPickupLocationsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    InternalPickupLocationsApi apiInstance = new InternalPickupLocationsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      InternalPickupLocationDTO result = apiInstance.getById(id, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling InternalPickupLocationsApi#getById");
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
| **id** | **UUID**|  | |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**InternalPickupLocationDTO**](InternalPickupLocationDTO.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Location found |  -  |
| **404** | Location not found |  -  |

