---
product: journey optimizer
title: getListItem
description: Learn about the function gstListItem
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: getListItem, function, expression, journey
exl-id: e995f479-bbaa-45f3-9531-e05680c5a723
---
# getListItem {#gestListItem}

Returns the item of the list at the given index.

## Category

List

## Function syntax

`getListItem(<parameters>)`

## Parameters

| Parameter | Type             |
|-----------|------------------|
| list      | listString       |
| list      | listBoolean      |
| list      | listInteger      |
| list      | listDecimal      |
| list      | listDuration     |
| list      | listDateTime     |
| list      | listDateTimeOnly |
| list      | listDateOnly     |
| index   | integer          |

## Signatures and returned type

`getListItem(<listInteger>,<index>)`

Returns an integer.

`getListItem(<listDecimal>,<index>)`

Returns a decimal.

`getListItem(<listString>,<index>)`

Returns a string.

`getListItem(<listDateTimeOnly>,<index>)`

Returns a datetime without considering time zone.

`getListItem(<listDateTime>,<index>)`

Returns a datetime.

`getListItem(<listDateOnly>,<index>)`

Returns a list of dates.

`getListItem(<listBoolean>,<index>)`

Returns a boolean.

`getListItem(<listDuration>,<index>)`

Returns a duration.

## Example

`getListItem([10, 2, 3], 1)`

Returns "2"

`getListItem(["A", "B", "C"], 2)`
Returns "C"

Examples with an event field 'event.appVersion' with value: "20.45.2.3434"

`split(@{event.appVersion}, "\\.")`

Returns `["20", "45", "2", "3434"]`

`getListItem(split(@{event.appVersion}, "\\."), 0)`

Returns "20"
