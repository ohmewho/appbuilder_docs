---
title: How to Count Active Children
category: tutorial
description: Example using formula field to get key metrics
---
When you open an App its always nice to see a few metrics that summarize the current situation.

## Goal
In Education Matters we want to show the metric 'Active Children'. This should be the number of children in the system with the `Status` set to `Active`.

### Prerequisites
- An Object called Children with 3 fields:

  | Field  | Type                                      |
  | ------ | ------------------------------------------|
  | Name   | Text                                      |
  | Age    | Number                                    |
  | Status | Select List (Options: Active, Not Active) |

- A form to add a Child record

## Step One: Create an Entity Object
First we need to add a new object to represent the entire system.

We can call it `Entity` and add a `Name` text field.

We also need to create a connected record field called `Children` with a connection to the Children object. The rule should be 1 Entity connects Multiple Children.

Now that Entity has Children connected we can use the Formula Field Type to count them.

We'll add the field `Active Children` with the field type Formula. Change the `Type` to `Count` and select the `Field` as `Children -> Age`.

{% include notification.html dismissable="true" status="is-info" message="In the formula field we need to use a number field from the connected record. In this case we use the child's age which may seem a bit strange. Because we are using the Count type, the age values are ignored. For example: 2 children that are 10 and 12 it will Count as 2. Any other field we use would work the same for Count. When using other operations (Sum, Average, Min, Max) it's important to consider the values." %}

Lastly we need to add a filter to the formula field. We'll use `Status` `equals` `Active` so that only children with the Active status show in our count.

## Step Two: Set up your Entity
Now that the object is ready let's add an Entity Record with the Name `Education Matters`.

Next we need to make sure that all Children get added to the Education Matters Entity. To do this we can add a [Record Rule](../../concepts/recordRules/RecordRules.md) to the Add Child Form. This will assign new children to the Education Matters Entity.

To create the record rule we need a Data Collection for our Entity. Because we only have 1 entity we can set [Select] to [First Record].

Now we can go into our form and add the record rule. Let's choose `update record` as the `Action` and then Set `Entity` to our Entity Data Collection with the current selection.

{% include notification.html dismissable="true" status="is-info" message="If you have multiple forms to add Children you will need to add record rules to each." %}

## Conclusion
We now have everything set up for the Active Children Count. It will increase as more children are added or when the Child's status is changed.
