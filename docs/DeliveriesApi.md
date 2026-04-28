# DeliveriesApi

All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**cancelDelivery**](DeliveriesApi.md#cancelDelivery) | **POST** /delivery/v1/deliveries/{deliveryId}/cancel | Cancel a delivery |
| [**createDelivery**](DeliveriesApi.md#createDelivery) | **POST** /delivery/v1/deliveries | Create a delivery |
| [**getDelivery**](DeliveriesApi.md#getDelivery) | **GET** /delivery/v1/deliveries/{deliveryId} | Get delivery status |
| [**getDeliveryLabel**](DeliveriesApi.md#getDeliveryLabel) | **GET** /delivery/v1/deliveries/{hubTrackingNumber}/label | Get delivery label metadata |
| [**getDeliveryLabelAsset**](DeliveriesApi.md#getDeliveryLabelAsset) | **GET** /delivery/v1/deliveries/{hubTrackingNumber}/label/{filename} | Download a label asset |
| [**getHandshakeDelivery**](DeliveriesApi.md#getHandshakeDelivery) | **GET** /delivery/v1/deliveries/{deliveryId}/handshake | Get handshake PIN info |
| [**getQuote**](DeliveriesApi.md#getQuote) | **POST** /delivery/v1/deliveries/quote | Get a delivery quote |
| [**searchDeliveries**](DeliveriesApi.md#searchDeliveries) | **POST** /delivery/v1/deliveries/search | Search deliveries |
| [**trackDelivery**](DeliveriesApi.md#trackDelivery) | **GET** /delivery/v1/deliveries/track/{hubTrackingNumber} | Track delivery by tracking number |


<a id="cancelDelivery"></a>
# **cancelDelivery**
> HubCancelDeliveryResponse cancelDelivery(deliveryId, acceptLanguage)

Cancel a delivery

Cancels a delivery that is in CREATED or ASSIGNED status. If the delivery has been dispatched to a provider, the cancellation is also forwarded to the provider.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.DeliveriesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    DeliveriesApi apiInstance = new DeliveriesApi(defaultClient);
    UUID deliveryId = UUID.fromString("550e8400-e29b-41d4-a716-446655440000"); // UUID | UUID of the delivery to cancel
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      HubCancelDeliveryResponse result = apiInstance.cancelDelivery(deliveryId, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling DeliveriesApi#cancelDelivery");
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
| **409** | Delivery cannot be cancelled in its current status |  -  |
| **422** | Provider cancellation failed |  -  |

<a id="createDelivery"></a>
# **createDelivery**
> HubCreateDeliveryResponse createDelivery(hubCreateDeliveryRequest, idempotencyKey, acceptLanguage)

Create a delivery

Dispatches a new delivery order to the best available carrier provider. An optional idempotency key prevents duplicate orders.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.DeliveriesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    DeliveriesApi apiInstance = new DeliveriesApi(defaultClient);
    HubCreateDeliveryRequest hubCreateDeliveryRequest = new HubCreateDeliveryRequest(); // HubCreateDeliveryRequest | 
    String idempotencyKey = "idempotencyKey_example"; // String | Unique key to ensure idempotent delivery creation
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      HubCreateDeliveryResponse result = apiInstance.createDelivery(hubCreateDeliveryRequest, idempotencyKey, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling DeliveriesApi#createDelivery");
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
| **hubCreateDeliveryRequest** | [**HubCreateDeliveryRequest**](HubCreateDeliveryRequest.md)|  | |
| **idempotencyKey** | **String**| Unique key to ensure idempotent delivery creation | [optional] |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**HubCreateDeliveryResponse**](HubCreateDeliveryResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Delivery created successfully |  -  |
| **400** | Invalid request parameters |  -  |
| **403** | Forbidden — insufficient permissions |  -  |
| **409** | Duplicate idempotency key |  -  |
| **500** | Internal server error |  -  |

<a id="getDelivery"></a>
# **getDelivery**
> HubDeliveryStatusResponse getDelivery(deliveryId, acceptLanguage)

Get delivery status

Retrieves the current status, tracking information, and full status history of a delivery.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.DeliveriesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    DeliveriesApi apiInstance = new DeliveriesApi(defaultClient);
    UUID deliveryId = UUID.fromString("550e8400-e29b-41d4-a716-446655440000"); // UUID | UUID of the delivery to retrieve
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      HubDeliveryStatusResponse result = apiInstance.getDelivery(deliveryId, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling DeliveriesApi#getDelivery");
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
| **deliveryId** | **UUID**| UUID of the delivery to retrieve | |
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
| **200** | Delivery details returned |  -  |
| **403** | Forbidden — insufficient permissions |  -  |
| **404** | Delivery not found |  -  |
| **500** | Internal server error |  -  |

<a id="getDeliveryLabel"></a>
# **getDeliveryLabel**
> HubDeliveryLabelResponse getDeliveryLabel(hubTrackingNumber, acceptLanguage)

Get delivery label metadata

Returns barcode value and URLs for barcode image, QR code, and label PDF for a delivery identified by its hub tracking number.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.DeliveriesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    DeliveriesApi apiInstance = new DeliveriesApi(defaultClient);
    String hubTrackingNumber = "HUB-0000001000"; // String | Hub tracking number
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      HubDeliveryLabelResponse result = apiInstance.getDeliveryLabel(hubTrackingNumber, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling DeliveriesApi#getDeliveryLabel");
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
| **hubTrackingNumber** | **String**| Hub tracking number | |
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

<a id="getDeliveryLabelAsset"></a>
# **getDeliveryLabelAsset**
> File getDeliveryLabelAsset(hubTrackingNumber, filename, acceptLanguage)

Download a label asset

Serves a label asset (barcode.png, qrcode.png, or label.pdf) for a delivery. Streams from storage or generates on-the-fly if not yet uploaded.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.DeliveriesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    DeliveriesApi apiInstance = new DeliveriesApi(defaultClient);
    String hubTrackingNumber = "HUB-0000001000"; // String | Hub tracking number
    String filename = "barcode.png"; // String | Asset filename
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      File result = apiInstance.getDeliveryLabelAsset(hubTrackingNumber, filename, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling DeliveriesApi#getDeliveryLabelAsset");
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
| **hubTrackingNumber** | **String**| Hub tracking number | |
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

<a id="getHandshakeDelivery"></a>
# **getHandshakeDelivery**
> HubHandshakeDeliveryResponse getHandshakeDelivery(deliveryId, acceptLanguage)

Get handshake PIN info

Returns PIN handshake information for a delivery, including whether a PIN is required and the PIN code if applicable.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.DeliveriesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    DeliveriesApi apiInstance = new DeliveriesApi(defaultClient);
    UUID deliveryId = UUID.fromString("550e8400-e29b-41d4-a716-446655440000"); // UUID | UUID of the delivery
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      HubHandshakeDeliveryResponse result = apiInstance.getHandshakeDelivery(deliveryId, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling DeliveriesApi#getHandshakeDelivery");
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
| **deliveryId** | **UUID**| UUID of the delivery | |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**HubHandshakeDeliveryResponse**](HubHandshakeDeliveryResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Handshake info returned |  -  |
| **403** | Forbidden — insufficient permissions |  -  |
| **404** | Delivery not found |  -  |

<a id="getQuote"></a>
# **getQuote**
> HubDeliveryQuoteResponse getQuote(hubDeliveryQuoteRequest, acceptLanguage)

Get a delivery quote

Returns a price quote and estimated arrival time for the given pickup/dropoff route and delivery type.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.DeliveriesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    DeliveriesApi apiInstance = new DeliveriesApi(defaultClient);
    HubDeliveryQuoteRequest hubDeliveryQuoteRequest = new HubDeliveryQuoteRequest(); // HubDeliveryQuoteRequest | 
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      HubDeliveryQuoteResponse result = apiInstance.getQuote(hubDeliveryQuoteRequest, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling DeliveriesApi#getQuote");
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
| **hubDeliveryQuoteRequest** | [**HubDeliveryQuoteRequest**](HubDeliveryQuoteRequest.md)|  | |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**HubDeliveryQuoteResponse**](HubDeliveryQuoteResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Quote returned successfully |  -  |
| **400** | Invalid request parameters |  -  |
| **403** | Forbidden — insufficient permissions |  -  |
| **500** | Internal server error |  -  |

<a id="searchDeliveries"></a>
# **searchDeliveries**
> PageResponseListHubDeliverySearchDTO searchDeliveries(searchDeliveriesRequest, acceptLanguage)

Search deliveries

Search and filter deliveries with pagination. Supports filtering by status, date range, and other criteria. Returns a paginated list of deliveries matching the search parameters.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.DeliveriesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    DeliveriesApi apiInstance = new DeliveriesApi(defaultClient);
    SearchDeliveriesRequest searchDeliveriesRequest = new SearchDeliveriesRequest(); // SearchDeliveriesRequest | 
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      PageResponseListHubDeliverySearchDTO result = apiInstance.searchDeliveries(searchDeliveriesRequest, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling DeliveriesApi#searchDeliveries");
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

<a id="trackDelivery"></a>
# **trackDelivery**
> HubDeliveryStatusResponse trackDelivery(hubTrackingNumber, acceptLanguage)

Track delivery by tracking number

Retrieves delivery status and tracking information using the hub tracking number. This endpoint is designed for easy tracking URL sharing and does not require authentication, but will only return information for deliveries that have been marked as &#39;trackable&#39; by the sender.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.DeliveriesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    DeliveriesApi apiInstance = new DeliveriesApi(defaultClient);
    String hubTrackingNumber = "HUB-0000001000"; // String | Hub tracking number
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      HubDeliveryStatusResponse result = apiInstance.trackDelivery(hubTrackingNumber, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling DeliveriesApi#trackDelivery");
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
| **hubTrackingNumber** | **String**| Hub tracking number | |
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
| **200** | Delivery details returned |  -  |
| **404** | Delivery not found |  -  |

