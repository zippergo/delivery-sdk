

# WebhookDTO

Webhook subscription details

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Long** | Webhook ID |  [optional] |
|**callbackUrl** | **String** | Callback URL receiving events |  [optional] |
|**enabled** | **Boolean** | Whether the webhook is active |  [optional] |
|**eventTypes** | **List&lt;String&gt;** | Subscribed event types |  [optional] |
|**callbackConfig** | [**CallbackConfigDTO**](CallbackConfigDTO.md) | Callback configuration (retry policy) |  [optional] |
|**createdAt** | **OffsetDateTime** | Creation timestamp |  [optional] |
|**updatedAt** | **OffsetDateTime** | Last update timestamp |  [optional] |
|**clientSecret** | **String** | HMAC secret for verifying webhook signatures (only returned on creation) |  [optional] |



