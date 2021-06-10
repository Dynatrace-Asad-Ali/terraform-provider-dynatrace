---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "dynatrace_calculated_service_metric Resource - terraform-provider-dynatrace"
subcategory: ""
description: |-
  
---

# dynatrace_calculated_service_metric (Resource)





<!-- schema generated by tfplugindocs -->
## Schema

### Required

- **metric_definition** (Block List, Min: 1, Max: 1) The definition of a calculated service metric (see [below for nested schema](#nestedblock--metric_definition))
- **metric_key** (String) The key of the calculated service metric
- **name** (String) The displayed name of the metric
- **unit** (String) The unit of the metric. Possible values are `BIT`, `BIT_PER_HOUR`, `BIT_PER_MINUTE`, `BIT_PER_SECOND`, `BYTE`, `BYTE_PER_HOUR`, `BYTE_PER_MINUTE`, `BYTE_PER_SECOND`, `CORES`, `COUNT`, `DAY`, `DECIBEL_MILLI_WATT`, `GIBI_BYTE`, `GIGA`, `GIGA_BYTE`, `HOUR`, `KIBI_BYTE`, `KIBI_BYTE_PER_HOUR`, `KIBI_BYTE_PER_MINUTE`, `KIBI_BYTE_PER_SECOND`, `KILO`, `KILO_BYTE`, `KILO_BYTE_PER_HOUR`, `KILO_BYTE_PER_MINUTE`, `KILO_BYTE_PER_SECOND`, `MEBI_BYTE`, `MEBI_BYTE_PER_HOUR`, `MEBI_BYTE_PER_MINUTE`, `MEBI_BYTE_PER_SECOND`, `MEGA`, `MEGA_BYTE`, `MEGA_BYTE_PER_HOUR`, `MEGA_BYTE_PER_MINUTE`, `MEGA_BYTE_PER_SECOND`, `MICRO_SECOND`, `MILLI_CORES`, `MILLI_SECOND`, `MILLI_SECOND_PER_MINUTE`, `MINUTE`, `MONTH`, `MSU`, `NANO_SECOND`, `NANO_SECOND_PER_MINUTE`, `NOT_APPLICABLE`, `PERCENT`, `PER_HOUR`, `PER_MINUTE`, `PER_SECOND`, `PIXEL`, `PROMILLE`, `RATIO`, `SECOND`, `STATE`, `UNSPECIFIED`, `WEEK` and `YEAR`

### Optional

- **conditions** (Block List) The set of conditions for the metric usage. **All** the specified conditions must be fulfilled to use the metric (see [below for nested schema](#nestedblock--conditions))
- **dimension_definition** (Block List, Max: 1) Parameters of a definition of a calculated service metric (see [below for nested schema](#nestedblock--dimension_definition))
- **enabled** (Boolean) The metric is enabled (`true`) or disabled (`false`)
- **entity_id** (String) Restricts the metric usage to the specified service. This field is mutually exclusive with the `management_zones` field
- **id** (String) The ID of this resource.
- **management_zones** (Set of String) Restricts the metric usage to specified management zones. This field is mutually exclusive with the `entity_id` field
- **unit_display_name** (String) The display name of the metric's unit. Only applicable when the **unit** parameter is set to `UNSPECIFIED`
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider

<a id="nestedblock--metric_definition"></a>
### Nested Schema for `metric_definition`

Required:

- **metric** (String) The metric to be captured. Possible values are `CPU_TIME`, `DATABASE_CHILD_CALL_COUNT`, `DATABASE_CHILD_CALL_TIME`, `DISK_IO_TIME`, `EXCEPTION_COUNT`, `FAILED_REQUEST_COUNT`, `FAILED_REQUEST_COUNT_CLIENT`, `FAILURE_RATE`, `FAILURE_RATE_CLIENT`, `HTTP_4XX_ERROR_COUNT`, `HTTP_4XX_ERROR_COUNT_CLIENT`, `HTTP_5XX_ERROR_COUNT`, `HTTP_5XX_ERROR_COUNT_CLIENT`, `IO_TIME`, `LOCK_TIME`, `NETWORK_IO_TIME`, `NON_DATABASE_CHILD_CALL_COUNT`, `NON_DATABASE_CHILD_CALL_TIME`, `PROCESSING_TIME`, `REQUEST_ATTRIBUTE`, `REQUEST_COUNT`, `RESPONSE_TIME`, `RESPONSE_TIME_CLIENT`, `SUCCESSFUL_REQUEST_COUNT`, `SUCCESSFUL_REQUEST_COUNT_CLIENT` and `WAIT_TIME`

Optional:

- **request_attribute** (String) The request attribute to be captured. Only applicable when the **metric** parameter is set to `REQUEST_ATTRIBUTE`


<a id="nestedblock--conditions"></a>
### Nested Schema for `conditions`

Optional:

- **condition** (Block List) A conditions for the metric usage (see [below for nested schema](#nestedblock--conditions--condition))

<a id="nestedblock--conditions--condition"></a>
### Nested Schema for `conditions.condition`

Required:

- **attribute** (String) The attribute to be matched.  Note that for a service property attribute you must use the comparison of the `FAST_STRING` type. Possible values are `ACTOR_SYSTEM`, `AKKA_ACTOR_CLASS_NAME`, `AKKA_ACTOR_MESSAGE_TYPE`, `AKKA_ACTOR_PATH`, `APPLICATION_BUILD_VERSION`, `APPLICATION_RELEASE_VERSION`, `AZURE_FUNCTIONS_FUNCTION_NAME`, `AZURE_FUNCTIONS_SITE_NAME`, `CICS_PROGRAM_NAME`, `CICS_SYSTEM_ID`, `CICS_TASK_ID`, `CICS_TRANSACTION_ID`, `CICS_USER_ID`, `CPU_TIME`, `CTG_GATEWAY_URL`, `CTG_PROGRAM`, `CTG_SERVER_NAME`, `CTG_TRANSACTION_ID`, `CUSTOMSERVICE_CLASS`, `CUSTOMSERVICE_METHOD`, `DATABASE_CHILD_CALL_COUNT`, `DATABASE_CHILD_CALL_TIME`, `DATABASE_HOST`, `DATABASE_NAME`, `DATABASE_TYPE`, `DATABASE_URL`, `DISK_IO_TIME`, `ERROR_COUNT`, `ESB_APPLICATION_NAME`, `ESB_INPUT_TYPE`, `ESB_LIBRARY_NAME`, `ESB_MESSAGE_FLOW_NAME`, `EXCEPTION_CLASS`, `EXCEPTION_MESSAGE`, `FAILED_STATE`, `FAILURE_REASON`, `FLAW_STATE`, `HTTP_REQUEST_METHOD`, `HTTP_STATUS`, `HTTP_STATUS_CLASS`, `IMS_PROGRAM_NAME`, `IMS_TRANSACTION_ID`, `IMS_USER_ID`, `IO_TIME`, `IS_KEY_REQUEST`, `LAMBDA_COLDSTART`, `LOCK_TIME`, `MESSAGING_DESTINATION_TYPE`, `MESSAGING_IS_TEMPORARY_QUEUE`, `MESSAGING_QUEUE_NAME`, `MESSAGING_QUEUE_VENDOR`, `NETWORK_IO_TIME`, `NON_DATABASE_CHILD_CALL_COUNT`, `NON_DATABASE_CHILD_CALL_TIME`, `PROCESS_GROUP_NAME`, `PROCESS_GROUP_TAG`, `REMOTE_ENDPOINT`, `REMOTE_METHOD`, `REMOTE_SERVICE_NAME`, `REQUEST_NAME`, `REQUEST_TYPE`, `RESPONSE_TIME`, `RESPONSE_TIME_CLIENT`, `RMI_CLASS`, `RMI_METHOD`, `SERVICE_DISPLAY_NAME`, `SERVICE_NAME`, `SERVICE_PORT`, `SERVICE_PUBLIC_DOMAIN_NAME`, `SERVICE_REQUEST_ATTRIBUTE`, `SERVICE_TAG`, `SERVICE_TYPE`, `SERVICE_WEB_APPLICATION_ID`, `SERVICE_WEB_CONTEXT_ROOT`, `SERVICE_WEB_SERVER_NAME`, `SERVICE_WEB_SERVICE_NAME`, `SERVICE_WEB_SERVICE_NAMESPACE`, `SUSPENSION_TIME`, `TOTAL_PROCESSING_TIME`, `WAIT_TIME`, `WEBREQUEST_QUERY`, `WEBREQUEST_RELATIVE_URL`, `WEBREQUEST_URL`, `WEBREQUEST_URL_HOST`, `WEBREQUEST_URL_PATH`, `WEBREQUEST_URL_PORT`, `WEBSERVICE_ENDPOINT`, `WEBSERVICE_METHOD` and `ZOS_CALL_TYPE`
- **comparison** (Block List, Min: 1, Max: 1) Type-specific comparison for attributes (see [below for nested schema](#nestedblock--conditions--condition--comparison))

<a id="nestedblock--conditions--condition--comparison"></a>
### Nested Schema for `conditions.condition.comparison`

Optional:

- **boolean** (Block List, Max: 1) Boolean Comparison for `BOOLEAN` attributes (see [below for nested schema](#nestedblock--conditions--condition--comparison--boolean))
- **esb_input_node_type** (Block List, Max: 1) Type-specific comparison information for attributes of type 'ESB_INPUT_NODE_TYPE' (see [below for nested schema](#nestedblock--conditions--condition--comparison--esb_input_node_type))
- **failed_state** (Block List, Max: 1) Comparison for `FAILED_STATE` attributes (see [below for nested schema](#nestedblock--conditions--condition--comparison--failed_state))
- **failure_reason** (Block List, Max: 1) Comparison for `FAILURE_REASON` attributes (see [below for nested schema](#nestedblock--conditions--condition--comparison--failure_reason))
- **fast_string** (Block List, Max: 1) Comparison for `FAST_STRING` attributes. Use it for all service property attributes (see [below for nested schema](#nestedblock--conditions--condition--comparison--fast_string))
- **flaw_state** (Block List, Max: 1) Comparison for `FLAW_STATE` attributes (see [below for nested schema](#nestedblock--conditions--condition--comparison--flaw_state))
- **generic** (Block List, Max: 1) Comparison for `NUMBER` attributes (see [below for nested schema](#nestedblock--conditions--condition--comparison--generic))
- **http_method** (Block List, Max: 1) Comparison for `HTTP_METHOD` attributes (see [below for nested schema](#nestedblock--conditions--condition--comparison--http_method))
- **http_status_class** (Block List, Max: 1) Comparison for `HTTP_STATUS_CLASS` attributes (see [below for nested schema](#nestedblock--conditions--condition--comparison--http_status_class))
- **iib_input_node_type** (Block List, Max: 1) Comparison for `IIB_INPUT_NODE_TYPE` attributes (see [below for nested schema](#nestedblock--conditions--condition--comparison--iib_input_node_type))
- **negate** (Boolean) Reverse the comparison **operator**. For example, it turns **equals** into **does not equal**
- **number** (Block List, Max: 1) Comparison for `NUMBER` attributes (see [below for nested schema](#nestedblock--conditions--condition--comparison--number))
- **number_request_attribute** (Block List, Max: 1) Comparison for `NUMBER_REQUEST_ATTRIBUTE` attributes (see [below for nested schema](#nestedblock--conditions--condition--comparison--number_request_attribute))
- **service_type** (Block List, Max: 1) Comparison for `SERVICE_TYPE` attributes (see [below for nested schema](#nestedblock--conditions--condition--comparison--service_type))
- **string** (Block List, Max: 1) Comparison for `STRING` attributes (see [below for nested schema](#nestedblock--conditions--condition--comparison--string))
- **string_request_attribute** (Block List, Max: 1) Comparison for `STRING_REQUEST_ATTRIBUTE` attributes (see [below for nested schema](#nestedblock--conditions--condition--comparison--string_request_attribute))
- **tag** (Block List, Max: 1) Comparison for `TAG` attributes (see [below for nested schema](#nestedblock--conditions--condition--comparison--tag))
- **zos_call_type** (Block List, Max: 1) Comparison for `ZOS_CALL_TYPE` attributes (see [below for nested schema](#nestedblock--conditions--condition--comparison--zos_call_type))

<a id="nestedblock--conditions--condition--comparison--boolean"></a>
### Nested Schema for `conditions.condition.comparison.zos_call_type`

Optional:

- **operator** (String) Operator of the comparison. You can reverse it by setting `negate` to `true`. Possible values are `EQUALS`, `EQUALS_ANY_OF` and `EXISTS`
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider
- **value** (Boolean) The value to compare to
- **values** (Set of Boolean) The values to compare to


<a id="nestedblock--conditions--condition--comparison--esb_input_node_type"></a>
### Nested Schema for `conditions.condition.comparison.zos_call_type`

Optional:

- **operator** (String) Operator of the comparison. You can reverse it by setting `negate` to `true`. Possible values are `EQUALS`, `EQUALS_ANY_OF` and `EXISTS`
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider
- **value** (String) The value to compare to. Possible values are `CALLABLE_FLOW_ASYNC_RESPONSE_NODE`, `CALLABLE_FLOW_INPUT_NODE`, `DATABASE_INPUT_NODE`, `DOTNET_INPUT_NODE`, `EMAIL_INPUT_NODE`, `EVENT_INPUT`, `EVENT_INPUT_NODE`, `FILE_INPUT_NODE`, `FTE_INPUT_NODE`, `HTTP_ASYNC_RESPONSE`, `JD_EDWARDS_INPUT_NODE`, `JMS_CLIENT_INPUT_NODE`, `LABEL_NODE`, `MQ_INPUT_NODE`, `PEOPLE_SOFT_INPUT_NODE`, `REST_ASYNC_RESPONSE`, `REST_REQUEST`, `SAP_INPUT_NODE`, `SCA_ASYNC_RESPONSE_NODE`, `SCA_INPUT_NODE`, `SIEBEL_INPUT_NODE`, `SOAP_INPUT_NODE`, `TCPIP_CLIENT_INPUT_NODE`, `TCPIP_CLIENT_REQUEST_NODE`, `TCPIP_SERVER_INPUT_NODE`, `TCPIP_SERVER_REQUEST_NODE`, `TIMEOUT_NOTIFICATION_NODE` and `WS_INPUT_NODE`
- **values** (Set of String) The values to compare to. Possible values are `CALLABLE_FLOW_ASYNC_RESPONSE_NODE`, `CALLABLE_FLOW_INPUT_NODE`, `DATABASE_INPUT_NODE`, `DOTNET_INPUT_NODE`, `EMAIL_INPUT_NODE`, `EVENT_INPUT`, `EVENT_INPUT_NODE`, `FILE_INPUT_NODE`, `FTE_INPUT_NODE`, `HTTP_ASYNC_RESPONSE`, `JD_EDWARDS_INPUT_NODE`, `JMS_CLIENT_INPUT_NODE`, `LABEL_NODE`, `MQ_INPUT_NODE`, `PEOPLE_SOFT_INPUT_NODE`, `REST_ASYNC_RESPONSE`, `REST_REQUEST`, `SAP_INPUT_NODE`, `SCA_ASYNC_RESPONSE_NODE`, `SCA_INPUT_NODE`, `SIEBEL_INPUT_NODE`, `SOAP_INPUT_NODE`, `TCPIP_CLIENT_INPUT_NODE`, `TCPIP_CLIENT_REQUEST_NODE`, `TCPIP_SERVER_INPUT_NODE`, `TCPIP_SERVER_REQUEST_NODE`, `TIMEOUT_NOTIFICATION_NODE` and `WS_INPUT_NODE`


<a id="nestedblock--conditions--condition--comparison--failed_state"></a>
### Nested Schema for `conditions.condition.comparison.zos_call_type`

Optional:

- **operator** (String) Operator of the comparison. You can reverse it by setting `negate` to `true`. Possible values are `EQUALS`, `EQUALS_ANY_OF` and `EXISTS`
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider
- **value** (String) The value to compare to. Possible values are `FAILED` and `FAILED`
- **values** (Set of String) The values to compare to. Possible values are `FAILED` and `FAILED`


<a id="nestedblock--conditions--condition--comparison--failure_reason"></a>
### Nested Schema for `conditions.condition.comparison.zos_call_type`

Optional:

- **operator** (String) Operator of the comparison. You can reverse it by setting `negate` to `true`. Possible values are `EQUALS`, `EQUALS_ANY_OF` and `EXISTS`
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider
- **value** (String) The value to compare to. Possible values are `EXCEPTION_AT_ENTRY_NODE`, `EXCEPTION_ON_ANY_NODE`, `HTTP_CODE` and `REQUEST_ATTRIBUTE`
- **values** (Set of String) The values to compare to. Possible values are `EXCEPTION_AT_ENTRY_NODE`, `EXCEPTION_ON_ANY_NODE`, `HTTP_CODE` and `REQUEST_ATTRIBUTE`


<a id="nestedblock--conditions--condition--comparison--fast_string"></a>
### Nested Schema for `conditions.condition.comparison.zos_call_type`

Optional:

- **case_sensitive** (Boolean) The comparison is case-sensitive (`true`) or not case-sensitive (`false`)
- **operator** (String) Operator of the comparison. You can reverse it by setting `negate` to `true`. Possible values are `EQUALS`, `EQUALS_ANY_OF` and `CONTAINS`
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider
- **value** (String) The value to compare to
- **values** (Set of String) The values to compare to


<a id="nestedblock--conditions--condition--comparison--flaw_state"></a>
### Nested Schema for `conditions.condition.comparison.zos_call_type`

Optional:

- **operator** (String) Operator of the comparison. You can reverse it by setting `negate` to `true`. Possible values are `EQUALS`, `EQUALS_ANY_OF` and `EXISTS`
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider
- **value** (String) The value to compare to. Possible values are `FLAWED` and `NOT_FLAWED`
- **values** (Set of String) The values to compare to. Possible values are `FLAWED` and `NOT_FLAWED`


<a id="nestedblock--conditions--condition--comparison--generic"></a>
### Nested Schema for `conditions.condition.comparison.zos_call_type`

Required:

- **type** (String) Defines the actual set of fields depending on the value

Optional:

- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider


<a id="nestedblock--conditions--condition--comparison--http_method"></a>
### Nested Schema for `conditions.condition.comparison.zos_call_type`

Optional:

- **operator** (String) Operator of the comparison. You can reverse it by setting `negate` to `true`. Possible values are `EQUALS`, `EQUALS_ANY_OF` and `EXISTS`
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider
- **value** (String) The value to compare to. Possible values are `CONNECT`, `DELETE`, `GET`, `HEAD`, `OPTIONS`, `PATCH`, `POST`, `PUT` and `TRACE`
- **values** (Set of String) The values to compare to. Possible values are `CONNECT`, `DELETE`, `GET`, `HEAD`, `OPTIONS`, `PATCH`, `POST`, `PUT` and `TRACE`


<a id="nestedblock--conditions--condition--comparison--http_status_class"></a>
### Nested Schema for `conditions.condition.comparison.zos_call_type`

Optional:

- **operator** (String) Operator of the comparison. You can reverse it by setting `negate` to `true`. Possible values are `EQUALS`, `EQUALS_ANY_OF` and `EXISTS`
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider
- **value** (String) The value to compare to. Possible values are `C_1XX`, `C_2XX`, `C_3XX`, `C_4XX`, `C_5XX` and `NO_RESPONSE`
- **values** (Set of String) The values to compare to. Possible values are `C_1XX`, `C_2XX`, `C_3XX`, `C_4XX`, `C_5XX` and `NO_RESPONSE`


<a id="nestedblock--conditions--condition--comparison--iib_input_node_type"></a>
### Nested Schema for `conditions.condition.comparison.zos_call_type`

Optional:

- **operator** (String) Operator of the comparison. You can reverse it by setting `negate` to `true`. Possible values are `EQUALS`, `EQUALS_ANY_OF` and `EXISTS`
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider
- **value** (String) The value to compare to. Possible values are `CALLABLE_FLOW_ASYNC_RESPONSE_NODE`, `CALLABLE_FLOW_INPUT_NODE`, `DATABASE_INPUT_NODE`, `DOTNET_INPUT_NODE`, `EMAIL_INPUT_NODE`, `EVENT_INPUT`, `EVENT_INPUT_NODE`, `FILE_INPUT_NODE`, `FTE_INPUT_NODE`, `HTTP_ASYNC_RESPONSE`, `JD_EDWARDS_INPUT_NODE`, `JMS_CLIENT_INPUT_NODE`, `LABEL_NODE`, `MQ_INPUT_NODE`, `PEOPLE_SOFT_INPUT_NODE`, `REST_ASYNC_RESPONSE`, `REST_REQUEST`, `SAP_INPUT_NODE`, `SCA_ASYNC_RESPONSE_NODE`, `SCA_INPUT_NODE`, `SIEBEL_INPUT_NODE`, `SOAP_INPUT_NODE`, `TCPIP_CLIENT_INPUT_NODE`, `TCPIP_CLIENT_REQUEST_NODE`, `TCPIP_SERVER_INPUT_NODE`, `TCPIP_SERVER_REQUEST_NODE`, `TIMEOUT_NOTIFICATION_NODE` and `WS_INPUT_NODE`
- **values** (Set of String) The values to compare to. Possible values are `CALLABLE_FLOW_ASYNC_RESPONSE_NODE`, `CALLABLE_FLOW_INPUT_NODE`, `DATABASE_INPUT_NODE`, `DOTNET_INPUT_NODE`, `EMAIL_INPUT_NODE`, `EVENT_INPUT`, `EVENT_INPUT_NODE`, `FILE_INPUT_NODE`, `FTE_INPUT_NODE`, `HTTP_ASYNC_RESPONSE`, `JD_EDWARDS_INPUT_NODE`, `JMS_CLIENT_INPUT_NODE`, `LABEL_NODE`, `MQ_INPUT_NODE`, `PEOPLE_SOFT_INPUT_NODE`, `REST_ASYNC_RESPONSE`, `REST_REQUEST`, `SAP_INPUT_NODE`, `SCA_ASYNC_RESPONSE_NODE`, `SCA_INPUT_NODE`, `SIEBEL_INPUT_NODE`, `SOAP_INPUT_NODE`, `TCPIP_CLIENT_INPUT_NODE`, `TCPIP_CLIENT_REQUEST_NODE`, `TCPIP_SERVER_INPUT_NODE`, `TCPIP_SERVER_REQUEST_NODE`, `TIMEOUT_NOTIFICATION_NODE` and `WS_INPUT_NODE`


<a id="nestedblock--conditions--condition--comparison--number"></a>
### Nested Schema for `conditions.condition.comparison.zos_call_type`

Optional:

- **operator** (String) Operator of the comparison. You can reverse it by setting `negate` to `true`. Possible values are `EQUALS`, `EQUALS_ANY_OF`, `EXISTS`, `GREATER_THAN`, `GREATER_THAN_OR_EQUAL`, `LOWER_THAN` and `LOWER_THAN_OR_EQUAL`
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider
- **value** (Number) The value to compare to
- **values** (Set of Number) The values to compare to


<a id="nestedblock--conditions--condition--comparison--number_request_attribute"></a>
### Nested Schema for `conditions.condition.comparison.zos_call_type`

Required:

- **request_attribute** (String) No documentation available for this attribute

Optional:

- **match_on_child_calls** (Boolean) If `true`, the request attribute is matched on child service calls. Default is `false`
- **operator** (String) Operator of the comparison. You can reverse it by setting `negate` to `true`. Possible values are `EQUALS`, `EQUALS_ANY_OF`, `EXISTS`, `GREATER_THAN`, `GREATER_THAN_OR_EQUAL`, `LOWER_THAN` and `LOWER_THAN_OR_EQUAL`
- **source** (Block List, Max: 1) Defines valid sources of request attributes for conditions or placeholders (see [below for nested schema](#nestedblock--conditions--condition--comparison--zos_call_type--source))
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider
- **value** (Number) The value to compare to
- **values** (Set of Number) The values to compare to

<a id="nestedblock--conditions--condition--comparison--zos_call_type--source"></a>
### Nested Schema for `conditions.condition.comparison.zos_call_type.source`

Optional:

- **management_zone** (String) Use only request attributes from services that belong to this management zone.. Use either this or `serviceTag`
- **service_tag** (Block List, Max: 1) Use only request attributes from services that have this tag. Use either this or `managementZone` (see [below for nested schema](#nestedblock--conditions--condition--comparison--zos_call_type--source--service_tag))
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider

<a id="nestedblock--conditions--condition--comparison--zos_call_type--source--service_tag"></a>
### Nested Schema for `conditions.condition.comparison.zos_call_type.source.unknowns`

Required:

- **key** (String) The key of the tag. For custom tags, put the tag value here. The key allows categorization of multiple tags. It is possible that there are multiple values for a single key which will all be represented as standalone tags. Therefore, the key does not have the semantic of a map key but is more like a key of a key-value tuple. In some cases, for example custom tags, the key represents the actual tag value and the value field is not set – those are called valueless tags

Optional:

- **context** (String) The origin of the tag, such as AWS or Cloud Foundry. For custom tags use the `CONTEXTLESS` value. The context is set for tags that are automatically imported by OneAgent (for example, from the AWS console or environment variables). It’s useful for determining the origin of tags when not manually defined, and it also helps to prevent clashes with other existing tags. If the tag is not automatically imported, `CONTEXTLESS` set. Possible values are `AWS`, `AWS_GENERIC`, `AZURE`, `CLOUD_FOUNDRY`, `CONTEXTLESS`, `ENVIRONMENT`, `GOOGLE_COMPUTE_ENGINE` and `KUBERNETES`
- **tag_key** (Block List, Max: 1) has no documentation (see [below for nested schema](#nestedblock--conditions--condition--comparison--zos_call_type--source--unknowns--tag_key))
- **value** (String) The value of the tag. Not applicable to custom tags. If a tag does have a separate key and value (in the textual representation they are split by the colon ‘:’), this field is set with the actual value. Key-value pairs can occur for automatically imported tags and tags set by rules if extractors are used

<a id="nestedblock--conditions--condition--comparison--zos_call_type--source--unknowns--tag_key"></a>
### Nested Schema for `conditions.condition.comparison.zos_call_type.source.unknowns.value`

Optional:

- **context** (String) has no documentation
- **key** (String) has no documentation





<a id="nestedblock--conditions--condition--comparison--service_type"></a>
### Nested Schema for `conditions.condition.comparison.zos_call_type`

Optional:

- **operator** (String) Operator of the comparison. You can reverse it by setting `negate` to `true`. Possible values are `EQUALS`, `EQUALS_ANY_OF` and `EXISTS`
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider
- **value** (String) The value to compare to. Possible values are `BACKGROUND_ACTIVITY`, `CICS_SERVICE`, `CUSTOM_SERVICE`, `DATABASE_SERVICE`, `ENTERPRISE_SERVICE_BUS_SERVICE`, `EXTERNAL`, `IBM_INTEGRATION_BUS_SERVICE`, `IMS_SERVICE`, `MESSAGING_SERVICE`, `RMI_SERVICE`, `RPC_SERVICE`, `WEB_REQUEST_SERVICE` and `WEB_SERVICE`
- **values** (Set of String) The values to compare to. Possible values are `BACKGROUND_ACTIVITY`, `CICS_SERVICE`, `CUSTOM_SERVICE`, `DATABASE_SERVICE`, `ENTERPRISE_SERVICE_BUS_SERVICE`, `EXTERNAL`, `IBM_INTEGRATION_BUS_SERVICE`, `IMS_SERVICE`, `MESSAGING_SERVICE`, `RMI_SERVICE`, `RPC_SERVICE`, `WEB_REQUEST_SERVICE` and `WEB_SERVICE`


<a id="nestedblock--conditions--condition--comparison--string"></a>
### Nested Schema for `conditions.condition.comparison.zos_call_type`

Optional:

- **case_sensitive** (Boolean) The comparison is case-sensitive (`true`) or not case-sensitive (`false`)
- **operator** (String) Operator of the comparison. You can reverse it by setting `negate` to `true`. Possible values are `BEGINS_WITH`, `BEGINS_WITH_ANY_OF`, `CONTAINS`, `ENDS_WITH`, `ENDS_WITH_ANY_OF`, `EQUALS`, `EQUALS_ANY_OF`, `EXISTS` and `REGEX_MATCHES`
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider
- **value** (String) The value to compare to
- **values** (Set of String) The values to compare to


<a id="nestedblock--conditions--condition--comparison--string_request_attribute"></a>
### Nested Schema for `conditions.condition.comparison.zos_call_type`

Required:

- **request_attribute** (String) No documentation available for this attribute

Optional:

- **case_sensitive** (Boolean) The comparison is case-sensitive (`true`) or not case-sensitive (`false`)
- **match_on_child_calls** (Boolean) If `true`, the request attribute is matched on child service calls. Default is `false`
- **operator** (String) Operator of the comparison. You can reverse it by setting `negate` to `true`. Possible values are `BEGINS_WITH`, `BEGINS_WITH_ANY_OF`, `CONTAINS`, `ENDS_WITH`, `ENDS_WITH_ANY_OF`, `EQUALS`, `EQUALS_ANY_OF`, `EXISTS` and `REGEX_MATCHES`
- **source** (Block List, Max: 1) Defines valid sources of request attributes for conditions or placeholders (see [below for nested schema](#nestedblock--conditions--condition--comparison--zos_call_type--source))
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider
- **value** (String) The value to compare to
- **values** (Set of String) The values to compare to

<a id="nestedblock--conditions--condition--comparison--zos_call_type--source"></a>
### Nested Schema for `conditions.condition.comparison.zos_call_type.source`

Optional:

- **management_zone** (String) Use only request attributes from services that belong to this management zone.. Use either this or `serviceTag`
- **service_tag** (Block List, Max: 1) Use only request attributes from services that have this tag. Use either this or `managementZone` (see [below for nested schema](#nestedblock--conditions--condition--comparison--zos_call_type--source--service_tag))
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider

<a id="nestedblock--conditions--condition--comparison--zos_call_type--source--service_tag"></a>
### Nested Schema for `conditions.condition.comparison.zos_call_type.source.unknowns`

Required:

- **key** (String) The key of the tag. For custom tags, put the tag value here. The key allows categorization of multiple tags. It is possible that there are multiple values for a single key which will all be represented as standalone tags. Therefore, the key does not have the semantic of a map key but is more like a key of a key-value tuple. In some cases, for example custom tags, the key represents the actual tag value and the value field is not set – those are called valueless tags

Optional:

- **context** (String) The origin of the tag, such as AWS or Cloud Foundry. For custom tags use the `CONTEXTLESS` value. The context is set for tags that are automatically imported by OneAgent (for example, from the AWS console or environment variables). It’s useful for determining the origin of tags when not manually defined, and it also helps to prevent clashes with other existing tags. If the tag is not automatically imported, `CONTEXTLESS` set. Possible values are `AWS`, `AWS_GENERIC`, `AZURE`, `CLOUD_FOUNDRY`, `CONTEXTLESS`, `ENVIRONMENT`, `GOOGLE_COMPUTE_ENGINE` and `KUBERNETES`
- **tag_key** (Block List, Max: 1) has no documentation (see [below for nested schema](#nestedblock--conditions--condition--comparison--zos_call_type--source--unknowns--tag_key))
- **value** (String) The value of the tag. Not applicable to custom tags. If a tag does have a separate key and value (in the textual representation they are split by the colon ‘:’), this field is set with the actual value. Key-value pairs can occur for automatically imported tags and tags set by rules if extractors are used

<a id="nestedblock--conditions--condition--comparison--zos_call_type--source--unknowns--tag_key"></a>
### Nested Schema for `conditions.condition.comparison.zos_call_type.source.unknowns.value`

Optional:

- **context** (String) has no documentation
- **key** (String) has no documentation





<a id="nestedblock--conditions--condition--comparison--tag"></a>
### Nested Schema for `conditions.condition.comparison.zos_call_type`

Optional:

- **operator** (String) Operator of the comparison. You can reverse it by setting `negate` to `true`. Possible values are `EQUALS`, `EQUALS_ANY_OF`, `TAG_KEY_EQUALS` and `TAG_KEY_EQUALS_ANY_OF`
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider
- **values** (Block List, Max: 1) The values to compare to (see [below for nested schema](#nestedblock--conditions--condition--comparison--zos_call_type--values))

<a id="nestedblock--conditions--condition--comparison--zos_call_type--values"></a>
### Nested Schema for `conditions.condition.comparison.zos_call_type.values`

Optional:

- **value** (Block List) The values to compare to (see [below for nested schema](#nestedblock--conditions--condition--comparison--zos_call_type--values--value))

<a id="nestedblock--conditions--condition--comparison--zos_call_type--values--value"></a>
### Nested Schema for `conditions.condition.comparison.zos_call_type.values.value`

Required:

- **context** (String) The origin of the tag, such as AWS or Cloud Foundry. Custom tags use the `CONTEXTLESS` value. Possible values are `AWS`, `AWS_GENERIC`, `AZURE`, `CLOUD_FOUNDRY`, `CONTEXTLESS`, `ENVIRONMENT`, `GOOGLE_CLOUD` and `KUBERNETES`
- **key** (String) The key of the tag. Custom tags have the tag value here

Optional:

- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider
- **value** (String) The value of the tag. Not applicable to custom tags




<a id="nestedblock--conditions--condition--comparison--zos_call_type"></a>
### Nested Schema for `conditions.condition.comparison.zos_call_type`

Optional:

- **operator** (String) Operator of the comparison. You can reverse it by setting `negate` to `true`. Possible values are `EQUALS`, `EQUALS_ANY_OF` and `EXISTS`
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider
- **value** (String) The value to compare to. Possible values are `CTG`, `DPL`, `EXPLICIT_ADK`, `IMS_CONNECT`, `IMS_CONNECT_API`, `IMS_ITRA`, `IMS_MSC`, `IMS_PGM_SWITCH`, `IMS_SHARED_QUEUES`, `IMS_TRANS_EXEC`, `MQ`, `SOAP`, `START`, `TX` and `UNKNOWN`
- **values** (Set of String) The values to compare to. Possible values are `CTG`, `DPL`, `EXPLICIT_ADK`, `IMS_CONNECT`, `IMS_CONNECT_API`, `IMS_ITRA`, `IMS_MSC`, `IMS_PGM_SWITCH`, `IMS_SHARED_QUEUES`, `IMS_TRANS_EXEC`, `MQ`, `SOAP`, `START`, `TX` and `UNKNOWN`





<a id="nestedblock--dimension_definition"></a>
### Nested Schema for `dimension_definition`

Required:

- **dimension** (String) The dimension value pattern. You can define custom placeholders in the `placeholders` field and use them here
- **name** (String) The name of the dimension
- **top_x** (Number) The number of top values to be calculated
- **top_x_aggregation** (String) The aggregation of the dimension. Possible values are `AVERAGE`, `COUNT`, `MAX`, `MIN`, `OF_INTEREST_RATIO`, `OTHER_RATIO`, `SINGLE_VALUE` and `SUM`
- **top_x_direction** (String) How to calculate the **topX** values. Possible values are `ASCENDING` and `DESCENDING`

Optional:

- **placeholders** (Block List, Max: 1) The list of custom placeholders to be used in a dimension value pattern (see [below for nested schema](#nestedblock--dimension_definition--placeholders))
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider

<a id="nestedblock--dimension_definition--placeholders"></a>
### Nested Schema for `dimension_definition.placeholders`

Optional:

- **placeholder** (Block List) A custom placeholder to be used in a dimension value pattern (see [below for nested schema](#nestedblock--dimension_definition--placeholders--placeholder))

<a id="nestedblock--dimension_definition--placeholders--placeholder"></a>
### Nested Schema for `dimension_definition.placeholders.placeholder`

Required:

- **attribute** (String) The attribute to extract from. You can only use attributes of the **string** type. Possible values are `ACTOR_SYSTEM`, `AKKA_ACTOR_CLASS_NAME`, `AKKA_ACTOR_MESSAGE_TYPE`, `AKKA_ACTOR_PATH`, `APPLICATION_BUILD_VERSION`, `APPLICATION_RELEASE_VERSION`, `AZURE_FUNCTIONS_FUNCTION_NAME`, `AZURE_FUNCTIONS_SITE_NAME`, `CICS_PROGRAM_NAME`, `CICS_SYSTEM_ID`, `CICS_TASK_ID`, `CICS_TRANSACTION_ID`, `CICS_USER_ID`, `CPU_TIME`, `CTG_GATEWAY_URL`, `CTG_PROGRAM`, `CTG_SERVER_NAME`, `CTG_TRANSACTION_ID`, `CUSTOMSERVICE_CLASS`, `CUSTOMSERVICE_METHOD`, `DATABASE_CHILD_CALL_COUNT`, `DATABASE_CHILD_CALL_TIME`, `DATABASE_HOST`, `DATABASE_NAME`, `DATABASE_TYPE`, `DATABASE_URL`, `DISK_IO_TIME`, `ERROR_COUNT`, `ESB_APPLICATION_NAME`, `ESB_INPUT_TYPE`, `ESB_LIBRARY_NAME`, `ESB_MESSAGE_FLOW_NAME`, `EXCEPTION_CLASS`, `EXCEPTION_MESSAGE`, `FAILED_STATE`, `FAILURE_REASON`, `FLAW_STATE`, `HTTP_REQUEST_METHOD`, `HTTP_STATUS`, `HTTP_STATUS_CLASS`, `IMS_PROGRAM_NAME`, `IMS_TRANSACTION_ID`, `IMS_USER_ID`, `IO_TIME`, `IS_KEY_REQUEST`, `LAMBDA_COLDSTART`, `LOCK_TIME`, `MESSAGING_DESTINATION_TYPE`, `MESSAGING_IS_TEMPORARY_QUEUE`, `MESSAGING_QUEUE_NAME`, `MESSAGING_QUEUE_VENDOR`, `NETWORK_IO_TIME`, `NON_DATABASE_CHILD_CALL_COUNT`, `NON_DATABASE_CHILD_CALL_TIME`, `PROCESS_GROUP_NAME`, `PROCESS_GROUP_TAG`, `REMOTE_ENDPOINT`, `REMOTE_METHOD`, `REMOTE_SERVICE_NAME`, `REQUEST_NAME`, `REQUEST_TYPE`, `RESPONSE_TIME`, `RESPONSE_TIME_CLIENT`, `RMI_CLASS`, `RMI_METHOD`, `SERVICE_DISPLAY_NAME`, `SERVICE_NAME`, `SERVICE_PORT`, `SERVICE_PUBLIC_DOMAIN_NAME`, `SERVICE_REQUEST_ATTRIBUTE`, `SERVICE_TAG`, `SERVICE_TYPE`, `SERVICE_WEB_APPLICATION_ID`, `SERVICE_WEB_CONTEXT_ROOT`, `SERVICE_WEB_SERVER_NAME`, `SERVICE_WEB_SERVICE_NAME`, `SERVICE_WEB_SERVICE_NAMESPACE`, `SUSPENSION_TIME`, `TOTAL_PROCESSING_TIME`, `WAIT_TIME`, `WEBREQUEST_QUERY`, `WEBREQUEST_RELATIVE_URL`, `WEBREQUEST_URL`, `WEBREQUEST_URL_HOST`, `WEBREQUEST_URL_PATH`, `WEBREQUEST_URL_PORT`, `WEBSERVICE_ENDPOINT`, `WEBSERVICE_METHOD` and `ZOS_CALL_TYPE`
- **kind** (String) The type of extraction. Defines either usage of regular expression (`regex`) or the position of request attribute value to be extracted. When the `attribute` is `SERVICE_REQUEST_ATTRIBUTE` attribute and `aggregation` is `COUNT`, needs to be set to `ORIGINAL_TEXT`. Possible values are 	`AFTER_DELIMITER`, `BEFORE_DELIMITER`, `BETWEEN_DELIMITER`, `ORIGINAL_TEXT` and `REGEX_EXTRACTION`
- **name** (String) The name of the placeholder. Use it in the naming pattern as `{name}`

Optional:

- **aggregation** (String) Which value of the request attribute must be used when it occurs across multiple child requests. Only applicable for the `SERVICE_REQUEST_ATTRIBUTE` attribute, when **useFromChildCalls** is `true`. For the `COUNT` aggregation, the **kind** field is not applicable. Possible values are `COUNT`, `FIRST` and `LAST`.
- **delimiter_or_regex** (String) Depending on the `kind` value:


* `REGEX_EXTRACTION`: The regular expression.


* `BETWEEN_DELIMITER`: The opening delimiter string to look for.


* All other values: The delimiter string to look for
- **end_delimiter** (String) The closing delimiter string to look for. Required if the `kind` value is `BETWEEN_DELIMITER`. Not applicable otherwise
- **normalization** (String) The format of the extracted string. Possible values are `ORIGINAL`, `TO_LOWER_CASE` and `TO_UPPER_CASE`
- **request_attribute** (String) The request attribute to extract from. Required if the `kind` value is `SERVICE_REQUEST_ATTRIBUTE`. Not applicable otherwise
- **source** (Block List, Max: 1) Defines valid sources of request attributes for conditions or placeholders (see [below for nested schema](#nestedblock--dimension_definition--placeholders--placeholder--source))
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider
- **use_from_child_calls** (Boolean) If `true` request attribute will be taken from a child service call. Only applicable for the `SERVICE_REQUEST_ATTRIBUTE` attribute. Defaults to `false`

<a id="nestedblock--dimension_definition--placeholders--placeholder--source"></a>
### Nested Schema for `dimension_definition.placeholders.placeholder.use_from_child_calls`

Optional:

- **management_zone** (String) Use only request attributes from services that belong to this management zone.. Use either this or `serviceTag`
- **service_tag** (Block List, Max: 1) Use only request attributes from services that have this tag. Use either this or `managementZone` (see [below for nested schema](#nestedblock--dimension_definition--placeholders--placeholder--use_from_child_calls--service_tag))
- **unknowns** (String) allows for configuring properties that are not explicitly supported by the current version of this provider

<a id="nestedblock--dimension_definition--placeholders--placeholder--use_from_child_calls--service_tag"></a>
### Nested Schema for `dimension_definition.placeholders.placeholder.use_from_child_calls.service_tag`

Required:

- **key** (String) The key of the tag. For custom tags, put the tag value here. The key allows categorization of multiple tags. It is possible that there are multiple values for a single key which will all be represented as standalone tags. Therefore, the key does not have the semantic of a map key but is more like a key of a key-value tuple. In some cases, for example custom tags, the key represents the actual tag value and the value field is not set – those are called valueless tags

Optional:

- **context** (String) The origin of the tag, such as AWS or Cloud Foundry. For custom tags use the `CONTEXTLESS` value. The context is set for tags that are automatically imported by OneAgent (for example, from the AWS console or environment variables). It’s useful for determining the origin of tags when not manually defined, and it also helps to prevent clashes with other existing tags. If the tag is not automatically imported, `CONTEXTLESS` set. Possible values are `AWS`, `AWS_GENERIC`, `AZURE`, `CLOUD_FOUNDRY`, `CONTEXTLESS`, `ENVIRONMENT`, `GOOGLE_COMPUTE_ENGINE` and `KUBERNETES`
- **tag_key** (Block List, Max: 1) has no documentation (see [below for nested schema](#nestedblock--dimension_definition--placeholders--placeholder--use_from_child_calls--service_tag--tag_key))
- **value** (String) The value of the tag. Not applicable to custom tags. If a tag does have a separate key and value (in the textual representation they are split by the colon ‘:’), this field is set with the actual value. Key-value pairs can occur for automatically imported tags and tags set by rules if extractors are used

<a id="nestedblock--dimension_definition--placeholders--placeholder--use_from_child_calls--service_tag--tag_key"></a>
### Nested Schema for `dimension_definition.placeholders.placeholder.use_from_child_calls.service_tag.value`

Optional:

- **context** (String) has no documentation
- **key** (String) has no documentation

