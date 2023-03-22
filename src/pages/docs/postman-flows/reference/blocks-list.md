---
title: "Postman Flows blocks"
updated: 2022-12-15
---

The [blocks](../blocks/) available in Postman Flows are described below.

* [Information blocks](#information-blocks)
* [Trigger block](#trigger-block)
* [Decision blocks](#decision-blocks)
* [Looping blocks](#looping-blocks)
* [Action blocks](#action-blocks)
* [Output block](#output-block)

## Information blocks

### Template

<img alt="Template block" src="https://assets.postman.com/postman-labs-docs/all-blocks/template-block.png" width="245px"/>

Enables the free-hand structuring of data and inclusion of variables in the format `{{variable}}`

**Variables** - Named data or assigned values that can be assigned in the text using the `{{variable}}` format.

**Out** - Outputs the data entered in the text box.

### Get Variable

<img alt="Get Variable block" src="https://assets.postman.com/postman-labs-docs/all-blocks/get-variable-block.png" width="153px"/>

Gets the specified variable's value from anywhere in the flow.

### Create Variable

<img alt="Create Variable block" src="https://assets.postman.com/postman-labs-docs/all-blocks/create-variable-block.png" width="136px"/>

Assigns a value to a variable that can then be accessed with the **Get Variable** block anywhere in the flow. The input is any value.

### Record

<img alt="Record block" src="https://assets.postman.com/postman-labs-docs/all-blocks/record-block.png" width="245px"/>

Structured data that can hold any of the other value block types or a record itself. Data is organized by having a key and a value.

### List

<img alt="List block" src="https://assets.postman.com/postman-docs/v10/list-block-v10.jpg" width="159px"/>

Emits the specified list of values. Each item can be any type of block, for example, a date block, a string, or a record.

### Date & Time

<img alt="Date &amp; Time block" src="https://assets.postman.com/postman-labs-docs/all-blocks/date-and-time-block.png" width="221px"/>

Emits the specified date and time.

### Date

<img alt="Date block" src="https://assets.postman.com/postman-labs-docs/all-blocks/date-block.png" width="164px"/>

Emits the specified date.

<!-- vale Postman.Avoid = NO -->
### Now

<img alt="Now block" src="https://assets.postman.com/postman-labs-docs/all-blocks/now-block.png" width="69px"/>

Emits the current date and time.
<!-- vale Postman.Avoid = YES -->

### Select

<img alt="Select block" src="https://assets.postman.com/postman-labs-docs/all-blocks/select-block.png" width="142px"/>

Parses a data stream to select a subset of the data available. If the input data is from a send request with a saved example, auto-fills the path as items are selected in the menu. Otherwise can be navigated using the forward slash to select sub-items. For example `/body/results` for a field named results in the body of a request.

### Regex

<img alt="Regex block" src="https://assets.postman.com/postman-labs-docs/all-blocks/regex-block.png" width="121px"/>

Emits a regular expression.

### Null

<img alt="Null block" src="https://assets.postman.com/postman-labs-docs/all-blocks/null-block.png" width="35px"/>

Emits a null value.

### Number

<img alt="Number block" src="https://assets.postman.com/postman-labs-docs/all-blocks/number-block.png" width="93px"/>

A whole or decimal number.

<!-- vale Postman.Spelling = NO -->
### Bool

<img alt="Bool block" src="https://assets.postman.com/postman-labs-docs/all-blocks/bool-block.png" width="118px"/>

True or false.

<!-- vale Postman.Spelling = YES -->
### String

<img alt="String block" src="https://assets.postman.com/postman-labs-docs/all-blocks/string-block.png" width="143px"/>

Emits the string that you enter.

## Trigger block

### Start

<img alt="Start block" src="https://assets.postman.com/postman-labs-docs/all-blocks/combined-start-block.png" width="110px"/>

Used as the entry point for [running flows on the cloud](/docs/postman-flows/running-flows-on-the-cloud/webhooks/). Can be configured to hold test data for testing locally by selecting the gear icon and will act as a webhook endpoint that accepts data when running on the cloud.

## Decision blocks

### If

<img alt="If block" src="https://assets.postman.com/postman-labs-docs/all-blocks/refactored-if-block.png" width="245px"/>

<!-- vale Postman.Spelling = NO -->
  Takes any number of variables and data, and takes a different branch depending on the result of the FQL condition.

  **Variables** - Named data or assigned values.

  **Text entry block** - Freeform query using FQL that evalutes to true or false.

  **Data** - Receives data or an event from another block.

  **Outputs** - Sends the data to either the True or False pathway depending on the value of the FQL condition.
<!-- vale Postman.Spelling = YES -->

### Evaluate

<img alt="Evaluate block" src="https://assets.postman.com/postman-labs-docs/all-blocks/updated-evaluate-block.png" width="318px"/>

Executes [FQL](/docs/postman-flows/flows-query-language/introduction-to-fql/) syntax to query structured data.

**Variables** - Named data or assigned values that can be accessed using FQL.

**Text entry block** - Freeform query using FQL.

**Out** - Outputs the result of the query.

## Looping blocks

### Repeat

<img alt="Repeat block" src="https://assets.postman.com/postman-labs-docs/all-blocks/repeat-block.png" width="129px"/>

Performs a loop a specified number of times.

**Count** - The number of times to run the block.

**Start** - Triggers the block.

**Index** - The index of the current run starting at 0 for the first run.

### For

<img alt="For block" src="https://assets.postman.com/postman-labs-docs/all-blocks/for-block.png" width="111px"/>

Loops over each item in a list.

**List** - A list of values like `[1,2,3]` or `["one","two","three"]`.

**Start** - Receives an event to trigger the block to start.

**Item** - Outputs a single item from the loop.

### Collect

<img alt="Collect block" src="https://assets.postman.com/postman-labs-docs/all-blocks/collect-block.png" width="118px"/>

Collects the results of a for loop, and outputs a list and an event when it has finished.

**Item** - Takes in a single item from a for loop.

**List** - Creates a list of all items sent to this block in the for loop.

**Finish** - Sends an event when the block is complete (when the for loop has ended and every item is in a new list).

## Action blocks

### Delay

<img alt="Delay block" src="https://assets.postman.com/postman-labs-docs/all-blocks/delay-block.png" width="212px"/>

Waits the specified amount of time before allowing data through.

**Data (input)** - Triggers the block to start the delay.

**Data (output)** - Once the delay is complete, passes through whatever data was input.

**Delay (in ms)** - The amount of time in milliseconds to wait.

### Send Request

<img alt="Send Request block" src="https://assets.postman.com/postman-labs-docs/all-blocks/send-request-block.png" width="237px"/>

Invokes a request in a collection.

**Send** - When any connection fires an event to this port, the block invokes the specified request.

**Environment** - Lets you select which Postman environment to use with your request.

**Body Type** - The schema that your data uses (for example JSON or XML). **Auto** will try to auto-detect which schema is being used.

**Variables** - Auto-populates with any `{{variable}}` that's in the specified request. Variables can either be assigned a value in the block itself, or have a value passed in.
<!-- vale Postman.ComplexWords = NO -->
**Success** - Contains the response of a successful API call if tests are assigned to the request and all pass or, if there are no tests, a 2xx HTTP status code is received. The API call can then be connected to another block or variable value to extract a field from the response.

**Failure** - Contains the response of a failed API call if tests are assigned to the request and any fail or, if there are no tests, a non 2xx HTTP status code is received. The API call can then be connected to another block or variable value to extract a field from the response.
<!-- vale Postman.ComplexWords = YES -->

## Output block

### Log (console)

<img alt="Log (console) block" src="https://assets.postman.com/postman-labs-docs/all-blocks/log-block.png" width="78px"/>

Prints the input to the console.

### Output

<img alt="Output block" src="https://assets.postman.com/postman-labs-docs/all-blocks/output-block.png" width="249px"/>

Displays the data passed through the port. The dropdown menu enables you to select from JSON, charts, tables, videos, images, and more. You can use **Output** blocks to:

* Debug flows by viewing data directly on the canvas instead of opening the Postman console to view logs.
* Create and display markdown, images, videos, and even YouTube embeds.
* Create interactive dashboards using bar charts, line charts, tables, and more.

For more information, see the [Building your first flow](/docs/postman-flows/tutorials/building-your-first-flow/) tutorial.
