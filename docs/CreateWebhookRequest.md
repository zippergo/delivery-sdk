

# CreateWebhookRequest

Request to create or update a webhook subscription

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**callbackUrl** | **String** | HTTPS URL that will receive webhook events |  |
|**enabled** | **Boolean** | Whether the webhook is active |  [optional] |
|**eventTypes** | **List&lt;String&gt;** | Event types to subscribe to |  |
|**callbackConfig** | [**CallbackConfigDTO**](CallbackConfigDTO.md) | Optional callback configuration (retry policy) |  [optional] |
|**webhookSecret** | **String** | Optional webhook secret. If not provided, one will be auto-generated. |  [optional] |



