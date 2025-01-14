---
product: journey optimizer
title: sort
description: Learn about the function sort
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: sort, function, expression, journey
exl-id: 607e1424-4165-48ae-b896-cce2d18f7dcc
---
# sort {#sort}

Sorts a list of values or objects in the natural order.

>[!NOTE]
>
>If the target list is a listObject, this function can only be used in custom action expressions.

## Category

List

## Function syntax

`sort(<parameters>)`

## Parameters

| Parameter | Type             | Description             |
|-----------|------------------|------------------|
| listToSort | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly, or listObject | List to sort out. For listObject, it must be a field reference. |
| keyAttributeName | string | This parameter is only for listObject. The attribute name in the objects of the given list is used as key for sorting. |
| sortingOrder | boolean | Ascending (true) or descending (false) |

## Signature and returned type

`sort(<listInteger>,<boolean>)`

Returns a list of integers.

`sort(<listDecimal>,<boolean>)`

Returns a list of decimals.

`sort(<listString>,<boolean>)`

Returns a list of strings.

`sort(<listDateTimeOnly>,<boolean>)`

Returns a list of datetimes without considering time zone.

`sort(<listDateTime>,<boolean>)`

Returns a list of datetimes.

`sort(<listDateOnly>,<boolean>)`

Returns a list of dates.

`sort(<listBoolean>,<boolean>)`

Returns a list of booleans.

`sort(<listObject>,<string>,<boolean>)`

Returns a list of objects.

## Example

`sort(["A", "C", "B"], true)`

Returns `["A","B","C"]`.

`sort([1, 3, 2], false)`

Returns `[3, 2, 1]`.

