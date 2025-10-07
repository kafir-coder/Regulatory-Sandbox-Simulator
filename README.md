# Regulatory Sandbox Simulator

## Overview
The **Regulatory Sandbox Simulator** is a lightweight, modular prototype of a financial compliance environment. It models the core components of a payment institution — including customer onboarding (KYC), transaction processing, and real-time anti–money laundering (AML) assessment — within a controlled, observable architecture.

## Key Features
- **Dynamic AML Rule Engine** — evaluates each transaction against configurable rules stored in a database or YAML file (e.g., high-value transfers, rapid transaction bursts, risky geographies).  
- **KYC Module** — simulates customer registration and assigns risk scores.  
- **Transaction Engine** — processes peer-to-peer transactions with built-in compliance hooks.  
- **Alerting System** — automatically flags and blocks suspicious transactions pending manual review.  
- **Observability Stack** — Prometheus metrics and Grafana dashboards expose operational and compliance insights in real time.  

## Use Case
This sandbox is intended for engineers, compliance analysts, and fintech developers who want to experiment with:
- Transaction monitoring workflows  
- Policy-driven AML logic  
- Integrations between financial core systems and observability layers  

## Tech Stack
- **Go** — API, rule engine, and metrics  
- **PostgreSQL** — data persistence and rule storage  
- **Prometheus + Grafana** — monitoring and visualization  

## Project Goals
- Demonstrate compliance-aware financial transaction handling.  
- Provide a framework for extending AML/KYC logic with real data sources or external APIs.  
- Serve as a reference for architects designing fintech or banking systems with regulatory requirements.

## Example Architecture
         +-------------------+
         |  API Gateway       |
         +-------------------+
                  |
                  v
      +-----------------------+
      | Customer Service (KYC)|
      +-----------------------+
                  |
                  v
      +-----------------------+
      | Transaction Engine    |
      | (simulates payments)  |
      +-----------------------+
                  |
                  v
      +-----------------------+
      | Compliance Engine     |
      | (AML + rules engine)  |
      +-----------------------+
                  |
                  v
      +-----------------------+
      | Metrics Exporter      |
      +-----------------------+
                  |
                  v
           [ Prometheus ]
                  |
                  v
            [ Grafana UI ]
