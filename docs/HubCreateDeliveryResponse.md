

# HubCreateDeliveryResponse

Response after successfully creating a delivery

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**deliveryId** | **UUID** | Unique delivery identifier |  [optional] |
|**deliveryType** | [**DeliveryTypeEnum**](#DeliveryTypeEnum) | Type of delivery |  [optional] |
|**status** | **String** | Current delivery status |  [optional] |
|**hubTrackingNumber** | **String** | Hub-assigned tracking number |  [optional] |
|**trackingUrl** | **String** | Public tracking URL for the delivery |  [optional] |



## Enum: DeliveryTypeEnum

| Name | Value |
|---- | -----|
| STORE_IMMEDIATE | &quot;STORE_IMMEDIATE&quot; |
| FOOD_IMMEDIATE | &quot;FOOD_IMMEDIATE&quot; |
| STORE_NEXT_DAY | &quot;STORE_NEXT_DAY&quot; |



