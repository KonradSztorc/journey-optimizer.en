---
title: Get started with offer catalog export
description: This section lists all the fields used in the exported dataset for decisions.
---
# Decisions dataset {#decisions-dataset}

Each time an offer is modified, the autogenerated dataset for decisions is updated.

![](../assets/dataset-activities.png)

The most recent successful batch in the dataset is displayed on the right. The hierarchical view of the schema for the dataset displays on the left pane.

>[!NOTE]
>
>Learn how to access the exported datasets for each object of your Offer Library in [this section](../export-catalog/access-dataset.md).

A decision (formerly known as offer decision) is used to control the decisioning process. It specifies the filter applied to the total inventory to narrow down offers by topic/category, the placement to narrow down the inventory to those offers that technically fit into the reserved space for the offer and specifies a fallback option should the combined constraints disqualify all available personalization offers.

Here is the list of all the fields that can be used in the **[!UICONTROL Decision Object Repository - Decisions]** dataset (formerly known as Decision Object Repository - Activities).
    
## Identifier
    
A unique identifier for the record.

Type: string

## _experience

### decisioning

#### criteria

Defines a set of decision criteria where each contains a set of constraints.

Type: array

* **Description**

    Criterion description. It is used to convey human readable intentions on how or why this criterion was constructed and how it is affecting the decision.

    Type: string

* **Option Selection**

    The option selection defines the validity/applicability of options in this context.

    Type: object

    * **Description**

        Option selection description. It is used to convey human readable intentions on how or why this option selection was constructed and/or what option will match.

        Type: string

    * **Option Filter**

        The reference to a tag based filter that matches options from an inventory using their attached tags. The value is the URI (@id) of the decision rule that is referenced. See schema https://ns.adobe.com/experience/decisioning/filter.

        Type: string

    * **Profile Constraint Type**

        Determines if any constraints are currently set and how the contraints are expressed. It could be though a filter query or through one or more segment memberships.

        Type: string

    * **Option List**

        A list that directly specifies the options without evaluating a filter query. Either an option list or an option filter rule can be specified.

        Type: array

        <!--Missing title under Option List? Desc = An identifier of an decision option entity. The value value refers to an `@id` property of a decision option.-->

* **placements**

    The placement constraint states that this criterion is only applicable for the listed placements. Only when the targeted placement is in the `xdm:placements` list is the option selection considered. Otherwise the entire decision criteria is skipped. When the 'xdm:placements' list is omitted or empty, the criterion is considered for any targeted placement. The placements listed here impose implicit criteria for the option selection. An option to be considered must have a representation for the targeted placement.

    Type: array

    * **Placement Identifier**

    A reference to a placement entity. The value is the URI (@id) of the placement that is referenced. See schema https://ns.adobe.com/experience/decisioning/placement.

    Type: string

* **Profile Constraint**

    The profile constraint decides if an option selection is eligible for this profile identity at this moment, in this context. If the profile constraint does not need to consider values of each of the option, i.e. it is invariant of the options from the option selection, the profile constraint that evaluates to 'false' cancels out the entire option selection. On the other hand, a profile constraint rule that takes an option as a parameter is evaluated for each qualifiying option of the option selection.

    Type: object

    * **Description**

        Profile constraint description. It is used to convey human readable intentions on how or why this profile constraint was constructed and/or what option will be included or excluded by it.

        Type: string

    * **Eligibility Rule**

        A reference to a decision rule that evaluates to true or false for a given profile and/or other given contextual XDM objects. The rule is used to decide if the option qualifies for a given profile. The value is the URI (@id) of the decision rule that is referenced. See schema https://ns.adobe.com/experience/decisioning/rule.

        Type: string

    * **Profile Constraint Type**

        Determines if any constraints are currently set and how the contraints are expressed. It could be though a rule or through one or more segment memberships.

        Type: string

        Possible values: "none", "eligibilityRule", "anySegments", "allSegments", "rules"

        Default value: "none"

    * **Segment Identifiers**

        Identifiers of the segments

        String: array

        * **Identifier**

            Identity of the segment in the related namespace.

            Type: string

        * **Namespace**

            The namespace associated with the `xid` attribute.

            Type: object

            * **Code**
                
                The code is a human readable identifier for the namespace and can be used to request the technical namespace id which is used for identity graph processing.

                Type: string

        * **Experience identifier**

            When present, this value represents a cross-namespace identifier that is unique across all namespace-scoped identifiers in all namespaces.

            Type: string

* **Ranking Details**

    Rank (priority). Defines how the \"best option\" is determined given the context of the decision criterion. Among all the selected options that meet the profile constraints, the ranking will decide the top (or top N) option(s) to be proposed.

    Type: object

    * **Order Evaluation**

        Evaluation of a relative order of one or more decision options. Options with higher ordinal values are selected over any options with lower ordinal values. The values determined by this method can be ordered but distances between them cannot be measured and neither can sums nor products be calculated. The median and the mode are the only measures of central tendency that can be used for ordinal data.

        Type: object

        * **Scoring function**

            A reference to a function that computes a numerical score for this decision option. Decision options will then be ordered (ranked) by that score. The value of this property is the URI (@id) of the function to be invoked with on option at a time. See schema https://ns.adobe.com/experience/decisioning/function.

            Type: string

        * **Order Evaluation Type**

            Specifies which order evaluation mechanism is used, static priority of the decision options, a scoring function that calculates a  numeric value for every option or a ranking strategy that receives a list to order it.

            Type: string

        * **Ranking Strategy**

            A reference to a strategy that ranks a list of decision option. Decision options will be returned in an ordered list. The value of this property is the URI (@id) of the function to be invoked with on option at a time. See schema https://ns.adobe.com/experience/decisioning/rankingStrategy.

            Type: string

    * **Priority**

        The priority of a single decision option relative to all other options. Options for which no order function is given are prioritized using this propery. Options with higher priority values are selected before any lower priority options. If two or more qualifying options share the highest priority value, one is chosen at uniform random and used for the decision proposition.
        
        Type: integer

        Minimum value: 0

        Default value: 0

#### Activity End Date and Time

Decision end date and end time. Property has the semantic of schema.org's 'endTime' property defined on http://schema.org/Action.

Type: string

#### Fallback Option

The reference to a fallback option that is used when decisioning in the context of this decision does not qualify any of the regular options (this typically happens when hard constraints are applied). The value is the URI (@id) of the fallback option that is referenced.

Type: string

#### Activity Name

Decision name that is displayed in various user interfaces.

Type: string

#### Activity Start Date and Time

Decision start date and end time. Property has the semantic of schema.org's 'startTime' property defined on http://schema.org/Action.

Type: string

## _repo
    
### Activity ETag

The revision that the decision object was at when the snapshot was taken.

Type: string