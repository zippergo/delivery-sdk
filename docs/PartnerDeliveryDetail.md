

# PartnerDeliveryDetail

Full detail of one of the partner's deliveries

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**deliveryId** | **UUID** |  |  [optional] |
|**hubTrackingNumber** | **String** |  |  [optional] |
|**hubOrderId** | **String** |  |  [optional] |
|**status** | **String** |  |  [optional] |
|**deliveryType** | **String** |  |  [optional] |
|**providerType** | **String** |  |  [optional] |
|**merchantId** | **UUID** |  |  [optional] |
|**merchantName** | **String** |  |  [optional] |
|**businessType** | **String** |  |  [optional] |
|**externalOrderId** | **String** |  |  [optional] |
|**providerTrackingId** | **String** |  |  [optional] |
|**providerTrackingUrl** | **String** |  |  [optional] |
|**scheduledPickupTime** | **OffsetDateTime** |  |  [optional] |
|**estimatedArrival** | **OffsetDateTime** |  |  [optional] |
|**createdDate** | **OffsetDateTime** |  |  [optional] |
|**pickupContactName** | **String** |  |  [optional] |
|**pickupContactPhone** | **String** |  |  [optional] |
|**pickupLocation** | [**PartnerDeliveryLocation**](PartnerDeliveryLocation.md) |  |  [optional] |
|**dropoffContactName** | **String** |  |  [optional] |
|**dropoffContactPhone** | **String** |  |  [optional] |
|**dropoffLocation** | [**PartnerDeliveryLocation**](PartnerDeliveryLocation.md) |  |  [optional] |
|**route** | **List&lt;List&lt;Double&gt;&gt;** | Road-network route as GeoJSON [longitude, latitude] pairs (null if not routed yet) |  [optional] |
|**distanceMeters** | **Long** | Road-network distance between pickup and dropoff in meters (null if not routed) |  [optional] |
|**courier** | [**PartnerCourier**](PartnerCourier.md) | Currently-assigned courier (null if none assigned yet) |  [optional] |



