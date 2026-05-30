# InternalDeliveriesApi

All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**internalCancelDelivery**](InternalDeliveriesApi.md#internalCancelDelivery) | **POST** /delivery/v1/internal/deliveries/{deliveryId}/cancel | Cancel a delivery |
| [**internalCreateDelivery**](InternalDeliveriesApi.md#internalCreateDelivery) | **POST** /delivery/v1/internal/users/{userId}/deliveries | Create a delivery for a user |
| [**internalGetDelivery**](InternalDeliveriesApi.md#internalGetDelivery) | **GET** /delivery/v1/internal/deliveries/{deliveryId} | Get delivery status |
| [**internalGetDeliveryLabel**](InternalDeliveriesApi.md#internalGetDeliveryLabel) | **GET** /delivery/v1/internal/deliveries/{hubTrackingNumber}/label | Get delivery label metadata |
| [**internalGetDeliveryLabelAsset**](InternalDeliveriesApi.md#internalGetDeliveryLabelAsset) | **GET** /delivery/v1/internal/deliveries/{hubTrackingNumber}/label/{filename} | Download a label asset |
| [**internalGetHandshakeDelivery**](InternalDeliveriesApi.md#internalGetHandshakeDelivery) | **GET** /delivery/v1/internal/deliveries/{deliveryId}/handshake | Get handshake PIN info |
| [**internalGetQuote**](InternalDeliveriesApi.md#internalGetQuote) | **POST** /delivery/v1/internal/users/{userId}/deliveries/quote | Get a delivery quote for a user |
| [**internalRetryDelivery**](InternalDeliveriesApi.md#internalRetryDelivery) | **POST** /delivery/v1/internal/deliveries/{deliveryId}/retry | Retry a delivery |
| [**internalSearchDeliveries**](InternalDeliveriesApi.md#internalSearchDeliveries) | **POST** /delivery/v1/internal/deliveries/search | Search deliveries |
| [**internalTrackDelivery**](InternalDeliveriesApi.md#internalTrackDelivery) | **GET** /delivery/v1/internal/deliveries/track/{hubTrackingNumber} | Track delivery by tracking number |
| [**statusesByIds**](InternalDeliveriesApi.md#statusesByIds) | **POST** /delivery/v1/internal/deliveries/by-ids | Get current status for a list of deliveries |


<a id="internalCancelDelivery"></a>
# **internalCancelDelivery**
> HubCancelDeliveryResponse internalCancelDelivery(deliveryId, acceptLanguage)

Cancel a delivery

Cancels a delivery that is in a cancellable status. If the delivery has been dispatched to a provider, the cancellation is also forwarded to the provider.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.InternalDeliveriesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    InternalDeliveriesApi apiInstance = new InternalDeliveriesApi(defaultClient);
    UUID deliveryId = UUID.fromString("550e8400-e29b-41d4-a716-446655440000"); // UUID | UUID of the delivery to cancel
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      HubCancelDeliveryResponse result = apiInstance.internalCancelDelivery(deliveryId, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling InternalDeliveriesApi#internalCancelDelivery");
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
| **403** | Forbidden — insufficient role/scope |  -  |
| **404** | Delivery not found |  -  |
| **409** | Delivery cannot be cancelled in its current status |  -  |

<a id="internalCreateDelivery"></a>
# **internalCreateDelivery**
> HubCreateDeliveryResponse internalCreateDelivery(userId, hubCreateDeliveryRequest, idempotencyKey, acceptLanguage)

Create a delivery for a user

Dispatches a new delivery order to the best available carrier provider on behalf of the path user. An optional idempotency key prevents duplicate orders.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.InternalDeliveriesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    InternalDeliveriesApi apiInstance = new InternalDeliveriesApi(defaultClient);
    String userId = "userId_example"; // String | 
    HubCreateDeliveryRequest hubCreateDeliveryRequest = new HubCreateDeliveryRequest(); // HubCreateDeliveryRequest | 
    String idempotencyKey = "idempotencyKey_example"; // String | Unique key to ensure idempotent delivery creation
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      HubCreateDeliveryResponse result = apiInstance.internalCreateDelivery(userId, hubCreateDeliveryRequest, idempotencyKey, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling InternalDeliveriesApi#internalCreateDelivery");
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
| **userId** | **String**|  | |
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
| **403** | Forbidden — insufficient role/scope |  -  |
| **409** | Duplicate idempotency key |  -  |

<a id="internalGetDelivery"></a>
# **internalGetDelivery**
> HubDeliveryStatusResponse internalGetDelivery(deliveryId, acceptLanguage)

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
import com.zipper.delivery.hub.sdk.api.InternalDeliveriesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    InternalDeliveriesApi apiInstance = new InternalDeliveriesApi(defaultClient);
    UUID deliveryId = UUID.fromString("550e8400-e29b-41d4-a716-446655440000"); // UUID | UUID of the delivery to retrieve
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      HubDeliveryStatusResponse result = apiInstance.internalGetDelivery(deliveryId, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling InternalDeliveriesApi#internalGetDelivery");
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
| **403** | Forbidden — insufficient role/scope |  -  |
| **404** | Delivery not found |  -  |

<a id="internalGetDeliveryLabel"></a>
# **internalGetDeliveryLabel**
> HubDeliveryLabelResponse internalGetDeliveryLabel(hubTrackingNumber, acceptLanguage)

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
import com.zipper.delivery.hub.sdk.api.InternalDeliveriesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    InternalDeliveriesApi apiInstance = new InternalDeliveriesApi(defaultClient);
    String hubTrackingNumber = "HUB-0000001000"; // String | Hub tracking number
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      HubDeliveryLabelResponse result = apiInstance.internalGetDeliveryLabel(hubTrackingNumber, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling InternalDeliveriesApi#internalGetDeliveryLabel");
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
| **403** | Forbidden — insufficient role/scope |  -  |
| **404** | Delivery not found |  -  |

<a id="internalGetDeliveryLabelAsset"></a>
# **internalGetDeliveryLabelAsset**
> File internalGetDeliveryLabelAsset(hubTrackingNumber, filename, acceptLanguage)

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
import com.zipper.delivery.hub.sdk.api.InternalDeliveriesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    InternalDeliveriesApi apiInstance = new InternalDeliveriesApi(defaultClient);
    String hubTrackingNumber = "HUB-0000001000"; // String | Hub tracking number
    String filename = "barcode.png"; // String | Asset filename
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      File result = apiInstance.internalGetDeliveryLabelAsset(hubTrackingNumber, filename, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling InternalDeliveriesApi#internalGetDeliveryLabelAsset");
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
| **403** | Forbidden — insufficient role/scope |  -  |
| **404** | Delivery not found |  -  |

<a id="internalGetHandshakeDelivery"></a>
# **internalGetHandshakeDelivery**
> HubHandshakeDeliveryResponse internalGetHandshakeDelivery(deliveryId, acceptLanguage)

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
import com.zipper.delivery.hub.sdk.api.InternalDeliveriesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    InternalDeliveriesApi apiInstance = new InternalDeliveriesApi(defaultClient);
    UUID deliveryId = UUID.fromString("550e8400-e29b-41d4-a716-446655440000"); // UUID | UUID of the delivery
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      HubHandshakeDeliveryResponse result = apiInstance.internalGetHandshakeDelivery(deliveryId, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling InternalDeliveriesApi#internalGetHandshakeDelivery");
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
| **403** | Forbidden — insufficient role/scope |  -  |
| **404** | Delivery not found |  -  |

<a id="internalGetQuote"></a>
# **internalGetQuote**
> HubDeliveryQuoteResponse internalGetQuote(userId, hubDeliveryQuoteRequest, acceptLanguage)

Get a delivery quote for a user

Returns a price quote and estimated arrival time for the given pickup/dropoff route and delivery type, on behalf of the path user.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.InternalDeliveriesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    InternalDeliveriesApi apiInstance = new InternalDeliveriesApi(defaultClient);
    String userId = "userId_example"; // String | 
    HubDeliveryQuoteRequest hubDeliveryQuoteRequest = new HubDeliveryQuoteRequest(); // HubDeliveryQuoteRequest | 
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      HubDeliveryQuoteResponse result = apiInstance.internalGetQuote(userId, hubDeliveryQuoteRequest, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling InternalDeliveriesApi#internalGetQuote");
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
| **userId** | **String**|  | |
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
| **403** | Forbidden — insufficient role/scope |  -  |

<a id="internalRetryDelivery"></a>
# **internalRetryDelivery**
> HubRetryDeliveryResponse internalRetryDelivery(deliveryId, acceptLanguage)

Retry a delivery

Re-dispatches a delivery that ended in a non-delivered terminal state (FAILED, CANCELLED, or REJECTED) by creating a new provider order under the same delivery.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.InternalDeliveriesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    InternalDeliveriesApi apiInstance = new InternalDeliveriesApi(defaultClient);
    UUID deliveryId = UUID.fromString("550e8400-e29b-41d4-a716-446655440000"); // UUID | UUID of the delivery to retry
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      HubRetryDeliveryResponse result = apiInstance.internalRetryDelivery(deliveryId, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling InternalDeliveriesApi#internalRetryDelivery");
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
| **deliveryId** | **UUID**| UUID of the delivery to retry | |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**HubRetryDeliveryResponse**](HubRetryDeliveryResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Retry accepted; delivery re-dispatched |  -  |
| **403** | Forbidden — insufficient role/scope |  -  |
| **404** | Delivery not found |  -  |
| **409** | Delivery cannot be retried in its current status |  -  |

<a id="internalSearchDeliveries"></a>
# **internalSearchDeliveries**
> PageResponseListHubDeliverySearchDTO internalSearchDeliveries(searchDeliveriesRequest, acceptLanguage)

Search deliveries

Search and filter deliveries with pagination.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.InternalDeliveriesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    InternalDeliveriesApi apiInstance = new InternalDeliveriesApi(defaultClient);
    SearchDeliveriesRequest searchDeliveriesRequest = new SearchDeliveriesRequest(); // SearchDeliveriesRequest | 
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      PageResponseListHubDeliverySearchDTO result = apiInstance.internalSearchDeliveries(searchDeliveriesRequest, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling InternalDeliveriesApi#internalSearchDeliveries");
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
| **403** | Forbidden — insufficient role/scope |  -  |

<a id="internalTrackDelivery"></a>
# **internalTrackDelivery**
> HubDeliveryStatusResponse internalTrackDelivery(hubTrackingNumber, acceptLanguage)

Track delivery by tracking number

Retrieves delivery status and tracking information using the hub tracking number.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.InternalDeliveriesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    InternalDeliveriesApi apiInstance = new InternalDeliveriesApi(defaultClient);
    String hubTrackingNumber = "HUB-0000001000"; // String | Hub tracking number
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      HubDeliveryStatusResponse result = apiInstance.internalTrackDelivery(hubTrackingNumber, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling InternalDeliveriesApi#internalTrackDelivery");
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
| **403** | Forbidden — insufficient role/scope |  -  |
| **404** | Delivery not found |  -  |

<a id="statusesByIds"></a>
# **statusesByIds**
> DeliveryStatusesResponse statusesByIds(deliveryStatusesRequest, acceptLanguage)

Get current status for a list of deliveries

Returns a map of deliveryId -&gt; current status. Missing IDs are omitted. Used by zipper-partner-program reconciliation to detect post-completion cancellations.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.InternalDeliveriesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    InternalDeliveriesApi apiInstance = new InternalDeliveriesApi(defaultClient);
    DeliveryStatusesRequest deliveryStatusesRequest = new DeliveryStatusesRequest(); // DeliveryStatusesRequest | 
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      DeliveryStatusesResponse result = apiInstance.statusesByIds(deliveryStatusesRequest, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling InternalDeliveriesApi#statusesByIds");
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
| **deliveryStatusesRequest** | [**DeliveryStatusesRequest**](DeliveryStatusesRequest.md)|  | |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**DeliveryStatusesResponse**](DeliveryStatusesResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

