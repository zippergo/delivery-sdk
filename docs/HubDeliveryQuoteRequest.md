

# HubDeliveryQuoteRequest

Request to get a delivery price quote

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**deliveryType** | [**DeliveryTypeEnum**](#DeliveryTypeEnum) | Type of delivery |  |
|**pickup** | [**HubContactDTO**](HubContactDTO.md) | Pickup contact and location. Optional when pickupLocationCode is provided. |  [optional] |
|**dropoff** | [**HubContactDTO**](HubContactDTO.md) | Dropoff contact and location |  |
|**items** | [**List&lt;HubItemDTO&gt;**](HubItemDTO.md) | List of items for weight/size estimation |  [optional] |
|**scheduledAt** | **OffsetDateTime** | Scheduled pickup time (null for immediate) |  [optional] |
|**pickupLocationCode** | **String** | Optional pickup location code. When set, pickup contact and address are auto-filled from the location. |  [optional] |



## Enum: DeliveryTypeEnum

| Name | Value |
|---- | -----|
| STORE_IMMEDIATE | &quot;STORE_IMMEDIATE&quot; |
| FOOD_IMMEDIATE | &quot;FOOD_IMMEDIATE&quot; |
| STORE_NEXT_DAY | &quot;STORE_NEXT_DAY&quot; |



