

# HubStatusEventDTO

A single status change event in the delivery lifecycle

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**status** | [**StatusEnum**](#StatusEnum) | Delivery status at this event |  [optional] |
|**occurredAt** | **OffsetDateTime** | When this status change occurred |  [optional] |
|**description** | **String** | Human-readable description of the event |  [optional] |
|**proofOfDeliveryUrl** | **String** | URL to proof-of-delivery image (only for DELIVERED status) |  [optional] |



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



