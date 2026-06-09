# InternalAnalyticsApi

All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**countDeliveryAnalytics**](InternalAnalyticsApi.md#countDeliveryAnalytics) | **GET** /delivery/v1/internal/analytics/deliveries/counts | Aggregate delivery counts per owner per time bucket |
| [**exportDeliveryAnalytics**](InternalAnalyticsApi.md#exportDeliveryAnalytics) | **GET** /delivery/v1/internal/analytics/deliveries/export | Export delivery analytics records (cursor-paginated) |


<a id="countDeliveryAnalytics"></a>
# **countDeliveryAnalytics**
> AnalyticsCountsResponse countDeliveryAnalytics(from, to, granularity, timezone, acceptLanguage)

Aggregate delivery counts per owner per time bucket

Returns authoritative per-ownerUserId, per-bucket delivery counts and COD sums for reconciliation. Buckets are timezone-aware (date_trunc in the requested timezone) to match the analytics service&#39;s ClickHouse buckets.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.InternalAnalyticsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    InternalAnalyticsApi apiInstance = new InternalAnalyticsApi(defaultClient);
    OffsetDateTime from = OffsetDateTime.parse("2025-01-01T00:00:00Z"); // OffsetDateTime | Inclusive start of the time window (ISO-8601 instant)
    OffsetDateTime to = OffsetDateTime.parse("2025-02-01T00:00:00Z"); // OffsetDateTime | Exclusive end of the time window (ISO-8601 instant)
    String granularity = "day"; // String | Bucket granularity: hour, day, week, or month
    String timezone = "Asia/Jerusalem"; // String | IANA timezone for bucket boundaries (e.g. Asia/Jerusalem)
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      AnalyticsCountsResponse result = apiInstance.countDeliveryAnalytics(from, to, granularity, timezone, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling InternalAnalyticsApi#countDeliveryAnalytics");
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
| **from** | **OffsetDateTime**| Inclusive start of the time window (ISO-8601 instant) | |
| **to** | **OffsetDateTime**| Exclusive end of the time window (ISO-8601 instant) | |
| **granularity** | **String**| Bucket granularity: hour, day, week, or month | [optional] [default to day] |
| **timezone** | **String**| IANA timezone for bucket boundaries (e.g. Asia/Jerusalem) | [optional] [default to Asia/Jerusalem] |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**AnalyticsCountsResponse**](AnalyticsCountsResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Aggregate counts |  -  |
| **400** | Invalid parameters |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient role/scope |  -  |

<a id="exportDeliveryAnalytics"></a>
# **exportDeliveryAnalytics**
> AnalyticsExportResponse exportDeliveryAnalytics(from, to, cursor, limit, acceptLanguage)

Export delivery analytics records (cursor-paginated)

Returns a stable-ordered page of delivery analytics records for deliveries with createdDate in [from, to). Uses keyset pagination — pass nextCursor from the previous response as the cursor param. nextCursor&#x3D;null means last page.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.InternalAnalyticsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    InternalAnalyticsApi apiInstance = new InternalAnalyticsApi(defaultClient);
    OffsetDateTime from = OffsetDateTime.parse("2025-01-01T00:00:00Z"); // OffsetDateTime | Inclusive start of the time window (ISO-8601 instant)
    OffsetDateTime to = OffsetDateTime.parse("2025-02-01T00:00:00Z"); // OffsetDateTime | Exclusive end of the time window (ISO-8601 instant)
    String cursor = "cursor_example"; // String | Opaque continuation cursor from a previous response (omit for first page)
    Integer limit = 500; // Integer | Page size; default 500, max 2000
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      AnalyticsExportResponse result = apiInstance.exportDeliveryAnalytics(from, to, cursor, limit, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling InternalAnalyticsApi#exportDeliveryAnalytics");
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
| **from** | **OffsetDateTime**| Inclusive start of the time window (ISO-8601 instant) | |
| **to** | **OffsetDateTime**| Exclusive end of the time window (ISO-8601 instant) | |
| **cursor** | **String**| Opaque continuation cursor from a previous response (omit for first page) | [optional] |
| **limit** | **Integer**| Page size; default 500, max 2000 | [optional] [default to 500] |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**AnalyticsExportResponse**](AnalyticsExportResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Page of analytics records |  -  |
| **400** | Invalid parameters |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient role/scope |  -  |

