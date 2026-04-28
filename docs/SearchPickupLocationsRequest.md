

# SearchPickupLocationsRequest

Advanced search request for pickup locations with filtering, sorting, and pagination capabilities. **Query Fields** (full-text search): `name`, `code`, `city`, `contactName` **Available Filter/Sort Fields:** - `code` (String, sortable) - `status` (PickupLocationStatus, sortable) - `type` (PickupLocationType, sortable) - `city` (String, sortable) - `countryCode` (String, sortable) - `isDefault` (Boolean, sortable) - `createdDate` (Instant, sortable) 

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**query** | **String** | Full-text search query string. Matches against predefined query fields using case-insensitive LIKE. |  [optional] |
|**filters** | **Map&lt;String, List&lt;Filter&gt;&gt;** | Filter groups with AND/OR logic. Each group contains a list of filter criteria that are combined using the specified operator. |  [optional] |
|**sort** | [**List&lt;SortField&gt;**](SortField.md) | Sort criteria applied in order. Only sortable fields are accepted. |  [optional] |
|**pagination** | [**Pagination**](Pagination.md) | Pagination parameters. Page numbers are 1-based. |  [optional] |



