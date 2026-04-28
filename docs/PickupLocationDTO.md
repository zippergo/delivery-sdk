

# PickupLocationDTO

Pickup location details

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **UUID** | Location ID |  [optional] |
|**name** | **String** | Display name |  [optional] |
|**code** | **String** | Unique code |  [optional] |
|**type** | [**TypeEnum**](#TypeEnum) | Location type |  [optional] |
|**status** | [**StatusEnum**](#StatusEnum) | Location status |  [optional] |
|**addressLine1** | **String** | Primary address line |  [optional] |
|**addressLine2** | **String** | Secondary address line |  [optional] |
|**houseNumber** | **String** | House number |  [optional] |
|**entranceFloor** | **String** | Entrance or floor |  [optional] |
|**city** | **String** | City |  [optional] |
|**region** | **String** | Region or state |  [optional] |
|**postalCode** | **String** | Postal code |  [optional] |
|**countryCode** | **String** | Country code |  [optional] |
|**latitude** | **Double** | Latitude |  [optional] |
|**longitude** | **Double** | Longitude |  [optional] |
|**contactName** | **String** | Contact name |  [optional] |
|**contactPhone** | **String** | Contact phone |  [optional] |
|**contactEmail** | **String** | Contact email |  [optional] |
|**openingHours** | [**OpeningHoursDTO**](OpeningHoursDTO.md) | Opening hours |  [optional] |
|**deliveryTypeConfig** | **Map&lt;String, Map&lt;String, Object&gt;&gt;** | Per-delivery-type configuration |  [optional] |
|**pickupInstructions** | **String** | Pickup instructions |  [optional] |
|**timezone** | **String** | Timezone |  [optional] |
|**createdDate** | **OffsetDateTime** | Created date |  [optional] |
|**lastModifiedDate** | **OffsetDateTime** | Last modified date |  [optional] |
|**_default** | **Boolean** |  |  [optional] |



## Enum: TypeEnum

| Name | Value |
|---- | -----|
| STORE | &quot;STORE&quot; |
| WAREHOUSE | &quot;WAREHOUSE&quot; |
| HUB | &quot;HUB&quot; |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| ACTIVE | &quot;ACTIVE&quot; |
| INACTIVE | &quot;INACTIVE&quot; |



