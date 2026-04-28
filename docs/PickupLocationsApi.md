# PickupLocationsApi

All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**bulkUpsertPickupLocations**](PickupLocationsApi.md#bulkUpsertPickupLocations) | **POST** /delivery/v1/pickup-locations/bulk-upsert | Bulk upsert pickup locations (async) |
| [**createPickupLocation**](PickupLocationsApi.md#createPickupLocation) | **POST** /delivery/v1/pickup-locations | Create a pickup location |
| [**deletePickupLocation**](PickupLocationsApi.md#deletePickupLocation) | **DELETE** /delivery/v1/pickup-locations/{id} | Delete a pickup location |
| [**getPickupLocation**](PickupLocationsApi.md#getPickupLocation) | **GET** /delivery/v1/pickup-locations/{id} | Get a pickup location by ID |
| [**searchPickupLocations**](PickupLocationsApi.md#searchPickupLocations) | **POST** /delivery/v1/pickup-locations/search | Search pickup locations |
| [**updatePickupLocation**](PickupLocationsApi.md#updatePickupLocation) | **PUT** /delivery/v1/pickup-locations/{id} | Update a pickup location |


<a id="bulkUpsertPickupLocations"></a>
# **bulkUpsertPickupLocations**
> bulkUpsertPickupLocations(bulkUpsertPickupLocationRequest, acceptLanguage)

Bulk upsert pickup locations (async)

Accepts a batch of pickup locations for create or update. Matching is by &#x60;code&#x60; — existing codes are updated, new codes are created. Processing is asynchronous via message queue. On completion, a webhook event &#x60;pickup_location_bulk_upsert_completed&#x60; is sent with results and any errors.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.PickupLocationsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    PickupLocationsApi apiInstance = new PickupLocationsApi(defaultClient);
    BulkUpsertPickupLocationRequest bulkUpsertPickupLocationRequest = new BulkUpsertPickupLocationRequest(); // BulkUpsertPickupLocationRequest | 
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      apiInstance.bulkUpsertPickupLocations(bulkUpsertPickupLocationRequest, acceptLanguage);
    } catch (ApiException e) {
      System.err.println("Exception when calling PickupLocationsApi#bulkUpsertPickupLocations");
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
| **bulkUpsertPickupLocationRequest** | [**BulkUpsertPickupLocationRequest**](BulkUpsertPickupLocationRequest.md)|  | |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

null (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: Not defined

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **202** | Batch accepted for async processing |  -  |
| **400** | Validation error |  -  |

<a id="createPickupLocation"></a>
# **createPickupLocation**
> PickupLocationDTO createPickupLocation(createPickupLocationRequest, acceptLanguage)

Create a pickup location

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.PickupLocationsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    PickupLocationsApi apiInstance = new PickupLocationsApi(defaultClient);
    CreatePickupLocationRequest createPickupLocationRequest = new CreatePickupLocationRequest(); // CreatePickupLocationRequest | 
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      PickupLocationDTO result = apiInstance.createPickupLocation(createPickupLocationRequest, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling PickupLocationsApi#createPickupLocation");
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
| **createPickupLocationRequest** | [**CreatePickupLocationRequest**](CreatePickupLocationRequest.md)|  | |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**PickupLocationDTO**](PickupLocationDTO.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Pickup location created |  -  |
| **400** | Validation error |  -  |
| **409** | Code already exists |  -  |

<a id="deletePickupLocation"></a>
# **deletePickupLocation**
> deletePickupLocation(id, acceptLanguage)

Delete a pickup location

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.PickupLocationsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    PickupLocationsApi apiInstance = new PickupLocationsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | Pickup location ID
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      apiInstance.deletePickupLocation(id, acceptLanguage);
    } catch (ApiException e) {
      System.err.println("Exception when calling PickupLocationsApi#deletePickupLocation");
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
| **id** | **UUID**| Pickup location ID | |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

null (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Pickup location deleted |  -  |
| **404** | Not found |  -  |

<a id="getPickupLocation"></a>
# **getPickupLocation**
> PickupLocationDTO getPickupLocation(id, acceptLanguage)

Get a pickup location by ID

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.PickupLocationsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    PickupLocationsApi apiInstance = new PickupLocationsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | Pickup location ID
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      PickupLocationDTO result = apiInstance.getPickupLocation(id, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling PickupLocationsApi#getPickupLocation");
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
| **id** | **UUID**| Pickup location ID | |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**PickupLocationDTO**](PickupLocationDTO.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Pickup location found |  -  |
| **404** | Not found |  -  |

<a id="searchPickupLocations"></a>
# **searchPickupLocations**
> PageResponseListPickupLocationDTO searchPickupLocations(searchPickupLocationsRequest, acceptLanguage)

Search pickup locations

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.PickupLocationsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    PickupLocationsApi apiInstance = new PickupLocationsApi(defaultClient);
    SearchPickupLocationsRequest searchPickupLocationsRequest = new SearchPickupLocationsRequest(); // SearchPickupLocationsRequest | 
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      PageResponseListPickupLocationDTO result = apiInstance.searchPickupLocations(searchPickupLocationsRequest, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling PickupLocationsApi#searchPickupLocations");
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
| **searchPickupLocationsRequest** | [**SearchPickupLocationsRequest**](SearchPickupLocationsRequest.md)|  | |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**PageResponseListPickupLocationDTO**](PageResponseListPickupLocationDTO.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Search results returned |  -  |

<a id="updatePickupLocation"></a>
# **updatePickupLocation**
> PickupLocationDTO updatePickupLocation(id, updatePickupLocationRequest, acceptLanguage)

Update a pickup location

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.PickupLocationsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    PickupLocationsApi apiInstance = new PickupLocationsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | Pickup location ID
    UpdatePickupLocationRequest updatePickupLocationRequest = new UpdatePickupLocationRequest(); // UpdatePickupLocationRequest | 
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      PickupLocationDTO result = apiInstance.updatePickupLocation(id, updatePickupLocationRequest, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling PickupLocationsApi#updatePickupLocation");
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
| **id** | **UUID**| Pickup location ID | |
| **updatePickupLocationRequest** | [**UpdatePickupLocationRequest**](UpdatePickupLocationRequest.md)|  | |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**PickupLocationDTO**](PickupLocationDTO.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Pickup location updated |  -  |
| **400** | Validation error |  -  |
| **404** | Not found |  -  |

