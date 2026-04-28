

# UpdatePickupLocationRequest

Request to update an existing pickup location. All fields are optional for partial update.

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**name** | **String** | Display name for the location |  [optional] |
|**type** | [**TypeEnum**](#TypeEnum) | Type of pickup location |  [optional] |
|**status** | [**StatusEnum**](#StatusEnum) | Status of the location |  [optional] |
|**isDefault** | **Boolean** | Whether this is the default pickup location |  [optional] |
|**addressLine1** | **String** | Primary address line |  [optional] |
|**addressLine2** | **String** | Secondary address line |  [optional] |
|**houseNumber** | **String** | House number |  [optional] |
|**entranceFloor** | **String** | Entrance or floor |  [optional] |
|**city** | **String** | City name |  [optional] |
|**region** | **String** | Region or state |  [optional] |
|**postalCode** | **String** | Postal code |  [optional] |
|**countryCode** | **String** | ISO country code |  [optional] |
|**latitude** | **Double** | Latitude coordinate |  [optional] |
|**longitude** | **Double** | Longitude coordinate |  [optional] |
|**contactName** | **String** | Contact person name |  [optional] |
|**contactPhone** | **String** | Contact phone number |  [optional] |
|**contactEmail** | **String** | Contact email |  [optional] |
|**openingHours** | [**OpeningHoursDTO**](OpeningHoursDTO.md) | Opening hours with interval support |  [optional] |
|**deliveryTypeConfig** | **Map&lt;String, Map&lt;String, Object&gt;&gt;** | Per-delivery-type configuration |  [optional] |
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



