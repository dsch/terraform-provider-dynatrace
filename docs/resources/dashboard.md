---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "dynatrace_dashboard Resource - terraform-provider-dynatrace"
subcategory: ""
description: |-
  
---

# dynatrace_dashboard (Resource)





<!-- schema generated by tfplugindocs -->
## Schema

### Optional

- **dashboard_metadata** (Block List, Max: 1) contains parameters of a dashboard (see [below for nested schema](#nestedblock--dashboard_metadata))
- **id** (String) The ID of this resource.
- **metadata** (Block List, Max: 1, Deprecated) `metadata` exists for backwards compatibility but shouldn't get specified anymore (see [below for nested schema](#nestedblock--metadata))
- **tile** (Block List) the tiles this Dashboard consist of (see [below for nested schema](#nestedblock--tile))
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider

<a id="nestedblock--dashboard_metadata"></a>
### Nested Schema for `dashboard_metadata`

Required:

- **name** (String) the name of the dashboard
- **owner** (String) the owner of the dashboard

Optional:

- **dynamic_filters** (Block List, Max: 1) Dashboard filter configuration of a dashboard (see [below for nested schema](#nestedblock--dashboard_metadata--dynamic_filters))
- **filter** (Block List, Max: 1) Global filter Settings for the Dashboard (see [below for nested schema](#nestedblock--dashboard_metadata--filter))
- **shared** (Boolean) the dashboard is shared (`true`) or private (`false`)
- **sharing_details** (Block List, Max: 1) represents sharing configuration of a dashboard (see [below for nested schema](#nestedblock--dashboard_metadata--sharing_details))
- **tags** (Set of String) a set of tags assigned to the dashboard
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider
- **valid_filter_keys** (Set of String) a set of all possible global dashboard filters that can be applied to dashboard

<a id="nestedblock--dashboard_metadata--dynamic_filters"></a>
### Nested Schema for `dashboard_metadata.dynamic_filters`

Required:

- **filters** (Set of String) A set of all possible global dashboard filters that can be applied to a dashboard 

Currently supported values are: 

	OS_TYPE,
	SERVICE_TYPE,
	DEPLOYMENT_TYPE,
	APPLICATION_INJECTION_TYPE,
	PAAS_VENDOR_TYPE,
	DATABASE_VENDOR,
	HOST_VIRTUALIZATION_TYPE,
	HOST_MONITORING_MODE,
	KUBERNETES_CLUSTER,
	RELATED_CLOUD_APPLICATION,
	RELATED_NAMESPACE,
	TAG_KEY:<tagname>

Optional:

- **tag_suggestion_types** (Set of String) A set of entities applied for tag filter suggestions. You can fetch the list of possible values with the [GET all entity types](https://dt-url.net/dw03s7h)request. 

Only applicable if the **filters** set includes `TAG_KEY:<tagname>`
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider


<a id="nestedblock--dashboard_metadata--filter"></a>
### Nested Schema for `dashboard_metadata.filter`

Optional:

- **management_zone** (Block List) the management zone this dashboard applies to (see [below for nested schema](#nestedblock--dashboard_metadata--filter--management_zone))
- **timeframe** (String) the default timeframe of the dashboard
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider

<a id="nestedblock--dashboard_metadata--filter--management_zone"></a>
### Nested Schema for `dashboard_metadata.filter.management_zone`

Required:

- **id** (String) the ID of the Dynatrace entity

Optional:

- **description** (String) a short description of the Dynatrace entity
- **name** (String) the name of the Dynatrace entity
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider



<a id="nestedblock--dashboard_metadata--sharing_details"></a>
### Nested Schema for `dashboard_metadata.sharing_details`

Optional:

- **link_shared** (Boolean) If `true`, the dashboard is shared via link and authenticated users with the link can view
- **published** (Boolean) If `true`, the dashboard is published to anyone on this environment
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider



<a id="nestedblock--metadata"></a>
### Nested Schema for `metadata`

Optional:

- **cluster_version** (String) Dynatrace server version
- **configuration_versions** (List of Number) A Sorted list of the version numbers of the configuration
- **current_configuration_versions** (List of String) A Sorted list of the version numbers of the configuration


<a id="nestedblock--tile"></a>
### Nested Schema for `tile`

Required:

- **name** (String) the name of the tile
- **tile_type** (String) the type of the tile. Must be either `APPLICATION_WORLDMAP`, `RESOURCES`, `THIRD_PARTY_MOST_ACTIVE`, `UEM_CONVERSIONS_PER_GOAL`, `PROCESS_GROUPS_ONE` or `HOST` .

Optional:

- **assigned_entities** (Set of String) The list of Dynatrace entities, assigned to the tile
- **bounds** (Block List, Max: 1) the position and size of a tile (see [below for nested schema](#nestedblock--tile--bounds))
- **chart_visible** (Boolean)
- **configured** (Boolean) The tile is configured and ready to use (`true`) or just placed on the dashboard (`false`)
- **custom_name** (String) The name of the tile, set by user
- **exclude_maintenance_windows** (Boolean) Include (`false') or exclude (`true`) maintenance windows from availability calculations
- **filter** (Block List, Max: 1) is filter applied to a tile. It overrides dashboard's filter (see [below for nested schema](#nestedblock--tile--filter))
- **filter_config** (Block List, Max: 1) the position and size of a tile (see [below for nested schema](#nestedblock--tile--filter_config))
- **limit** (Number) The limit of the results, if not set will use the default value of the system
- **markdown** (String) The markdown-formatted content of the tile
- **metric** (String) The metric assigned to the tile
- **query** (String) A [user session query](https://www.dynatrace.com/support/help/shortlink/usql-info) executed by the tile
- **time_frame_shift** (String) The comparison timeframe of the query. If specified, you additionally get the results of the same query with the specified time shift
- **type** (String) The attribute `type` exists for backwards compatibilty. Usage is discouraged. You should use `visualization` instead.
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider
- **visualization** (String) The visualization of the tile. Possible values are: `COLUMN_CHART`, `FUNNEL`, `LINE_CHART`, `PIE_CHART`, `SINGLE_VALUE`, `TABLE`
- **visualization_config** (Block List, Max: 1) Configuration of a User session query visualization tile (see [below for nested schema](#nestedblock--tile--visualization_config))

<a id="nestedblock--tile--bounds"></a>
### Nested Schema for `tile.bounds`

Required:

- **height** (Number) the height of the tile, in pixels
- **left** (Number) the horizontal distance from the top left corner of the dashboard to the top left corner of the tile, in pixels
- **top** (Number) the vertical distance from the top left corner of the dashboard to the top left corner of the tile, in pixels
- **width** (Number) the width of the tile, in pixels

Optional:

- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider


<a id="nestedblock--tile--filter"></a>
### Nested Schema for `tile.filter`

Optional:

- **management_zone** (Block List) the management zone this tile applies to (see [below for nested schema](#nestedblock--tile--filter--management_zone))
- **timeframe** (String) the default timeframe of the tile
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider

<a id="nestedblock--tile--filter--management_zone"></a>
### Nested Schema for `tile.filter.management_zone`

Required:

- **id** (String) the ID of the Dynatrace entity

Optional:

- **description** (String) a short description of the Dynatrace entity
- **name** (String) the name of the Dynatrace entity
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider



<a id="nestedblock--tile--filter_config"></a>
### Nested Schema for `tile.filter_config`

Required:

- **custom_name** (String) The name of the tile, set by user
- **default_name** (String) The default name of the tile
- **type** (String) The type of the filter. Possible values are `ALB`, `APPLICATION`, `APPLICATION_METHOD`, `APPMON`, `ASG`, `AWS_CREDENTIALS`, `AWS_CUSTOM_SERVICE`, `AWS_LAMBDA_FUNCTION`, `CLOUD_APPLICATION`, `CLOUD_APPLICATION_INSTANCE`, `CLOUD_APPLICATION_NAMESPACE`, `CONTAINER_GROUP_INSTANCE`, `CUSTOM_APPLICATION`, `CUSTOM_DEVICES`, `CUSTOM_SERVICES`, `DATABASE`, `DATABASE_KEY_REQUEST`, `DCRUM_APPLICATION`, `DCRUM_ENTITY`, `DYNAMO_DB`, `EBS`, `EC2`, `ELB`, `ENVIRONMENT`, `ESXI`, `EXTERNAL_SYNTHETIC_TEST`, `GLOBAL_BACKGROUND_ACTIVITY`, `HOST`, `IOT`, `KUBERNETES_CLUSTER`, `KUBERNETES_NODE`, `MDA_SERVICE`, `MIXED`, `MOBILE_APPLICATION`, `MONITORED_ENTITY`, `NLB`, `PG_BACKGROUND_ACTIVITY`, `PROBLEM`, `PROCESS_GROUP_INSTANCE`, `RDS`, `REMOTE_PLUGIN`, `SERVICE`, `SERVICE_KEY_REQUEST`, `SYNTHETIC_BROWSER_MONITOR`, `SYNTHETIC_HTTPCHECK`, `SYNTHETIC_HTTPCHECK_STEP`, `SYNTHETIC_LOCATION`, `SYNTHETIC_TEST`, `SYNTHETIC_TEST_STEP`, `UI_ENTITY`, `VIRTUAL_MACHINE`, `WEB_CHECK`.

Optional:

- **chart_config** (Block List, Max: 1) Configuration of a custom chart (see [below for nested schema](#nestedblock--tile--filter_config--chart_config))
- **filters** (Block List, Max: 1) Configuration of a custom chart (see [below for nested schema](#nestedblock--tile--filter_config--filters))
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider

<a id="nestedblock--tile--filter_config--chart_config"></a>
### Nested Schema for `tile.filter_config.chart_config`

Required:

- **type** (String) The type of the chart

Optional:

- **axis_limits** (Map of Number) The optional custom y-axis limits
- **left_axis_custom_unit** (String) Either one of `Bit`, `BitPerHour`, `BitPerMinute`, `BitPerSecond`, `Byte`, `BytePerHour`, `BytePerMinute`, `BytePerSecond`, `Cores`, `Count`, `Day`, `DecibelMilliWatt`, `GibiByte`, `Giga`, `GigaByte`, `Hour`, `KibiByte`, `KibiBytePerHour`, `KibiBytePerMinute`, `KibiBytePerSecond`, `Kilo`, `KiloByte`, `KiloBytePerHour`, `KiloBytePerMinute`, `KiloBytePerSecond`, `MebiByte`, `MebiBytePerHour`, `MebiBytePerMinute`, `MebiBytePerSecond`, `Mega`, `MegaByte`, `MegaBytePerHour`, `MegaBytePerMinute`, `MegaBytePerSecond`, `MicroSecond`, `MilliCores`, `MilliSecond`, `MilliSecondPerMinute`, `Minute`, `Month`, `NanoSecond`, `NanoSecondPerMinute`, `NotApplicable`, `PerHour`, `PerMinute`, `PerSecond`, `Percent`, `Pixel`, `Promille`, `Ratio`, `Second`, `State`, `Unspecified`, `Week`, `Year`
- **legend** (Boolean) Defines if a legend should be shown
- **result_metadata** (Block List) Additional information about charted metric (see [below for nested schema](#nestedblock--tile--filter_config--chart_config--result_metadata))
- **right_axis_custom_unit** (String) Either one of `Bit`, `BitPerHour`, `BitPerMinute`, `BitPerSecond`, `Byte`, `BytePerHour`, `BytePerMinute`, `BytePerSecond`, `Cores`, `Count`, `Day`, `DecibelMilliWatt`, `GibiByte`, `Giga`, `GigaByte`, `Hour`, `KibiByte`, `KibiBytePerHour`, `KibiBytePerMinute`, `KibiBytePerSecond`, `Kilo`, `KiloByte`, `KiloBytePerHour`, `KiloBytePerMinute`, `KiloBytePerSecond`, `MebiByte`, `MebiBytePerHour`, `MebiBytePerMinute`, `MebiBytePerSecond`, `Mega`, `MegaByte`, `MegaBytePerHour`, `MegaBytePerMinute`, `MegaBytePerSecond`, `MicroSecond`, `MilliCores`, `MilliSecond`, `MilliSecondPerMinute`, `Minute`, `Month`, `NanoSecond`, `NanoSecondPerMinute`, `NotApplicable`, `PerHour`, `PerMinute`, `PerSecond`, `Percent`, `Pixel`, `Promille`, `Ratio`, `Second`, `State`, `Unspecified`, `Week`, `Year`
- **series** (Block List) A list of charted metrics (see [below for nested schema](#nestedblock--tile--filter_config--chart_config--series))
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider

<a id="nestedblock--tile--filter_config--chart_config--result_metadata"></a>
### Nested Schema for `tile.filter_config.chart_config.unknowns`

Optional:

- **config** (Block List) Additional metadata for charted metric (see [below for nested schema](#nestedblock--tile--filter_config--chart_config--unknowns--config))

<a id="nestedblock--tile--filter_config--chart_config--unknowns--config"></a>
### Nested Schema for `tile.filter_config.chart_config.unknowns.config`

Optional:

- **custom_color** (String) The color of the metric in the chart, hex format
- **key** (String) A generated key by the Dynatrace Server
- **last_modified** (Number) The timestamp of the last metadata modification, in UTC milliseconds
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider



<a id="nestedblock--tile--filter_config--chart_config--series"></a>
### Nested Schema for `tile.filter_config.chart_config.unknowns`

Required:

- **aggregation** (String) The charted aggregation of the metric
- **entity_type** (String) The visualization of the timeseries chart
- **metric** (String) The name of the charted metric
- **type** (String) The visualization of the timeseries chart. Possible values are `AREA`, `BAR` and `LINE`.

Optional:

- **aggregation_rate** (String)
- **dimension** (Block List) Configuration of the charted metric splitting (see [below for nested schema](#nestedblock--tile--filter_config--chart_config--unknowns--dimension))
- **percentile** (Number) The charted percentile. Only applicable if the **aggregation** is set to `PERCENTILE`
- **sort_ascending** (Boolean) Sort ascending (`true`) or descending (`false`)
- **sort_column** (Boolean) Sort the column (`true`) or (`false`)
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider

<a id="nestedblock--tile--filter_config--chart_config--unknowns--dimension"></a>
### Nested Schema for `tile.filter_config.chart_config.unknowns.dimension`

Required:

- **id** (String) The ID of the dimension by which the metric is split

Optional:

- **entity_dimension** (Boolean)
- **name** (String) The name of the dimension by which the metric is split
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider
- **values** (Set of String) The splitting value




<a id="nestedblock--tile--filter_config--filters"></a>
### Nested Schema for `tile.filter_config.filters`

Optional:

- **filter** (Block List) the tiles this Dashboard consist of (see [below for nested schema](#nestedblock--tile--filter_config--filters--filter))

<a id="nestedblock--tile--filter_config--filters--filter"></a>
### Nested Schema for `tile.filter_config.filters.filter`

Required:

- **entity_type** (String) The entity type (e.g. HOST, SERVICE, ...)

Optional:

- **match** (Block List) the tiles this Dashboard consist of (see [below for nested schema](#nestedblock--tile--filter_config--filters--filter--match))

<a id="nestedblock--tile--filter_config--filters--filter--match"></a>
### Nested Schema for `tile.filter_config.filters.filter.match`

Required:

- **key** (String) The entity type (e.g. HOST, SERVICE, ...)

Optional:

- **values** (Set of String) the tiles this Dashboard consist of





<a id="nestedblock--tile--visualization_config"></a>
### Nested Schema for `tile.visualization_config`

Optional:

- **has_axis_bucketing** (Boolean) The axis bucketing when enabled groups similar series in the same virtual axis
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider


