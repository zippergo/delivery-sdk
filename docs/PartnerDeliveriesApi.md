# PartnerDeliveriesApi

All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**partnerDeliveries**](PartnerDeliveriesApi.md#partnerDeliveries) | **GET** /delivery/v1/partner/deliveries | List the partner&#39;s deliveries |
| [**partnerDelivery**](PartnerDeliveriesApi.md#partnerDelivery) | **GET** /delivery/v1/partner/deliveries/{deliveryId} | Get one of the partner&#39;s deliveries |
| [**partnerDeliveryLabelAsset**](PartnerDeliveriesApi.md#partnerDeliveryLabelAsset) | **GET** /delivery/v1/partner/deliveries/{deliveryId}/label/{filename} | Download a delivery label asset |
| [**partnerDeliveryStatusCounts**](PartnerDeliveriesApi.md#partnerDeliveryStatusCounts) | **GET** /delivery/v1/partner/deliveries/status-counts | Delivery count per status for the partner |
| [**partnerMerchantDeliveries**](PartnerDeliveriesApi.md#partnerMerchantDeliveries) | **GET** /delivery/v1/partner/merchants/{merchantId}/deliveries | List a merchant&#39;s deliveries |
| [**partnerRecentDeliveries**](PartnerDeliveriesApi.md#partnerRecentDeliveries) | **GET** /delivery/v1/partner/recent-deliveries | Get the partner&#39;s recent deliveries |
| [**partnerSearchDeliveries**](PartnerDeliveriesApi.md#partnerSearchDeliveries) | **POST** /delivery/v1/partner/deliveries/search | Search the partner&#39;s deliveries |


<a id="partnerDeliveries"></a>
# **partnerDeliveries**
> PageResponseListPartnerDeliveryRow partnerDeliveries(page, size, acceptLanguage)

List the partner&#39;s deliveries

Returns a page of all deliveries across the authenticated partner&#39;s merchants (newest first), enriched with each delivery&#39;s owning merchant. Backs the partner-portal deliveries list.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.PartnerDeliveriesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    PartnerDeliveriesApi apiInstance = new PartnerDeliveriesApi(defaultClient);
    Integer page = 1; // Integer | 1-based page number (default 1)
    Integer size = 20; // Integer | Items per page (1-1000, default 20)
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      PageResponseListPartnerDeliveryRow result = apiInstance.partnerDeliveries(page, size, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling PartnerDeliveriesApi#partnerDeliveries");
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
| **page** | **Integer**| 1-based page number (default 1) | [optional] [default to 1] |
| **size** | **Integer**| Items per page (1-1000, default 20) | [optional] [default to 20] |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**PageResponseListPartnerDeliveryRow**](PageResponseListPartnerDeliveryRow.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

<a id="partnerDelivery"></a>
# **partnerDelivery**
> PartnerDeliveryDetail partnerDelivery(deliveryId, acceptLanguage)

Get one of the partner&#39;s deliveries

Returns the detail of a single delivery owned by one of the authenticated partner&#39;s merchants. 404 if the delivery does not exist or is not the partner&#39;s.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.PartnerDeliveriesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    PartnerDeliveriesApi apiInstance = new PartnerDeliveriesApi(defaultClient);
    UUID deliveryId = UUID.randomUUID(); // UUID | 
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      PartnerDeliveryDetail result = apiInstance.partnerDelivery(deliveryId, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling PartnerDeliveriesApi#partnerDelivery");
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

[**PartnerDeliveryDetail**](PartnerDeliveryDetail.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Delivery detail returned |  -  |
| **404** | Not found or not owned |  -  |

<a id="partnerDeliveryLabelAsset"></a>
# **partnerDeliveryLabelAsset**
> File partnerDeliveryLabelAsset(deliveryId, filename, acceptLanguage)

Download a delivery label asset

Serves a label asset (barcode.png, qrcode.png, or label.pdf) for a delivery owned by one of the authenticated partner&#39;s merchants. 404 if the delivery is not the partner&#39;s, 400 for an unknown filename.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.PartnerDeliveriesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    PartnerDeliveriesApi apiInstance = new PartnerDeliveriesApi(defaultClient);
    UUID deliveryId = UUID.randomUUID(); // UUID | 
    String filename = "barcode.png"; // String | Asset filename
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      File result = apiInstance.partnerDeliveryLabelAsset(deliveryId, filename, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling PartnerDeliveriesApi#partnerDeliveryLabelAsset");
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
| **200** | OK |  -  |

<a id="partnerDeliveryStatusCounts"></a>
# **partnerDeliveryStatusCounts**
> Map&lt;String, Long&gt; partnerDeliveryStatusCounts(acceptLanguage)

Delivery count per status for the partner

Per-HubDeliveryStatus count across the authenticated partner&#39;s merchants&#39; deliveries. Drives the partner deliveries list&#39;s status-tab counts. Owner-scoped; statuses with no rows are omitted.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.PartnerDeliveriesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    PartnerDeliveriesApi apiInstance = new PartnerDeliveriesApi(defaultClient);
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      Map<String, Long> result = apiInstance.partnerDeliveryStatusCounts(acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling PartnerDeliveriesApi#partnerDeliveryStatusCounts");
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
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

**Map&lt;String, Long&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

<a id="partnerMerchantDeliveries"></a>
# **partnerMerchantDeliveries**
> PageResponseListMerchantDeliveryRow partnerMerchantDeliveries(merchantId, page, size, acceptLanguage)

List a merchant&#39;s deliveries

Returns a page of the merchant&#39;s deliveries (newest first) for the merchant detail-page Deliveries tab. 404 if the merchant is not the partner&#39;s.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.PartnerDeliveriesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    PartnerDeliveriesApi apiInstance = new PartnerDeliveriesApi(defaultClient);
    UUID merchantId = UUID.randomUUID(); // UUID | 
    Integer page = 1; // Integer | 
    Integer size = 20; // Integer | 
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      PageResponseListMerchantDeliveryRow result = apiInstance.partnerMerchantDeliveries(merchantId, page, size, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling PartnerDeliveriesApi#partnerMerchantDeliveries");
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
| **merchantId** | **UUID**|  | |
| **page** | **Integer**|  | [optional] [default to 1] |
| **size** | **Integer**|  | [optional] [default to 20] |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**PageResponseListMerchantDeliveryRow**](PageResponseListMerchantDeliveryRow.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

<a id="partnerRecentDeliveries"></a>
# **partnerRecentDeliveries**
> List&lt;RecentDeliveryResponse&gt; partnerRecentDeliveries(limit, acceptLanguage)

Get the partner&#39;s recent deliveries

Returns the most-recent deliveries across all of the authenticated partner&#39;s merchants (newest first), enriched with each delivery&#39;s merchant business name. Backs the partner dashboard&#39;s \&quot;Recent activity\&quot; feed.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.PartnerDeliveriesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    PartnerDeliveriesApi apiInstance = new PartnerDeliveriesApi(defaultClient);
    Integer limit = 10; // Integer | Max rows to return (1-50, default 10)
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      List<RecentDeliveryResponse> result = apiInstance.partnerRecentDeliveries(limit, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling PartnerDeliveriesApi#partnerRecentDeliveries");
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
| **limit** | **Integer**| Max rows to return (1-50, default 10) | [optional] [default to 10] |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**List&lt;RecentDeliveryResponse&gt;**](RecentDeliveryResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

<a id="partnerSearchDeliveries"></a>
# **partnerSearchDeliveries**
> PageResponseListPartnerDeliveryRow partnerSearchDeliveries(searchDeliveriesRequest, acceptLanguage)

Search the partner&#39;s deliveries

Free-text search + filter/sort/paginate across all deliveries of the authenticated partner&#39;s merchants. Server-side; the result set is always scoped to the partner&#39;s merchants regardless of the request body. Backs the partner-portal global search.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.PartnerDeliveriesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    PartnerDeliveriesApi apiInstance = new PartnerDeliveriesApi(defaultClient);
    SearchDeliveriesRequest searchDeliveriesRequest = new SearchDeliveriesRequest(); // SearchDeliveriesRequest | 
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      PageResponseListPartnerDeliveryRow result = apiInstance.partnerSearchDeliveries(searchDeliveriesRequest, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling PartnerDeliveriesApi#partnerSearchDeliveries");
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

[**PageResponseListPartnerDeliveryRow**](PageResponseListPartnerDeliveryRow.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

