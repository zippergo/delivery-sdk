

# SearchDeliveriesRequest

Advanced search request for deliveries with filtering, sorting, and pagination capabilities. **Query Fields** (full-text search): `providerTrackingId`, `externalOrderId` **Available Filter/Sort Fields:** - `status` (HubDeliveryStatus, sortable) - CREATED, ASSIGNED, PICKED_UP, IN_TRANSIT, DELIVERED, CANCELLED, FAILED - `deliveryType` (DeliveryType, sortable) - `providerType` (DeliveryProviderType, sortable) - `createdDate` (Instant, sortable) - `userId` (Long, sortable) - Auto-filtered for non-admin users 

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**query** | **String** | Full-text search query string. Matches against predefined query fields using case-insensitive LIKE. |  [optional] |
|**filters** | **Map&lt;String, List&lt;Filter&gt;&gt;** | Filter groups with AND/OR logic. Each group contains a list of filter criteria that are combined using the specified operator. |  [optional] |
|**sort** | [**List&lt;SortField&gt;**](SortField.md) | Sort criteria applied in order. Only sortable fields are accepted. |  [optional] |
|**pagination** | [**Pagination**](Pagination.md) | Pagination parameters. Page numbers are 1-based. |  [optional] |



