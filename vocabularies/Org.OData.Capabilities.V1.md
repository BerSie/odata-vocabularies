# Capabilities Vocabulary
**Namespace: [Org.OData.Capabilities.V1](Org.OData.Capabilities.V1.xml)**

Terms describing capabilities of a service


There are some capabilities which are strongly recommended for services to support even
though they are optional. Support for $top and $skip is a good example as
supporting these query options helps with performance of a service and are essential. Such
capabilities are assumed to be default capabilities of an OData service even in
the case that a capabilities annotation doesn’t exist. Capabilities annotations are
mainly expected to be used to explicitly specify that a service doesn’t support such
capabilities. Capabilities annotations can as well be used to declaratively
specify the support of such capabilities.

On the other hand, there are some capabilities that a service may choose to support or
not support and in varying degrees. $filter and $orderby are such good examples.
This vocabulary aims to define terms to specify support or no support for such
capabilities.

A service is assumed to support by default the following capabilities even though an
annotation doesn’t exist:
- Countability ($count)
- Client pageability ($top, $skip)
- Expandability ($expand)
- Indexability by key
- Batch support ($batch)
- Navigability of navigation properties

A service is expected to support the following capabilities. If not supported, the
service is expected to call out the restrictions using annotations:
- Filterability ($filter)
- Sortability ($orderby)
- Queryability of top level entity sets
- Query functions

A client cannot assume that a service supports certain capabilities. A client can try, but
it needs to be prepared to handle an error in case the following capabilities are not
supported:
- Insertability
- Updatability
- Deletability
        


## Terms

Term|Type|Description
:---|:---|:----------
[ConformanceLevel](Org.OData.Capabilities.V1.xml#L115)|[ConformanceLevelType](#ConformanceLevelType)|<a name="ConformanceLevel"></a>The conformance level achieved by this service
[SupportedFormats](Org.OData.Capabilities.V1.xml#L132)|\[MediaType\]|<a name="SupportedFormats"></a>Media types of supported formats, including format parameters
[SupportedMetadataFormats](Org.OData.Capabilities.V1.xml#L137)|\[MediaType\]|<a name="SupportedMetadataFormats"></a>Media types of supported formats for $metadata, including format parameters
[AcceptableEncodings](Org.OData.Capabilities.V1.xml#L142)|\[String\]|<a name="AcceptableEncodings"></a>List of acceptable compression methods for ($batch) requests, e.g. gzip
[AsynchronousRequestsSupported](Org.OData.Capabilities.V1.xml#L148)|[Tag](Org.OData.Core.V1.md#Tag)|<a name="AsynchronousRequestsSupported"></a>Service supports the asynchronous request preference
[BatchContinueOnErrorSupported](Org.OData.Capabilities.V1.xml#L152)|[Tag](Org.OData.Core.V1.md#Tag)|<a name="BatchContinueOnErrorSupported"></a>Service supports the continue on error preference. Supports $batch requests. Services that apply the BatchContinueOnErrorSupported term should also specify the ContinueOnErrorSupported property from the BatchSupport term.
[IsolationSupported](Org.OData.Capabilities.V1.xml#L157)|[IsolationLevel](#IsolationLevel)|<a name="IsolationSupported"></a>Supported odata.isolation levels
[CrossJoinSupported](Org.OData.Capabilities.V1.xml#L167)|[Tag](Org.OData.Core.V1.md#Tag)|<a name="CrossJoinSupported"></a>Supports cross joins for the entity sets in this container
[CallbackSupported](Org.OData.Capabilities.V1.xml#L171)|[CallbackType](#CallbackType)|<a name="CallbackSupported"></a>Supports callbacks for the specified protocols
[ChangeTracking](Org.OData.Capabilities.V1.xml#L194)|[ChangeTrackingType](#ChangeTrackingType)|<a name="ChangeTracking"></a>Change tracking capabilities of this service or entity set
[CountRestrictions](Org.OData.Capabilities.V1.xml#L211)|[CountRestrictionsType](#CountRestrictionsType)|<a name="CountRestrictions"></a>Restrictions on /$count path suffix and $count=true system query option
[NavigationRestrictions](Org.OData.Capabilities.V1.xml#L226)|[NavigationRestrictionsType](#NavigationRestrictionsType)|<a name="NavigationRestrictions"></a>Restrictions on navigating properties according to OData URL conventions<p>Restrictions specified on an entity set are valid whether the request is directly to the entity set or through a navigation property bound to that entity set. Services can specify a different set of restrictions specific to a path, in which case the more specific restrictions take precedence.</p>
[IndexableByKey](Org.OData.Capabilities.V1.xml#L294)|[Tag](Org.OData.Core.V1.md#Tag)|<a name="IndexableByKey"></a>Supports key values according to OData URL conventions
[TopSupported](Org.OData.Capabilities.V1.xml#L298)|[Tag](Org.OData.Core.V1.md#Tag)|<a name="TopSupported"></a>Supports $top
[SkipSupported](Org.OData.Capabilities.V1.xml#L301)|[Tag](Org.OData.Core.V1.md#Tag)|<a name="SkipSupported"></a>Supports $skip
[BatchSupported](Org.OData.Capabilities.V1.xml#L305)|[Tag](Org.OData.Core.V1.md#Tag)|<a name="BatchSupported"></a>Supports $batch requests. Services that apply the BatchSupported term should also apply the more comprehensive BatchSupport term.
[BatchSupport](Org.OData.Capabilities.V1.xml#L310)|[BatchSupportType](#BatchSupportType)|<a name="BatchSupport"></a>Batch Support for the service
[FilterFunctions](Org.OData.Capabilities.V1.xml#L331)|\[String\]|<a name="FilterFunctions"></a>List of functions and operators supported in $filter
[FilterRestrictions](Org.OData.Capabilities.V1.xml#L335)|[FilterRestrictionsType](#FilterRestrictionsType)|<a name="FilterRestrictions"></a>Restrictions on $filter expressions
[SortRestrictions](Org.OData.Capabilities.V1.xml#L404)|[SortRestrictionsType](#SortRestrictionsType)|<a name="SortRestrictions"></a>Restrictions on $orderby expressions
[ExpandRestrictions](Org.OData.Capabilities.V1.xml#L422)|[ExpandRestrictionsType](#ExpandRestrictionsType)|<a name="ExpandRestrictions"></a>Restrictions on $expand expressions
[SearchRestrictions](Org.OData.Capabilities.V1.xml#L438)|[SearchRestrictionsType](#SearchRestrictionsType)|<a name="SearchRestrictions"></a>Restrictions on $search expressions
[KeyAsSegmentSupported](Org.OData.Capabilities.V1.xml#L470)|[Tag](Org.OData.Core.V1.md#Tag)|<a name="KeyAsSegmentSupported"></a>Supports [key-as-segment convention](http://docs.oasis-open.org/odata/odata/v4.01/odata-v4.01-part2-url-conventions.html#sec_KeyasSegmentConvention) for addressing entities within a collection
[InsertRestrictions](Org.OData.Capabilities.V1.xml#L477)|[InsertRestrictionsType](#InsertRestrictionsType)|<a name="InsertRestrictions"></a>Restrictions on insert operations
[DeepInsertSupport](Org.OData.Capabilities.V1.xml#L493)|[DeepInsertSupportType](#DeepInsertSupportType)|<a name="DeepInsertSupport"></a>Deep Insert Support of the annotated resource (the whole service, an entity set, or a collection-valued resource)
[UpdateRestrictions](Org.OData.Capabilities.V1.xml#L507)|[UpdateRestrictionsType](#UpdateRestrictionsType)|<a name="UpdateRestrictions"></a>Restrictions on update operations
[DeleteRestrictions](Org.OData.Capabilities.V1.xml#L523)|[DeleteRestrictionsType](#DeleteRestrictionsType)|<a name="DeleteRestrictions"></a>Restrictions on delete operations
[CollectionPropertyRestrictions](Org.OData.Capabilities.V1.xml#L539)|\[[CollectionPropertyRestrictionsType](#CollectionPropertyRestrictionsType)\]|<a name="CollectionPropertyRestrictions"></a>Describes restrictions on operations applied to collection-valued structural properties

## <a name="ConformanceLevelType"></a>[ConformanceLevelType](Org.OData.Capabilities.V1.xml#L118)


Member|Value|Description
:-----|----:|:----------
[Minimal](Org.OData.Capabilities.V1.xml#L119)|0|Minimal conformance level
[Intermediate](Org.OData.Capabilities.V1.xml#L122)|1|Intermediate conformance level
[Advanced](Org.OData.Capabilities.V1.xml#L125)|2|Advanced conformance level

## <a name="IsolationLevel"></a>[IsolationLevel](Org.OData.Capabilities.V1.xml#L160)


Flag Member|Value|Description
:-----|----:|:----------
[Snapshot](Org.OData.Capabilities.V1.xml#L161)|1|All data returned for a request, including multiple requests within a batch or results retrieved across multiple pages, will be consistent as of a single point in time

## <a name="CallbackType"></a>[CallbackType](Org.OData.Capabilities.V1.xml#L174)
A non-empty collection lists the full set of supported protocols. A empty collection means 'only HTTP is supported'

Property|Type|Description
:-------|:---|:----------
[CallbackProtocols](Org.OData.Capabilities.V1.xml#L175)|\[[CallbackProtocol](#CallbackProtocol)\]|List of supported callback protocols, e.g. `http` or `wss`

## <a name="CallbackProtocol"></a>[CallbackProtocol](Org.OData.Capabilities.V1.xml#L181)


Property|Type|Description
:-------|:---|:----------
[Id](Org.OData.Capabilities.V1.xml#L182)|String|Protocol Identifier
[UrlTemplate](Org.OData.Capabilities.V1.xml#L185)|String|URL Template including parameters. Parameters are enclosed in curly braces {} as defined in RFC6570
[DocumentationUrl](Org.OData.Capabilities.V1.xml#L188)|URL|Human readable description of the meaning of the URL Template parameters

## <a name="ChangeTrackingType"></a>[ChangeTrackingType](Org.OData.Capabilities.V1.xml#L197)


Property|Type|Description
:-------|:---|:----------
[Supported](Org.OData.Capabilities.V1.xml#L198)|Boolean|This entity set supports the odata.track-changes preference
[FilterableProperties](Org.OData.Capabilities.V1.xml#L201)|\[PropertyPath\]|Change tracking supports filters on these properties
[ExpandableProperties](Org.OData.Capabilities.V1.xml#L204)|\[NavigationPropertyPath\]|Change tracking supports these properties expanded

## <a name="CountRestrictionsType"></a>[CountRestrictionsType](Org.OData.Capabilities.V1.xml#L214)


Property|Type|Description
:-------|:---|:----------
[Countable](Org.OData.Capabilities.V1.xml#L215)|Boolean|Entities can be counted
[NonCountableProperties](Org.OData.Capabilities.V1.xml#L218)|\[PropertyPath\]|These collection properties do not allow /$count segments
[NonCountableNavigationProperties](Org.OData.Capabilities.V1.xml#L221)|\[NavigationPropertyPath\]|These navigation properties do not allow /$count segments

## <a name="NavigationRestrictionsType"></a>[NavigationRestrictionsType](Org.OData.Capabilities.V1.xml#L231)


Property|Type|Description
:-------|:---|:----------
[Navigability](Org.OData.Capabilities.V1.xml#L232)|[NavigationType](#NavigationType)|Supported Navigability
[RestrictedProperties](Org.OData.Capabilities.V1.xml#L235)|\[[NavigationPropertyRestriction](#NavigationPropertyRestriction)\]|List of navigation properties with restrictions

## <a name="NavigationPropertyRestriction"></a>[NavigationPropertyRestriction](Org.OData.Capabilities.V1.xml#L239)


Property|Type|Description
:-------|:---|:----------
[NavigationProperty](Org.OData.Capabilities.V1.xml#L240)|NavigationPropertyPath|Navigation properties can be navigated
[Navigability](Org.OData.Capabilities.V1.xml#L243)|[NavigationType](#NavigationType)|Navigation properties can be navigated to this level
[FilterFunctions](Org.OData.Capabilities.V1.xml#L246)|\[String\]|List of functions and operators supported in $filter. If null, all functions and operators may be attempted.
[FilterRestrictions](Org.OData.Capabilities.V1.xml#L250)|[FilterRestrictionsType](#FilterRestrictionsType)|Restrictions on $filter expressions
[SearchRestrictions](Org.OData.Capabilities.V1.xml#L253)|[SearchRestrictionsType](#SearchRestrictionsType)|Restrictions on $search expressions
[SortRestrictions](Org.OData.Capabilities.V1.xml#L256)|[SortRestrictionsType](#SortRestrictionsType)|Restrictions on $orderby expressions
[TopSupported](Org.OData.Capabilities.V1.xml#L259)|[Tag](Org.OData.Core.V1.md#Tag)|Supports $top
[SkipSupported](Org.OData.Capabilities.V1.xml#L262)|[Tag](Org.OData.Core.V1.md#Tag)|Supports $skip
[IndexableByKey](Org.OData.Capabilities.V1.xml#L265)|[Tag](Org.OData.Core.V1.md#Tag)|Supports key values according to OData URL conventions
[InsertRestrictions](Org.OData.Capabilities.V1.xml#L268)|[InsertRestrictionsType](#InsertRestrictionsType)|Restrictions on insert operations
[DeepInsertSupport](Org.OData.Capabilities.V1.xml#L271)|[DeepInsertSupportType](#DeepInsertSupportType)|Deep Insert Support of the annotated resource (the whole service, an entity set, or a collection-valued resource)
[UpdateRestrictions](Org.OData.Capabilities.V1.xml#L275)|[UpdateRestrictionsType](#UpdateRestrictionsType)|Restrictions on update operations
[DeleteRestrictions](Org.OData.Capabilities.V1.xml#L278)|[DeleteRestrictionsType](#DeleteRestrictionsType)|Restrictions on delete operations

## <a name="NavigationType"></a>[NavigationType](Org.OData.Capabilities.V1.xml#L282)


Member|Value|Description
:-----|----:|:----------
[Recursive](Org.OData.Capabilities.V1.xml#L283)|0|Navigation properties can be recursively navigated
[Single](Org.OData.Capabilities.V1.xml#L286)|1|Navigation properties can be navigated to a single level
[None](Org.OData.Capabilities.V1.xml#L289)|2|Navigation properties are not navigable

## <a name="BatchSupportType"></a>[BatchSupportType](Org.OData.Capabilities.V1.xml#L313)


Property|Type|Description
:-------|:---|:----------
[Supported](Org.OData.Capabilities.V1.xml#L314)|Boolean|Service supports requests to $batch
[ContinueOnErrorSupported](Org.OData.Capabilities.V1.xml#L317)|Boolean|Service supports the continue on error preference
[ReferencesInRequestBodiesSupported](Org.OData.Capabilities.V1.xml#L320)|Boolean|Service supports Content-ID referencing in request bodies
[ReferencesAcrossChangeSetsSupported](Org.OData.Capabilities.V1.xml#L323)|Boolean|Service supports Content-ID referencing across change sets
[EtagReferencesSupported](Org.OData.Capabilities.V1.xml#L326)|Boolean|Service supports referencing Etags from previous requests

## <a name="FilterRestrictionsType"></a>[FilterRestrictionsType](Org.OData.Capabilities.V1.xml#L338)


Property|Type|Description
:-------|:---|:----------
[Filterable](Org.OData.Capabilities.V1.xml#L339)|Boolean|$filter is supported
[RequiresFilter](Org.OData.Capabilities.V1.xml#L342)|Boolean|$filter is required
[RequiredProperties](Org.OData.Capabilities.V1.xml#L345)|\[PropertyPath\]|These properties must be specified in the $filter clause (properties of derived types are not allowed here)
[NonFilterableProperties](Org.OData.Capabilities.V1.xml#L349)|\[PropertyPath\]|These structural properties cannot be used in $filter expressions
[FilterExpressionRestrictions](Org.OData.Capabilities.V1.xml#L352)|\[[FilterExpressionRestrictionType](#FilterExpressionRestrictionType)\]|These properties only allow a subset of expressions
[MaxLevels](Org.OData.Capabilities.V1.xml#L355)|Int32|The maximum number of levels (including recursion) that can be traversed in a $filter expression. A value of -1 indicates there is no restriction.

## <a name="FilterExpressionRestrictionType"></a>[FilterExpressionRestrictionType](Org.OData.Capabilities.V1.xml#L360)


Property|Type|Description
:-------|:---|:----------
[Property](Org.OData.Capabilities.V1.xml#L361)|PropertyPath|Path to the restricted property
[AllowedExpressions](Org.OData.Capabilities.V1.xml#L364)|[FilterExpressionType](#FilterExpressionType)|Allowed subset of expressions

## <a name="FilterExpressionType"></a>[FilterExpressionType](Org.OData.Capabilities.V1.xml#L368)
**Type:** String



Allowed Value|Description
:------------|:----------
[SingleValue](Org.OData.Capabilities.V1.xml#L371)|Property can be used in a single eq clause
[MultiValue](Org.OData.Capabilities.V1.xml#L375)|Property can be used in a single in clause
[SingleRange](Org.OData.Capabilities.V1.xml#L379)|Property can be used in at most one ge and/or one le clause, separated by and
[SearchExpression](Org.OData.Capabilities.V1.xml#L383)|String property can be used as first operand in startswith, endswith, and contains clauses
[MultiRange](Org.OData.Capabilities.V1.xml#L387)|Property can be compared to a union of one or more closed, half-open, or open intervals<p>The filter expression for this property consists of one or more interval expressions combined by OR. A single interval expression is either a single comparison of the property and a literal value with eq, le, lt, ge, or gt, or pair of boundaries combined by AND and enclosed in parentheses. The lower boundary is either ge or gt, the upper boundary either le or lt.</p>
[MultiRangeOrSearchExpression](Org.OData.Capabilities.V1.xml#L393)|Property can be compared to a union of zero or more closed, half-open, or open intervals plus zero or more simple string patterns<p>The filter expression for this property consists of one or more interval expressions or string comparison functions combined by OR. See MultiRange for a definition of an interval expression. See SearchExpression for the allowed string comparison functions.</p>

## <a name="SortRestrictionsType"></a>[SortRestrictionsType](Org.OData.Capabilities.V1.xml#L407)


Property|Type|Description
:-------|:---|:----------
[Sortable](Org.OData.Capabilities.V1.xml#L408)|Boolean|$orderby is supported
[AscendingOnlyProperties](Org.OData.Capabilities.V1.xml#L411)|\[PropertyPath\]|These properties can only be used for sorting in Ascending order
[DescendingOnlyProperties](Org.OData.Capabilities.V1.xml#L414)|\[PropertyPath\]|These properties can only be used for sorting in Descending order
[NonSortableProperties](Org.OData.Capabilities.V1.xml#L417)|\[PropertyPath\]|These structural properties cannot be used in $orderby expressions

## <a name="ExpandRestrictionsType"></a>[ExpandRestrictionsType](Org.OData.Capabilities.V1.xml#L425)


Property|Type|Description
:-------|:---|:----------
[Expandable](Org.OData.Capabilities.V1.xml#L426)|Boolean|$expand is supported
[NonExpandableProperties](Org.OData.Capabilities.V1.xml#L429)|\[NavigationPropertyPath\]|These properties cannot be used in $expand expressions
[MaxLevels](Org.OData.Capabilities.V1.xml#L432)|Int32|The maximum number of levels that can be expanded in a $expand expression. A value of -1 indicates there is no restriction.

## <a name="SearchRestrictionsType"></a>[SearchRestrictionsType](Org.OData.Capabilities.V1.xml#L441)


Property|Type|Description
:-------|:---|:----------
[Searchable](Org.OData.Capabilities.V1.xml#L442)|Boolean|$search is supported
[UnsupportedExpressions](Org.OData.Capabilities.V1.xml#L445)|[SearchExpressions](#SearchExpressions)|Expressions not supported in $search

## <a name="SearchExpressions"></a>[SearchExpressions](Org.OData.Capabilities.V1.xml#L449)


Flag Member|Value|Description
:-----|----:|:----------
[none](Org.OData.Capabilities.V1.xml#L450)|0|Single search term
[AND](Org.OData.Capabilities.V1.xml#L453)|1|Multiple search terms separated by AND
[OR](Org.OData.Capabilities.V1.xml#L456)|2|Multiple search terms separated by OR
[NOT](Org.OData.Capabilities.V1.xml#L459)|4|Search terms preceded by NOT
[phrase](Org.OData.Capabilities.V1.xml#L462)|8|Search phrases enclosed in double quotes
[group](Org.OData.Capabilities.V1.xml#L465)|16|Precedence grouping of search expressions with parentheses

## <a name="InsertRestrictionsType"></a>[InsertRestrictionsType](Org.OData.Capabilities.V1.xml#L480)


Property|Type|Description
:-------|:---|:----------
[Insertable](Org.OData.Capabilities.V1.xml#L481)|Boolean|Entities can be inserted
[NonInsertableNavigationProperties](Org.OData.Capabilities.V1.xml#L484)|\[NavigationPropertyPath\]|These navigation properties do not allow deep inserts
[MaxLevels](Org.OData.Capabilities.V1.xml#L487)|Int32|The maximum number of navigation properties that can be traversed when addressing the collection to insert into. A value of -1 indicates there is no restriction.

## <a name="DeepInsertSupportType"></a>[DeepInsertSupportType](Org.OData.Capabilities.V1.xml#L497)


Property|Type|Description
:-------|:---|:----------
[Supported](Org.OData.Capabilities.V1.xml#L498)|Boolean|Annotation target supports deep inserts
[ContentIDSupported](Org.OData.Capabilities.V1.xml#L501)|Boolean|Annotation target supports accepting and returning nested entities annotated with the `Core.ContentID` instance annotation.

## <a name="UpdateRestrictionsType"></a>[UpdateRestrictionsType](Org.OData.Capabilities.V1.xml#L510)


Property|Type|Description
:-------|:---|:----------
[Updatable](Org.OData.Capabilities.V1.xml#L511)|Boolean|Entities can be updated
[NonUpdatableNavigationProperties](Org.OData.Capabilities.V1.xml#L514)|\[NavigationPropertyPath\]|These navigation properties do not allow rebinding
[MaxLevels](Org.OData.Capabilities.V1.xml#L517)|Int32|The maximum number of navigation properties that can be traversed when addressing the collection or entity to update. A value of -1 indicates there is no restriction.

## <a name="DeleteRestrictionsType"></a>[DeleteRestrictionsType](Org.OData.Capabilities.V1.xml#L526)


Property|Type|Description
:-------|:---|:----------
[Deletable](Org.OData.Capabilities.V1.xml#L527)|Boolean|Entities can be deleted
[NonDeletableNavigationProperties](Org.OData.Capabilities.V1.xml#L530)|\[NavigationPropertyPath\]|These navigation properties do not allow DeleteLink requests
[MaxLevels](Org.OData.Capabilities.V1.xml#L533)|Int32|The maximum number of navigation properties that can be traversed when addressing the collection to delete from or the entity to delete. A value of -1 indicates there is no restriction.

## <a name="CollectionPropertyRestrictionsType"></a>[CollectionPropertyRestrictionsType](Org.OData.Capabilities.V1.xml#L542)


Property|Type|Description
:-------|:---|:----------
[CollectionProperty](Org.OData.Capabilities.V1.xml#L543)|PropertyPath|Restricted Collection-valued property
[FilterFunctions](Org.OData.Capabilities.V1.xml#L546)|\[String\]|List of functions and operators supported in $filter. If null, all functions and operators may be attempted
[FilterRestrictions](Org.OData.Capabilities.V1.xml#L550)|[FilterRestrictionsType](#FilterRestrictionsType)|Restrictions on $filter expressions
[SearchRestrictions](Org.OData.Capabilities.V1.xml#L553)|[SearchRestrictionsType](#SearchRestrictionsType)|Restrictions on $search expressions
[SortRestrictions](Org.OData.Capabilities.V1.xml#L556)|[SortRestrictionsType](#SortRestrictionsType)|Restrictions on $orderby expressions
[TopSupported](Org.OData.Capabilities.V1.xml#L559)|[Tag](Org.OData.Core.V1.md#Tag)|Supports $top
[SkipSupported](Org.OData.Capabilities.V1.xml#L562)|[Tag](Org.OData.Core.V1.md#Tag)|Supports $skip
[Insertable](Org.OData.Capabilities.V1.xml#L565)|Boolean|This collection supports positional inserts
[Updatable](Org.OData.Capabilities.V1.xml#L568)|Boolean|Members of this ordered collection can be updated by ordinal
[Deletable](Org.OData.Capabilities.V1.xml#L571)|Boolean|Members of this ordered collection can be deleted by ordinal
