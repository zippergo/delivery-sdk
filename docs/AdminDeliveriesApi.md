# AdminDeliveriesApi

All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**adminCancelDelivery**](AdminDeliveriesApi.md#adminCancelDelivery) | **POST** /delivery/v1/admin/deliveries/{deliveryId}/cancel | Cancel a delivery (admin) |
| [**adminGetDelivery**](AdminDeliveriesApi.md#adminGetDelivery) | **GET** /delivery/v1/admin/deliveries/{deliveryId} | Get delivery by ID |
| [**adminGetDeliveryLabel**](AdminDeliveriesApi.md#adminGetDeliveryLabel) | **GET** /delivery/v1/admin/deliveries/{deliveryId}/label | Get delivery label metadata (admin) |
| [**adminGetDeliveryLabelAsset**](AdminDeliveriesApi.md#adminGetDeliveryLabelAsset) | **GET** /delivery/v1/admin/deliveries/{deliveryId}/label/{filename} | Download a label asset (admin) |
| [**adminSearchAllDeliveries**](AdminDeliveriesApi.md#adminSearchAllDeliveries) | **POST** /delivery/v1/admin/deliveries/search | Search all deliveries |


<a id="adminCancelDelivery"></a>
# **adminCancelDelivery**
> HubCancelDeliveryResponse adminCancelDelivery(deliveryId, acceptLanguage)

Cancel a delivery (admin)

Cancels a delivery that is in CREATED or ASSIGNED status. Admin only, no ownership check.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.AdminDeliveriesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    AdminDeliveriesApi apiInstance = new AdminDeliveriesApi(defaultClient);
    UUID deliveryId = UUID.fromString("550e8400-e29b-41d4-a716-446655440000"); // UUID | UUID of the delivery to cancel
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      HubCancelDeliveryResponse result = apiInstance.adminCancelDelivery(deliveryId, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling AdminDeliveriesApi#adminCancelDelivery");
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
| **deliveryId** | **UUID**| UUID of the delivery to cancel | |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**HubCancelDeliveryResponse**](HubCancelDeliveryResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Delivery cancelled successfully |  -  |
| **404** | Delivery not found |  -  |
| **403** | Forbidden |  -  |
| **409** | Delivery cannot be cancelled in its current status |  -  |
| **422** | Provider cancellation failed |  -  |

<a id="adminGetDelivery"></a>
# **adminGetDelivery**
> HubDeliveryStatusResponse adminGetDelivery(deliveryId, acceptLanguage)

Get delivery by ID

Get a single delivery by its ID. Admin only, no ownership check.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.AdminDeliveriesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    AdminDeliveriesApi apiInstance = new AdminDeliveriesApi(defaultClient);
    UUID deliveryId = UUID.randomUUID(); // UUID | 
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      HubDeliveryStatusResponse result = apiInstance.adminGetDelivery(deliveryId, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling AdminDeliveriesApi#adminGetDelivery");
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
| **deliveryId** | **UUID**|  | |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**HubDeliveryStatusResponse**](HubDeliveryStatusResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Delivery found |  -  |
| **404** | Delivery not found |  -  |
| **403** | Forbidden |  -  |

<a id="adminGetDeliveryLabel"></a>
# **adminGetDeliveryLabel**
> HubDeliveryLabelResponse adminGetDeliveryLabel(deliveryId, acceptLanguage)

Get delivery label metadata (admin)

Returns barcode value and URLs for barcode image, QR code, and label PDF. Admin only, no ownership check.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.AdminDeliveriesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    AdminDeliveriesApi apiInstance = new AdminDeliveriesApi(defaultClient);
    UUID deliveryId = UUID.fromString("550e8400-e29b-41d4-a716-446655440000"); // UUID | UUID of the delivery to get label for
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      HubDeliveryLabelResponse result = apiInstance.adminGetDeliveryLabel(deliveryId, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling AdminDeliveriesApi#adminGetDeliveryLabel");
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
| **deliveryId** | **UUID**| UUID of the delivery to get label for | |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**HubDeliveryLabelResponse**](HubDeliveryLabelResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Label metadata returned |  -  |
| **404** | Delivery not found |  -  |
| **403** | Forbidden |  -  |

<a id="adminGetDeliveryLabelAsset"></a>
# **adminGetDeliveryLabelAsset**
> File adminGetDeliveryLabelAsset(deliveryId, filename, acceptLanguage)

Download a label asset (admin)

Serves a label asset (barcode.png, qrcode.png, or label.pdf) for a delivery. Admin only, no ownership check.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.AdminDeliveriesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    AdminDeliveriesApi apiInstance = new AdminDeliveriesApi(defaultClient);
    UUID deliveryId = UUID.fromString("550e8400-e29b-41d4-a716-446655440000"); // UUID | UUID of the delivery to get label asset for
    String filename = "barcode.png"; // String | Asset filename
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      File result = apiInstance.adminGetDeliveryLabelAsset(deliveryId, filename, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling AdminDeliveriesApi#adminGetDeliveryLabelAsset");
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
| **deliveryId** | **UUID**| UUID of the delivery to get label asset for | |
| **filename** | **String**| Asset filename | |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**File**](File.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Asset returned |  -  |
| **400** | Invalid filename |  -  |
| **404** | Delivery not found |  -  |
| **403** | Forbidden |  -  |

<a id="adminSearchAllDeliveries"></a>
# **adminSearchAllDeliveries**
> PageResponseListHubDeliverySearchDTO adminSearchAllDeliveries(searchDeliveriesRequest, acceptLanguage)

Search all deliveries

Search and filter deliveries across all users with pagination. Admin only.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.AdminDeliveriesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    AdminDeliveriesApi apiInstance = new AdminDeliveriesApi(defaultClient);
    SearchDeliveriesRequest searchDeliveriesRequest = new SearchDeliveriesRequest(); // SearchDeliveriesRequest | 
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      PageResponseListHubDeliverySearchDTO result = apiInstance.adminSearchAllDeliveries(searchDeliveriesRequest, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling AdminDeliveriesApi#adminSearchAllDeliveries");
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
| **searchDeliveriesRequest** | [**SearchDeliveriesRequest**](SearchDeliveriesRequest.md)|  | |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**PageResponseListHubDeliverySearchDTO**](PageResponseListHubDeliverySearchDTO.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Search results returned |  -  |
| **403** | Forbidden |  -  |

