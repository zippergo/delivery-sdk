

# CustomsDeclarationDTO

Customs declaration for an international export shipment

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**contentsType** | [**ContentsTypeEnum**](#ContentsTypeEnum) | What the shipment contains, for customs |  [optional] |
|**reasonForExport** | **String** | Reason the goods are being exported |  [optional] |
|**incoterm** | **String** | Incoterm governing who pays duties/taxes |  [optional] |
|**currency** | **String** | Currency of the declared item values (ISO-4217) |  [optional] |



## Enum: ContentsTypeEnum

| Name | Value |
|---- | -----|
| MERCHANDISE | &quot;merchandise&quot; |
| GIFT | &quot;gift&quot; |
| SAMPLE | &quot;sample&quot; |
| DOCUMENTS | &quot;documents&quot; |



