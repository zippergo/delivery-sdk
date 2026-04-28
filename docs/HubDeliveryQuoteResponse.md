

# HubDeliveryQuoteResponse

Delivery price quote from a carrier provider

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**deliveryType** | [**DeliveryTypeEnum**](#DeliveryTypeEnum) | Type of delivery |  [optional] |
|**provider** | [**ProviderEnum**](#ProviderEnum) | Carrier provider name |  [optional] |
|**price** | **BigDecimal** | Quoted delivery price |  [optional] |
|**currency** | **String** | Price currency code |  [optional] |
|**estimatedArrivalSeconds** | **Integer** | Estimated time of arrival in seconds |  [optional] |
|**quoteId** | **UUID** | Internal quote identifier for use when creating a delivery |  [optional] |
|**distanceMeters** | **Long** | Distance between pickup and dropoff in meters |  [optional] |
|**durationSeconds** | **Long** | Estimated travel duration in seconds |  [optional] |
|**expiresAt** | **OffsetDateTime** | Quote expiration time — create delivery before this time |  [optional] |



## Enum: DeliveryTypeEnum

| Name | Value |
|---- | -----|
| STORE_IMMEDIATE | &quot;STORE_IMMEDIATE&quot; |
| FOOD_IMMEDIATE | &quot;FOOD_IMMEDIATE&quot; |
| STORE_NEXT_DAY | &quot;STORE_NEXT_DAY&quot; |



## Enum: ProviderEnum

| Name | Value |
|---- | -----|
| ZIPPERG | &quot;ZIPPERG&quot; |
| ZIPPERW | &quot;ZIPPERW&quot; |
| ZIPPERK | &quot;ZIPPERK&quot; |



