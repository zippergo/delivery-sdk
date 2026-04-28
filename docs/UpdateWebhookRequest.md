

# UpdateWebhookRequest

Request to update an existing webhook subscription. All fields are optional; only provided fields will be updated.

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**callbackUrl** | **String** | HTTPS URL that will receive webhook events |  [optional] |
|**enabled** | **Boolean** | Whether the webhook is active |  [optional] |
|**eventTypes** | **List&lt;String&gt;** | Event types to subscribe to |  [optional] |
|**callbackConfig** | [**CallbackConfigDTO**](CallbackConfigDTO.md) | Optional callback configuration (retry policy) |  [optional] |



