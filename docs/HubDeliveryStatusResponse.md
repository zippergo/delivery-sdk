

# HubDeliveryStatusResponse

Full delivery status including tracking and history

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**deliveryId** | **UUID** | Unique delivery identifier |  [optional] |
|**userId** | **String** | Owner (merchant/user) id — admin views only |  [optional] |
|**createdDate** | **OffsetDateTime** | When the delivery was created — admin views only |  [optional] |
|**courier** | [**HubDeliveryCourierDTO**](HubDeliveryCourierDTO.md) | Currently-assigned courier — admin views only |  [optional] |
|**dispatchAttempts** | [**List&lt;HubDispatchAttemptDTO&gt;**](HubDispatchAttemptDTO.md) | Provider dispatch attempts (chronological) — admin views only |  [optional] |
|**pickupSite** | [**HubPickupLocationDTO**](HubPickupLocationDTO.md) | Pickup site (warehouse/store/hub) the delivery was created from — admin views only |  [optional] |
|**externalOrderId** | **String** | Merchant&#39;s external order id — admin views only |  [optional] |
|**merchantName** | **String** | Owner merchant business name (from partner_merchant mirror) — admin views only |  [optional] |
|**businessType** | **String** | Owner merchant business type (food/retail) — admin views only |  [optional] |
|**recipientName** | **String** | Recipient name — admin views only |  [optional] |
|**recipientPhone** | **String** | Recipient phone — admin views only |  [optional] |
|**recipientEmail** | **String** | Recipient email — admin views only |  [optional] |
|**pinCode** | **String** | PIN handshake code — admin views only |  [optional] |
|**pinRequired** | **Boolean** | Whether a PIN handshake is required — admin views only |  [optional] |
|**smsNotifications** | **Boolean** | Whether SMS notifications are enabled — admin views only |  [optional] |
|**scheduledPickupTime** | **OffsetDateTime** | Scheduled pickup time (null &#x3D; immediate) — admin views only |  [optional] |
|**originalQuotedEta** | **OffsetDateTime** | Originally quoted ETA — admin views only |  [optional] |
|**dispatchRetryCount** | **Integer** | Dispatch retry count — admin views only |  [optional] |
|**maxDispatchRetries** | **Integer** | Max dispatch retries — admin views only |  [optional] |
|**stuckPollCount** | **Integer** | Stuck poll count — admin views only |  [optional] |
|**nextRetryAt** | **OffsetDateTime** | Next scheduled retry — admin views only |  [optional] |
|**lastPolledAt** | **OffsetDateTime** | Last poll time — admin views only |  [optional] |
|**providerData** | **Map&lt;String, String&gt;** | Raw provider data — admin views only |  [optional] |
|**idempotencyKey** | **String** | Idempotency key — admin views only |  [optional] |
|**quoteId** | **UUID** | Quote id — admin views only |  [optional] |
|**createdBy** | **String** | Created by (audit) — admin views only |  [optional] |
|**lastModifiedDate** | **OffsetDateTime** | Last modified time (audit) — admin views only |  [optional] |
|**lastModifiedBy** | **String** | Last modified by (audit) — admin views only |  [optional] |
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
|**distanceMeters** | **Long** | Internal road-network distance between pickup and dropoff in meters |  [optional] |
|**durationSeconds** | **Long** | Internal estimated travel duration in seconds |  [optional] |
|**routeGeometry** | [**GeoJsonLineString**](GeoJsonLineString.md) | Internal route geometry (GeoJSON LineString) for drawing the route on a map |  [optional] |
|**routeMeta** | [**RouteMeta**](RouteMeta.md) | Additional internal routing metadata (weight, snap distances, road summary) |  [optional] |



## Enum: DeliveryTypeEnum

| Name | Value |
|---- | -----|
| STORE_IMMEDIATE | &quot;STORE_IMMEDIATE&quot; |
| FOOD_IMMEDIATE | &quot;FOOD_IMMEDIATE&quot; |
| STORE_NEXT_DAY | &quot;STORE_NEXT_DAY&quot; |
| PASSENGER_TRANSPORT | &quot;PASSENGER_TRANSPORT&quot; |
| INTERNATIONAL_EXPORT | &quot;INTERNATIONAL_EXPORT&quot; |



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
| ZIPPERGP | &quot;ZIPPERGP&quot; |
| ZIPPERU | &quot;ZIPPERU&quot; |



