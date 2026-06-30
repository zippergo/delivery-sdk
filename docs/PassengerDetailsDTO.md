

# PassengerDetailsDTO

Passenger-transport details. Required for PASSENGER_TRANSPORT delivery type.

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**passengers** | [**List&lt;PassengerContactDTO&gt;**](PassengerContactDTO.md) | Passengers to transport (at least one). One passenger ⇒ Single ride, many ⇒ Multi ride. |  |
|**luggageCount** | **Integer** | Number of luggage items |  [optional] |
|**vehicleClass** | **String** | Requested vehicle/product class (provider-specific) |  [optional] |
|**notes** | **String** | Free-text notes for the ride (e.g. accessibility needs) |  [optional] |



