

# HubDeliveryCourierDTO

Currently-assigned courier (admin views only)

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**providerDriverId** | **String** |  |  [optional] |
|**name** | **String** |  |  [optional] |
|**phone** | **String** |  |  [optional] |
|**photoUrl** | **String** |  |  [optional] |
|**rating** | **Double** |  |  [optional] |
|**vehicleType** | [**VehicleTypeEnum**](#VehicleTypeEnum) |  |  [optional] |
|**rawVehicleType** | **String** |  |  [optional] |
|**licensePlate** | **String** |  |  [optional] |
|**make** | **String** |  |  [optional] |
|**model** | **String** |  |  [optional] |
|**color** | **String** |  |  [optional] |
|**lat** | **Double** |  |  [optional] |
|**lng** | **Double** |  |  [optional] |
|**assignedAt** | **OffsetDateTime** |  |  [optional] |



## Enum: VehicleTypeEnum

| Name | Value |
|---- | -----|
| BICYCLE | &quot;BICYCLE&quot; |
| MOTORCYCLE | &quot;MOTORCYCLE&quot; |
| CAR | &quot;CAR&quot; |
| VAN | &quot;VAN&quot; |
| TRUCK | &quot;TRUCK&quot; |
| ON_FOOT | &quot;ON_FOOT&quot; |
| UNKNOWN | &quot;UNKNOWN&quot; |



