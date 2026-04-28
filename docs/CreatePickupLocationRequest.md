

# CreatePickupLocationRequest

Request to create a new pickup location

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**name** | **String** | Display name for the location |  |
|**code** | **String** | Unique code for the location (per user) |  |
|**type** | [**TypeEnum**](#TypeEnum) | Type of pickup location |  |
|**status** | [**StatusEnum**](#StatusEnum) | Status of the location |  [optional] |
|**isDefault** | **Boolean** | Whether this is the default pickup location |  [optional] |
|**addressLine1** | **String** | Primary address line |  |
|**addressLine2** | **String** | Secondary address line |  [optional] |
|**houseNumber** | **String** | House number |  [optional] |
|**entranceFloor** | **String** | Entrance or floor |  [optional] |
|**city** | **String** | City name |  |
|**region** | **String** | Region or state |  [optional] |
|**postalCode** | **String** | Postal code |  [optional] |
|**countryCode** | **String** | ISO country code |  |
|**latitude** | **Double** | Latitude coordinate |  [optional] |
|**longitude** | **Double** | Longitude coordinate |  [optional] |
|**contactName** | **String** | Contact person name |  [optional] |
|**contactPhone** | **String** | Contact phone number |  [optional] |
|**contactEmail** | **String** | Contact email |  [optional] |
|**openingHours** | [**OpeningHoursDTO**](OpeningHoursDTO.md) | Opening hours with interval support |  [optional] |
|**deliveryTypeConfig** | **Map&lt;String, Map&lt;String, Object&gt;&gt;** | Per-delivery-type configuration. Keys are delivery type names (e.g. STORE_NEXT_DAY), values are key-value maps. |  [optional] |
|**pickupInstructions** | **String** | Instructions for pickup couriers |  [optional] |
|**timezone** | **String** | Timezone for opening hours validation |  [optional] |



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



