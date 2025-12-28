# Azure Data Factory – Enterprise Migration & Orchestration Pipelines
# 📌 Overview

This repository contains production-grade Azure Data Factory (ADF) pipelines designed to demonstrate enterprise data migration and orchestration patterns.
The solution focuses on on-premises to Azure migration, reusable pipeline design, incremental loading, error handling, and secure hybrid connectivity.

The implementation mirrors real-world ADF projects used in large-scale cloud modernization and data platform initiatives.
# 🏗️ High-Level Architecture

Source Systems

On-Prem SQL Server

On-Prem File Share

Orchestration

Azure Data Factory (Git-enabled)

Self-Hosted Integration Runtime (Hybrid Connectivity)

Target Systems

Azure Data Lake Storage Gen2 (ADLS)

Azure SQL Database

Flow

On-Prem SQL / File Share
        ↓
Self-Hosted Integration Runtime
        ↓
Azure Data Factory
        ↓
ADLS Gen2 / Azure SQL

🧩 Repository Structure
/factory
  └── ADF factory definition

/integrationRuntime
  └── Self-Hosted Integration Runtime configuration

/linkedService
  └── Linked services for SQL Server, File Share, ADLS, Azure SQL

/dataset
  └── Source and target datasets (parameterized)

/pipeline
  └── Enterprise ADF pipelines (migration, incremental, logging)

/README.md


This structure follows ADF Git-mode best practices, where each artifact is version-controlled and independently managed.

🚀 Key Features & Capabilities

On-Prem to Azure Migration

SQL Server and File Share sources

Self-Hosted Integration Runtime for secure hybrid connectivity

Parameterized & Reusable Pipelines

Dynamic datasets and pipelines

Single pipeline supports multiple tables and sources

Full & Incremental Load Patterns

Watermark-based incremental loading

Control-table driven execution

Enterprise Error Handling & Logging

On-Failure paths

Retry logic

Centralized pipeline execution logging

Secure Design

No hardcoded credentials

Designed for Azure Key Vault & Managed Identity integration

Trigger-Based Orchestration

Schedule and dependency-based execution

🔄 Pipelines Included

PL_OnPremSQL_FullLoad

Full data migration from on-prem SQL Server to Azure SQL / ADLS

PL_OnPremSQL_IncrementalLoad

Incremental data load using watermark column strategy

PL_MetadataDriven_Load

Metadata-driven framework to dynamically process multiple tables

PL_Error_Logging

Centralized pipeline execution and failure logging

🔐 Security & Connectivity

Self-Hosted Integration Runtime for on-prem access

Designed for:

Azure Key Vault secrets

Managed Identity authentication

Secure network boundaries respected (no direct inbound access)

📊 Monitoring & Error Handling

Pipeline run status captured for:

Success / Failure

Start & end time

Error message

Retry policies configured for transient failures

Designed to integrate with alerting mechanisms (email / webhook)

🚢 CI/CD & Deployment Approach

ADF Git integration enabled

Artifact-based deployment using ARM templates (conceptual)

Environment-specific values handled via parameterization

Supports Dev → Test → Prod promotion model

🧠 Real-World Relevance

This repository is not a tutorial project.
It reflects real enterprise migration scenarios, including:

Hybrid connectivity challenges

Incremental data movement

Reusability and maintainability concerns

Production-ready error handling patterns

The design decisions align with ADF implementations used in large BFSI and enterprise cloud migration programs.

📌 How This Repo Can Be Extended

Databricks notebook orchestration via ADF

Metadata-driven CDC frameworks

Integration with monitoring tools (Log Analytics)

CI/CD automation using Azure DevOps or GitHub Actions
