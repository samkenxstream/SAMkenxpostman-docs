---
title: "About blocks and passing information"
updated: 2023-03-20
contextual_links:
  - type: section
    name: "Prerequisites"
  - type: link
    name: "Download and Install"
    url: "https://www.postman.com/downloads/"
  - type: section
    name: "Additional resources"
  - type: subtitle
    name: "Blog posts"
  - type: link
    name: "Announcing Postman Flows Early Access"
    url: "https://blog.postman.com/announcing-postman-flows-early-access/"
  - type: subtitle
    name: "Case Studies"
  - type: link
    name: "Built Technologies non-technical team members use Postman Flows"
    url: "https://www.postman.com/case-studies/built/"
---

_Blocks_ are used to create Flows, and data is exchanged between them with _messages_.

## Contents

* [Blocks](#blocks)
* [Passing information](#passing-information)

## Blocks

Blocks are the basic units used to create a flow. Every block has a specific purpose, such as performing actions, creating information, or making a decision.

### Block fundamentals

Every block has either an input, an output, or both. You can pass a information from one block to another. For more information on each block, see [Types of Blocks](#types-of-blocks).

### Block anatomy

> below is the sample anatomy of the [Send Request Block](/docs/postman-flows/reference/blocks-list/#send-request)

![Block anatomy](https://assets.postman.com/postman-labs-docs/block/updated-block-anatomy.png)

1. **Name** - Name of the block.

2. **Request to run** - Which request from your collection is going to be run.

3. **Send event input** - Starts running the block when this input receives information.

4. **Environment** - Which Postman environment to use.

5. **Body Type** - Structure of the information the request uses.

6. **Variables** - The variables that are either provided in the flow or from the environment.

7. **Success** - When the API being run is successful this output is triggered.

8. **Failure** - When the API being run is unsuccessful this output is triggered.

### Types of blocks

There are three types of blocks:

* **Action blocks** perform an action like getting information from an API.
* **Information blocks** create values of a specific type; like text or numbers.
* **Decision blocks** changes data in some way and then determines how to proceed in the Flow.

## Passing information

In Flows, information passes from one block to the next. This information could be a text, a number, or it could be larger complex information like a list of users, or an entire movie.
