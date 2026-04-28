# WebhooksApi

All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createWebhook**](WebhooksApi.md#createWebhook) | **POST** /delivery/v1/webhooks | Create a webhook |
| [**deleteWebhookById**](WebhooksApi.md#deleteWebhookById) | **DELETE** /delivery/v1/webhooks/{id} | Delete a specific webhook |
| [**listWebhooks**](WebhooksApi.md#listWebhooks) | **GET** /delivery/v1/webhooks | List all webhooks |
| [**testWebhook**](WebhooksApi.md#testWebhook) | **POST** /delivery/v1/webhooks/test | Send a test webhook event |
| [**updateWebhook**](WebhooksApi.md#updateWebhook) | **PUT** /delivery/v1/webhooks/{id} | Update a webhook |


<a id="createWebhook"></a>
# **createWebhook**
> WebhookDTO createWebhook(createWebhookRequest, acceptLanguage)

Create a webhook

Registers a new webhook for the current user. Returns 409 Conflict if a webhook with the same callback URL already exists.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.WebhooksApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    WebhooksApi apiInstance = new WebhooksApi(defaultClient);
    CreateWebhookRequest createWebhookRequest = new CreateWebhookRequest(); // CreateWebhookRequest | 
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      WebhookDTO result = apiInstance.createWebhook(createWebhookRequest, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling WebhooksApi#createWebhook");
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
| **createWebhookRequest** | [**CreateWebhookRequest**](CreateWebhookRequest.md)|  | |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**WebhookDTO**](WebhookDTO.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Webhook created |  -  |
| **400** | Invalid request parameters |  -  |
| **403** | Forbidden — insufficient permissions |  -  |
| **409** | Webhook with this callback URL already exists |  -  |
| **500** | Internal server error |  -  |

<a id="deleteWebhookById"></a>
# **deleteWebhookById**
> deleteWebhookById(id, acceptLanguage)

Delete a specific webhook

Removes a specific webhook subscription by ID for the current user.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.WebhooksApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    WebhooksApi apiInstance = new WebhooksApi(defaultClient);
    Long id = 1L; // Long | Webhook ID
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      apiInstance.deleteWebhookById(id, acceptLanguage);
    } catch (ApiException e) {
      System.err.println("Exception when calling WebhooksApi#deleteWebhookById");
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
| **id** | **Long**| Webhook ID | |
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
| **204** | Webhook deleted |  -  |
| **403** | Forbidden — insufficient permissions |  -  |
| **404** | Webhook not found |  -  |
| **500** | Internal server error |  -  |

<a id="listWebhooks"></a>
# **listWebhooks**
> List&lt;WebhookDTO&gt; listWebhooks(acceptLanguage)

List all webhooks

Returns all webhook subscriptions for the current user.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.WebhooksApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    WebhooksApi apiInstance = new WebhooksApi(defaultClient);
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      List<WebhookDTO> result = apiInstance.listWebhooks(acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling WebhooksApi#listWebhooks");
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

[**List&lt;WebhookDTO&gt;**](WebhookDTO.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of webhooks |  -  |
| **403** | Forbidden — insufficient permissions |  -  |
| **500** | Internal server error |  -  |

<a id="testWebhook"></a>
# **testWebhook**
> testWebhook(acceptLanguage, testWebhookRequest)

Send a test webhook event

Publishes a test event to all registered webhooks for the current user.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.WebhooksApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    WebhooksApi apiInstance = new WebhooksApi(defaultClient);
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    TestWebhookRequest testWebhookRequest = new TestWebhookRequest(); // TestWebhookRequest | 
    try {
      apiInstance.testWebhook(acceptLanguage, testWebhookRequest);
    } catch (ApiException e) {
      System.err.println("Exception when calling WebhooksApi#testWebhook");
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
| **testWebhookRequest** | [**TestWebhookRequest**](TestWebhookRequest.md)|  | [optional] |

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
| **202** | Test event accepted for delivery |  -  |
| **403** | Forbidden — insufficient permissions |  -  |
| **404** | No webhook registered for this user |  -  |
| **500** | Internal server error |  -  |

<a id="updateWebhook"></a>
# **updateWebhook**
> WebhookDTO updateWebhook(id, updateWebhookRequest, acceptLanguage)

Update a webhook

Updates an existing webhook subscription by ID for the current user.

### Example
```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.WebhooksApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    WebhooksApi apiInstance = new WebhooksApi(defaultClient);
    Long id = 1L; // Long | Webhook ID
    UpdateWebhookRequest updateWebhookRequest = new UpdateWebhookRequest(); // UpdateWebhookRequest | 
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      WebhookDTO result = apiInstance.updateWebhook(id, updateWebhookRequest, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling WebhooksApi#updateWebhook");
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
| **id** | **Long**| Webhook ID | |
| **updateWebhookRequest** | [**UpdateWebhookRequest**](UpdateWebhookRequest.md)|  | |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**WebhookDTO**](WebhookDTO.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Webhook updated |  -  |
| **400** | Invalid request parameters |  -  |
| **403** | Forbidden — insufficient permissions |  -  |
| **404** | Webhook not found |  -  |
| **409** | Webhook with this callback URL already exists |  -  |
| **500** | Internal server error |  -  |

