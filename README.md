# Advanced Cloud Architecture for Photo Album Application

## Overview

This project presents an advanced cloud architecture design for a photo album web application. The proposed design integrates multiple AWS services to ensure continuous website functionality, superior performance, scalability, reliability, security, and cost-effectiveness.

## Team Members

- Dac Tung Duong Nguyen - 104357292
- Ansh Sehgal - 104172848

## Abstract

In previous phases, the cloud infrastructure supporting the photo album web application was successfully implemented and is presently in use. Nonetheless, the foreseeing increase in demand for this web application in the future poses a challenge for the current system, which lacks the capacity to handle this surge in user activity. To address this issue, this project proposes an advanced cloud architecture design for the photo album application.

## Table of Contents

1. [Introduction](#introduction)
2. [Business Scenario](#business-scenario)
3. [Architectural Diagram](#architectural-diagram)
4. [UML Diagram](#uml-diagram)
5. [Description of Used AWS Services](#description-of-used-aws-services)
6. [Requirements and Justification](#requirements-and-justification)
7. [Alternative Solution](#alternative-solution)
8. [Design Criteria](#design-criteria)
9. [Justification for Selection of Best Solution](#justification-for-selection-of-best-solution)

## Introduction

The photo album web application provides users with a platform to upload and store their photos. With the rising demand, the existing system is unable to handle the increased workload effectively. To guarantee consistent availability and performance, a new cloud architecture design is suggested. This fresh approach focuses on enhanced scalability and higher availability compared to the current system, optimized for cost-effectiveness.

## Business Scenario

1. Employing managed cloud services to reduce the necessity for internal system administration.
2. Addressing the anticipated growth, expected to double every 6 months for the next 2 to 3 years, continuously.
3. Utilizing a cost-effective and efficient database system for swift operations.
4. Embracing a serverless/event-driven approach for streamlined processes.
5. Enhancing global response times significantly.
6. Preparing the system for future scalability by accommodating video media handling.
7. Automatically generating different versions of the uploaded media files.
8. Ensuring that the architecture for processing media is adaptable and expandable.
9. Designing the architecture to prevent overloading and ensuring effective decoupling of components.

## Architectural Diagram

(Include a visual diagram here)

## UML Diagram

(Include UML diagrams here)

## Description of Used AWS Services

- **CloudFront**: Fast and efficient content delivery network (CDN) service.
- **Lambda**: Serverless computing service that executes code without managing servers.
- **Route53**: Scalable Domain Name System (DNS) service.
- **Elastic Beanstalk**: Managed service for deploying applications.
- **DynamoDB**: Managed NoSQL database service.
- **S3**: Scalable cloud storage service.
- **SNS**: Managed messaging service for sending notifications.
- **SQS**: Managed message queuing service for asynchronous communication.
- **Elastic Transcoder**: Service that converts multimedia files into different formats.
- **Rekognition**: Service that uses deep learning to analyze images and videos.
- **IAM**: Service that controls access to resources by managing user identities and permissions.
- **Cognito**: Service that simplifies user authentication and management.
- **CloudWatch**: Monitoring service for tracking metrics, logs, and setting alarms.

## Requirements and Justification

### Managed Cloud Services & AWS S3 for Media Storage

- **Requirement**: Minimize in-house systems administration.
- **Justification**: AWS Elastic Beanstalk abstracts infrastructure complexities, allowing developers to focus on code.

### Scalability for Growing Demand

- **Requirement**: Handle growth expected to double every six months.
- **Justification**: AWS Elastic Beanstalk and CloudFront ensure scalability and rapid content delivery.

### Compute Capacity & EC2 Instances

- **Requirement**: Address performance issues exceeding the 80% limit.
- **Justification**: AWS Lambda ensures efficient processing without manual server management.

### Serverless/Event-Driven Solution

- **Requirement**: Prefer a serverless/event-driven solution.
- **Justification**: AWS Lambda, combined with SNS and SQS, provides the event-driven architecture.

### Database Solution

- **Requirement**: Seek a cost-effective option for simple table structure.
- **Justification**: AWS DynamoDB offers fast performance and scalability.

### Global Response Times

- **Requirement**: Improve global response times.
- **Justification**: AWS CloudFront caches content at multiple edge locations.

### Handling Video Media

- **Requirement**: Handle video media in the future.
- **Justification**: AWS Elastic Transcoder handles video transcoding.

### Media Processing

- **Requirement**: Automatic production of various media versions.
- **Justification**: AWS Lambda and Elastic Transcoder ensure efficient media processing.

## Alternative Solution

### Serverless Computing

- **Used**: AWS Lambda
- **Alternative**: Virtual machines (e.g., EC2) or Containers (e.g., ECS)

### NoSQL Database

- **Used**: DynamoDB
- **Alternative**: SQL database (e.g., RDS)

### Caching Options

- **Used**: CloudFront
- **Alternative**: In-memory cache (e.g., Elasticache)

### Push vs. Pull Message Handling

- **Used**: Push (SNS) and Pull (SQS)
- **Alternative**: Direct communication without decoupling

### Multi-Tier Architecture

- **Used**: Multi-Tier architecture
- **Alternative**: 2-Tier architecture

### Media Transformation

- **Used**: Elastic Transcoder and Rekognition
- **Alternative**: Custom-built solutions on EC2

## Design Criteria

### Performance and Scalability

- **Serverless Architecture (Lambda)**: Scales automatically based on demand.
- **Decoupling using Messaging Services (SNS & SQS)**: Ensures high loads on one component don't impact others.
- **Global Content Delivery (CloudFront & Edge Locations)**: Enhances performance by reducing latency.

### Reliability

- **Distributed Storage (S3)**: Provides high durability and integrity.
- **Managed Services (Elastic Beanstalk, DynamoDB)**: Ensures high availability and fault tolerance.
- **DNS Management (Route53)**: Provides reliable and cost-effective domain name registration.

### Security

- **Authentication and Authorization (IAM & Cognito)**: Ensures secure access control.
- **Encrypted Storage (S3)**: Ensures data confidentiality and security.

### Cost

- **Fixed Expenses**: Route53, IAM, Cognito
- **Variable Expenses**: Lambda, S3, CloudFront, DynamoDB, Elastic Transcoder, SNS, SQS, Rekognition, Elastic Beanstalk, Edge Locations, CloudWatch

## Justification for Selection of Best Solution

The proposed solution leverages AWS services to create a robust, scalable, secure, and cost-effective architecture that aligns with the company's growth projections and global user base while ensuring a seamless user experience.