---
title: AWS info
nav_order: 6
parent: Handbook   # optional grouping
---
# AWS info
## Introduction

Think before you do.

## Good practice

- If you don't use your instance, put it down (stop/terminate it)
- First start small, then go big (if you need it)
- Use a European region like Ireland (`eu-west-1`), these are cheaper

## S3

This is the place to save your results and raw data after you finished your analysis.

The important part here is to use the rules in AWS. In your bucket you need to go to **Management**. Here you can add **Lifecycle configuration**, for example:

- **Raw data**
  - Day 0: Objects uploaded
  - Day 1: Objects move to Glacier Deep Archive
- **Results**
  - Day 0: Objects uploaded
  - Day 90: Objects move to Standard-IA
  - Day 180: Objects move to Glacier Deep Archive

This is important because the cost to save data in **Glacier Deep Archive** is much lower than in **Standard**. **Standard-IA** is higher than Deep Glacier but lower than Standard.

It is thus important to think about what you're going to do with your data:
- If after analyzing you don't need the raw data anymore, put them directly in Deep Glacier.
- If you still want to take a look at some of your results or you want to reuse a file, keep them for the time needed in Standard or Standard-IA.

It is also possible to retrieve something from Deep Glacier, but this comes with a cost. So to do this you need to do the following:

## Instances

### Setting up

You need an AWS account. This can be requested from Arvid/Marie/Jeanette.

If you have this, you need to go in the upper bar to **EC2**. Here you check on top the **region**; it needs to be **Europe**.

Everything you do or want to couple needs to be in the same region, so it is important to know in which region you are working.

- **STEP 1** Go to **Instances**
- **STEP 2** Click on the big orange button on top: **Launch instance**
- **STEP 3** Fill in what you need. Remember good practice: start small, go big after if needed.  
  It is better to set things up in a small instance than starting big and not using all the resources.

## EBS

## EFS