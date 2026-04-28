

# HubDeliveryStatusResponse

Full delivery status including tracking and history

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**deliveryId** | **UUID** | Unique delivery identifier |  [optional] |
|**deliveryType** | [**DeliveryTypeEnum**](#DeliveryTypeEnum) | Type of delivery |  [optional] |
|**status** | [**StatusEnum**](#StatusEnum) | Current delivery status |  [optional] |
|**provider** | [**ProviderEnum**](#ProviderEnum) | Carrier provider handling the delivery |  [optional] |
|**providerTrackingId** | **String** | Tracking ID from the carrier provider |  [optional] |
|**hubTrackingNumber** | **String** | Hub tracking number |  [optional] |
|**hubOrderId** | **String** | Hub order ID |  [optional] |
|**hubBarcode** | **String** | Hub barcode |  [optional] |
|**estimatedArrival** | **OffsetDateTime** | Estimated arrival time |  [optional] |
|**trackingUrl** | **String** | Public tracking URL for the delivery recipient |  [optional] |
|**statusHistory** | [**List&lt;HubStatusEventDTO&gt;**](HubStatusEventDTO.md) | Chronological list of status changes |  [optional] |
|**proofOfDeliveryUrl** | **String** | URL to the proof-of-delivery image (available after delivery) |  [optional] |
|**items** | [**List&lt;HubItemDTO&gt;**](HubItemDTO.md) | Items included in the delivery |  [optional] |
|**pickupContactName** | **String** | Pickup contact name |  [optional] |
|**pickupContactPhone** | **String** | Pickup contact phone number |  [optional] |
|**pickupEmail** | **String** | Pickup contact email |  [optional] |
|**pickupNotes** | **String** | Pickup notes or instructions |  [optional] |
|**pickupReferenceNumber** | **String** | Pickup reference number used by the driver to collect the package (e.g., invoice number, warehouse release code) |  [optional] |
|**pickupLocation** | [**HubDeliveryLocationDTO**](HubDeliveryLocationDTO.md) | Pickup location details |  [optional] |
|**dropoffContactName** | **String** | Dropoff contact name |  [optional] |
|**dropoffContactPhone** | **String** | Dropoff contact phone number |  [optional] |
|**dropoffEmail** | **String** | Dropoff contact email |  [optional] |
|**dropoffNotes** | **String** | Dropoff notes or instructions |  [optional] |
|**dropoffLocation** | [**HubDeliveryLocationDTO**](HubDeliveryLocationDTO.md) | Dropoff location details |  [optional] |



## Enum: DeliveryTypeEnum

| Name | Value |
|---- | -----|
| STORE_IMMEDIATE | &quot;STORE_IMMEDIATE&quot; |
| FOOD_IMMEDIATE | &quot;FOOD_IMMEDIATE&quot; |
| STORE_NEXT_DAY | &quot;STORE_NEXT_DAY&quot; |



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



## Enum: ProviderEnum

| Name | Value |
|---- | -----|
| ZIPPERG | &quot;ZIPPERG&quot; |
| ZIPPERW | &quot;ZIPPERW&quot; |
| ZIPPERK | &quot;ZIPPERK&quot; |



