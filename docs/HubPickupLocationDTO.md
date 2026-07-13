

# HubPickupLocationDTO

Pickup site (warehouse/store/hub) with opening hours (admin views only)

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**externalId** | **UUID** |  |  [optional] |
|**name** | **String** |  |  [optional] |
|**code** | **String** |  |  [optional] |
|**type** | [**TypeEnum**](#TypeEnum) |  |  [optional] |
|**status** | [**StatusEnum**](#StatusEnum) |  |  [optional] |
|**addressLine1** | **String** |  |  [optional] |
|**addressLine2** | **String** |  |  [optional] |
|**houseNumber** | **String** |  |  [optional] |
|**entranceFloor** | **String** |  |  [optional] |
|**city** | **String** |  |  [optional] |
|**region** | **String** |  |  [optional] |
|**postalCode** | **String** |  |  [optional] |
|**countryCode** | **String** |  |  [optional] |
|**latitude** | **Double** |  |  [optional] |
|**longitude** | **Double** |  |  [optional] |
|**contactName** | **String** |  |  [optional] |
|**contactPhone** | **String** |  |  [optional] |
|**contactEmail** | **String** |  |  [optional] |
|**openingHours** | [**OpeningHours**](OpeningHours.md) |  |  [optional] |
|**pickupInstructions** | **String** |  |  [optional] |
|**timezone** | **String** |  |  [optional] |
|**deliveryTypeConfig** | **Map&lt;String, Map&lt;String, Object&gt;&gt;** |  |  [optional] |
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



