

# HubCreateDeliveryRequest

Request to create a new delivery order. A quoteId from a prior quote request is required; pickup and dropoff must match the quoted addresses.

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**quoteId** | **UUID** | Quote ID from a prior quote request |  |
|**deliveryType** | [**DeliveryTypeEnum**](#DeliveryTypeEnum) | Type of delivery |  |
|**externalOrderId** | **String** | Your external order reference ID |  [optional] |
|**pickup** | [**HubContactDTO**](HubContactDTO.md) | Pickup contact and location. Optional when pickupLocationCode is provided. |  [optional] |
|**dropoff** | [**HubContactDTO**](HubContactDTO.md) | Dropoff contact and location |  |
|**items** | [**List&lt;HubItemDTO&gt;**](HubItemDTO.md) | List of items to deliver |  [optional] |
|**codAmount** | **BigDecimal** | Cash-on-delivery amount (null if not COD) |  [optional] |
|**scheduledAt** | **OffsetDateTime** | Scheduled pickup time (null for immediate dispatch) |  [optional] |
|**smsNotifications** | **Boolean** | Content for the SMS message(s) which will be sent to the recipient at certain stages of the delivery.  This is an optional feature for communicating the tracking link to the recipient. |  [optional] |
|**handshake** | [**HandshakeDeliveryDTO**](HandshakeDeliveryDTO.md) | Handshake details for secure delivery. Enables PIN verification on delivery. |  [optional] |
|**recipient** | [**RecipientDeliveryDTO**](RecipientDeliveryDTO.md) | Details of the recipient who is going to receive the delivery |  [optional] |
|**providerData** | [**ProviderDataDTO**](ProviderDataDTO.md) | Provider-specific account data. Required for STORE_NEXT_DAY delivery type. |  [optional] |
|**pickupLocationCode** | **String** | Optional pickup location code. When set, pickup contact and address are auto-filled from the location. |  [optional] |



## Enum: DeliveryTypeEnum

| Name | Value |
|---- | -----|
| STORE_IMMEDIATE | &quot;STORE_IMMEDIATE&quot; |
| FOOD_IMMEDIATE | &quot;FOOD_IMMEDIATE&quot; |
| STORE_NEXT_DAY | &quot;STORE_NEXT_DAY&quot; |



