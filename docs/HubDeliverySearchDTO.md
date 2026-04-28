

# HubDeliverySearchDTO


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**deliveryId** | **UUID** |  |  [optional] |
|**userId** | **String** |  |  [optional] |
|**deliveryType** | [**DeliveryTypeEnum**](#DeliveryTypeEnum) |  |  [optional] |
|**providerType** | [**ProviderTypeEnum**](#ProviderTypeEnum) |  |  [optional] |
|**status** | [**StatusEnum**](#StatusEnum) |  |  [optional] |
|**hubTrackingNumber** | **String** |  |  [optional] |
|**hubOrderId** | **String** |  |  [optional] |
|**externalOrderId** | **String** |  |  [optional] |
|**providerTrackingId** | **String** |  |  [optional] |
|**providerTrackingUrl** | **String** |  |  [optional] |
|**scheduledPickupTime** | **OffsetDateTime** |  |  [optional] |
|**estimatedArrival** | **OffsetDateTime** |  |  [optional] |
|**createdDate** | **OffsetDateTime** |  |  [optional] |
|**pickupContactName** | **String** |  |  [optional] |
|**pickupContactPhone** | **String** |  |  [optional] |
|**pickupLocation** | [**HubDeliveryLocationDTO**](HubDeliveryLocationDTO.md) |  |  [optional] |
|**dropoffContactName** | **String** |  |  [optional] |
|**dropoffContactPhone** | **String** |  |  [optional] |
|**dropoffLocation** | [**HubDeliveryLocationDTO**](HubDeliveryLocationDTO.md) |  |  [optional] |



## Enum: DeliveryTypeEnum

| Name | Value |
|---- | -----|
| STORE_IMMEDIATE | &quot;STORE_IMMEDIATE&quot; |
| FOOD_IMMEDIATE | &quot;FOOD_IMMEDIATE&quot; |
| STORE_NEXT_DAY | &quot;STORE_NEXT_DAY&quot; |



## Enum: ProviderTypeEnum

| Name | Value |
|---- | -----|
| ZIPPERG | &quot;ZIPPERG&quot; |
| ZIPPERW | &quot;ZIPPERW&quot; |
| ZIPPERK | &quot;ZIPPERK&quot; |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| PENDING | &quot;PENDING&quot; |
| DISPATCHED | &quot;DISPATCHED&quot; |
| PROVIDER_ACCEPTED | &quot;PROVIDER_ACCEPTED&quot; |
| ASSIGNED | &quot;ASSIGNED&quot; |
| READY_FOR_PICKUP | &quot;READY_FOR_PICKUP&quot; |
| PICKED_UP | &quot;PICKED_UP&quot; |
| IN_TRANSIT | &quot;IN_TRANSIT&quot; |
| DELIVERED | &quot;DELIVERED&quot; |
| CANCELLED | &quot;CANCELLED&quot; |
| FAILED | &quot;FAILED&quot; |
| REJECTED | &quot;REJECTED&quot; |
| AWAITING_DRIVER | &quot;AWAITING_DRIVER&quot; |



