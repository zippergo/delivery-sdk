

# HubDispatchAttemptDTO

A single provider dispatch attempt (admin views only)

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**attemptNumber** | **Integer** |  |  [optional] |
|**providerType** | [**ProviderTypeEnum**](#ProviderTypeEnum) |  |  [optional] |
|**providerOrderId** | **String** |  |  [optional] |
|**providerTrackingId** | **String** |  |  [optional] |
|**providerTrackingUrl** | **String** |  |  [optional] |
|**status** | [**StatusEnum**](#StatusEnum) |  |  [optional] |
|**createdAt** | **OffsetDateTime** |  |  [optional] |



## Enum: ProviderTypeEnum

| Name | Value |
|---- | -----|
| ZIPPERG | &quot;ZIPPERG&quot; |
| ZIPPERW | &quot;ZIPPERW&quot; |
| ZIPPERK | &quot;ZIPPERK&quot; |
| ZIPPERGP | &quot;ZIPPERGP&quot; |
| ZIPPERU | &quot;ZIPPERU&quot; |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| PENDING | &quot;PENDING&quot; |
| DISPATCHED | &quot;DISPATCHED&quot; |
| PROVIDER_ACCEPTED | &quot;PROVIDER_ACCEPTED&quot; |
| ASSIGNED | &quot;ASSIGNED&quot; |
| READY_FOR_PICKUP | &quot;READY_FOR_PICKUP&quot; |
| PICKED_UP | &quot;PICKED_UP&quot; |
| IN_TRANSIT | &quot;IN_TRANSIT&quot; |
| DELIVERED | &quot;DELIVERED&quot; |
| CANCELLED | &quot;CANCELLED&quot; |
| FAILED | &quot;FAILED&quot; |
| REJECTED | &quot;REJECTED&quot; |
| AWAITING_DRIVER | &quot;AWAITING_DRIVER&quot; |



