

# HubItemDTO

An item included in the delivery

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**sku** | **String** | Optional SKU or identifier for the item |  [optional] |
|**name** | **String** | Item name |  |
|**quantity** | **Integer** | Quantity of this item |  |
|**description** | **String** | Optional item description |  [optional] |
|**weightKg** | **Double** | Optional package weight in kilograms |  [optional] |
|**lengthCm** | **Double** | Optional package length in centimeters |  [optional] |
|**widthCm** | **Double** | Optional package width in centimeters |  [optional] |
|**heightCm** | **Double** | Optional package height in centimeters |  [optional] |
|**unitValue** | **BigDecimal** | Declared value of a single unit, for customs |  [optional] |
|**valueCurrency** | **String** | Currency of unitValue (ISO-4217). Defaults to the shipment customs currency. |  [optional] |
|**hsCode** | **String** | Optional HS / tariff classification code |  [optional] |
|**originCountry** | **String** | Country of origin/manufacture (ISO-2) |  [optional] |



