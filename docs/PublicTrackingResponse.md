

# PublicTrackingResponse


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**trackingNumber** | **String** |  |  [optional] |
|**hubBarcode** | **String** |  |  [optional] |
|**packageDetails** | [**PublicPackageDetails**](PublicPackageDetails.md) |  |  [optional] |
|**status** | [**StatusEnum**](#StatusEnum) |  |  [optional] |
|**deliveryType** | **String** |  |  [optional] |
|**estimatedPickupAt** | **OffsetDateTime** |  |  [optional] |
|**estimatedDropoffAt** | **OffsetDateTime** |  |  [optional] |
|**pickup** | [**PublicPickupInfo**](PublicPickupInfo.md) |  |  [optional] |
|**dropoff** | [**PublicDropoffInfo**](PublicDropoffInfo.md) |  |  [optional] |
|**courier** | [**PublicCourierInfo**](PublicCourierInfo.md) |  |  [optional] |
|**statusTimeline** | [**List&lt;PublicStatusEvent&gt;**](PublicStatusEvent.md) |  |  [optional] |
|**items** | [**List&lt;PublicItemInfo&gt;**](PublicItemInfo.md) |  |  [optional] |
|**proofOfDeliveryUrl** | **String** |  |  [optional] |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| CONFIRMED | &quot;CONFIRMED&quot; |
| LOOKING_FOR_DRIVER | &quot;LOOKING_FOR_DRIVER&quot; |
| DRIVER_ASSIGNED | &quot;DRIVER_ASSIGNED&quot; |
| PREPARING | &quot;PREPARING&quot; |
| PICKED_UP | &quot;PICKED_UP&quot; |
| ON_THE_WAY | &quot;ON_THE_WAY&quot; |
| DELIVERED | &quot;DELIVERED&quot; |
| CANCELLED | &quot;CANCELLED&quot; |
| UNSUCCESSFUL | &quot;UNSUCCESSFUL&quot; |



