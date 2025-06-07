# **Flow of Funds Diagram and Documentation**

**Institution Name:** InversePay  
**Date:** June 7, 2025  
**Prepared by:** Treasury Department  
**Approved by:** [Chief Financial Officer, Head of Compliance]

---

## **1. Introduction**

This document outlines the flow of funds within the InversePay electronic payment system, detailing how money moves between various stakeholders including customers, agents, banks, and other financial institutions. The flow of funds documentation ensures transparency, regulatory compliance, and operational clarity for all transaction types supported by the platform.

---

## **2. Key Stakeholders in Fund Flows**

| Stakeholder | Role in Fund Flow | Account Types |
|-------------|-------------------|--------------|
| End Users | Originators and recipients of transactions | Mobile wallets, linked bank accounts |
| Agents | Cash-in/cash-out points, transaction facilitators | Agent float accounts, commission accounts |
| InversePay | Platform operator, transaction processor | Settlement accounts, operational accounts, escrow accounts |
| Partner Banks | Banking services provider, settlement facilitator | Nostro accounts, settlement accounts, operational accounts |
| Mobile Money Providers | Digital wallet services, transaction channels | Float accounts, settlement accounts |
| Merchants | Goods/services providers, payment recipients | Merchant accounts, settlement accounts |
| Regulatory Authorities | Oversight and compliance monitoring | Reporting interfaces |

---

## **3. Fund Flow Diagrams**

### **3.1 Overall System Fund Flow**

```
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│                 │     │                 │     │                 │
│  Funding        │     │  InversePay     │     │  Disbursement   │
│  Sources        │◄────┤  Settlement     ├────►│  Destinations   │
│                 │     │  System         │     │                 │
└────────┬────────┘     └────────┬────────┘     └────────┬────────┘
         │                       │                       │
         ▼                       ▼                       ▼
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│ • Bank Deposits │     │ • Trust Account │     │ • Bank Accounts │
│ • Cash at Agents│     │ • Float Accounts│     │ • Mobile Money  │
│ • Mobile Money  │     │ • Nostro/Vostro│     │ • Cash at Agents│
│ • Card Payments │     │ • Escrow        │     │ • Int'l Remit   │
└─────────────────┘     └─────────────────┘     └─────────────────┘
```

### **3.2 Wallet Funding Flow**

```
┌──────────────┐     ┌───────────────┐     ┌───────────────┐     ┌───────────────┐
│              │     │               │     │               │     │               │
│  Customer    │────►│ Funding       │────►│ InversePay    │────►│ Customer      │
│  Funding     │     │ Channel       │     │ Settlement    │     │ Wallet        │
│  Source      │     │               │     │ System        │     │               │
└──────────────┘     └───────┬───────┘     └───────────────┘     └───────────────┘
                            │
                            ▼
                     ┌─────────────────┐
                     │ • Bank Transfer │
                     │ • Agent Deposit │
                     │ • Mobile Money  │
                     │ • Card Payment  │
                     └─────────────────┘
```

### **3.3 Wallet-to-Wallet Transfer Flow**

```
┌──────────────┐     ┌───────────────┐     ┌───────────────┐     ┌───────────────┐
│              │     │               │     │               │     │               │
│  Sender      │────►│ InversePay    │────►│ Internal      │────►│ Recipient     │
│  Wallet      │     │ Transaction   │     │ Ledger        │     │ Wallet        │
│              │     │ Processor     │     │ Transfer      │     │               │
└──────────────┘     └───────────────┘     └───────────────┘     └───────────────┘
       │                                                                │
       │                                                                │
       ▼                                                                ▼
┌──────────────┐                                               ┌───────────────┐
│ Sender       │                                               │ Recipient     │
│ Balance      │                                               │ Balance       │
│ Decreases    │                                               │ Increases     │
└──────────────┘                                               └───────────────┘
```

### **3.4 Cash-Out Flow**

```
┌──────────────┐     ┌───────────────┐     ┌───────────────┐     ┌───────────────┐
│              │     │               │     │               │     │               │
│  Customer    │────►│ InversePay    │────►│ Agent         │────►│ Cash to       │
│  Wallet      │     │ Transaction   │     │ Float         │     │ Customer      │
│              │     │ Processor     │     │ Account       │     │               │
└──────────────┘     └───────────────┘     └───────┬───────┘     └───────────────┘
                                                   │
                                                   ▼
                                           ┌───────────────┐
                                           │ Settlement    │
                                           │ with Agent    │
                                           │ (T+1)         │
                                           └───────────────┘
```

### **3.5 International Remittance Flow**

```
┌──────────────┐     ┌───────────────┐     ┌───────────────┐     ┌───────────────┐
│              │     │               │     │               │     │               │
│  Sender in   │────►│ Remittance    │────►│ InversePay    │────►│ Recipient     │
│  Country A   │     │ Partner       │     │ Settlement    │     │ Wallet        │
│              │     │               │     │ System        │     │               │
└──────────────┘     └───────────────┘     └───────┬───────┘     └───────────────┘
                                                   │
                                                   ▼
                                           ┌───────────────┐
                                           │ Currency      │
                                           │ Exchange &    │
                                           │ Settlement    │
                                           └───────────────┘
```

### **3.6 Currency Exchange Flow**

```
┌──────────────┐     ┌───────────────┐     ┌───────────────┐     ┌───────────────┐
│              │     │               │     │               │     │               │
│  Source      │────►│ Exchange      │────►│ FX            │────►│ Destination   │
│  Currency    │     │ Request       │     │ Conversion    │     │ Currency      │
│  Wallet      │     │ Processor     │     │ Engine        │     │ Wallet        │
└──────────────┘     └───────────────┘     └───────┬───────┘     └───────────────┘
                                                   │
                                                   ▼
                                           ┌───────────────┐
                                           │ Treasury      │
                                           │ Management    │
                                           │ System        │
                                           └───────────────┘
```

### **3.7 Agent Liquidity Management Flow**

```
┌──────────────┐     ┌───────────────┐     ┌───────────────┐     ┌───────────────┐
│              │     │               │     │               │     │               │
│  Agent       │────►│ Liquidity     │────►│ InversePay    │────►│ Agent         │
│  Bank        │     │ Request       │     │ Treasury      │     │ Float         │
│  Account     │     │ System        │     │ System        │     │ Account       │
└──────────────┘     └───────────────┘     └───────┬───────┘     └───────────────┘
                                                   │
                                                   ▼
                                           ┌───────────────┐
                                           │ Float         │
                                           │ Monitoring &  │
                                           │ Reporting     │
                                           └───────────────┘
```

---

## **4. Detailed Fund Flow Processes**

### **4.1 Customer Wallet Funding Process**

| Step | Description | Stakeholders | Timing | Controls |
|------|-------------|--------------|--------|----------|
| 1 | Customer initiates deposit via chosen channel | Customer, Channel Provider | T | Transaction validation, limit checks |
| 2 | Funds received in InversePay collection account | InversePay, Channel Provider | T to T+1 | Reconciliation, fraud screening |
| 3 | Transaction validated and processed | InversePay | T | AML/CFT checks, compliance verification |
| 4 | Customer wallet credited | InversePay, Customer | T | Balance update, notification |
| 5 | Settlement with channel provider | InversePay, Channel Provider | T+1 to T+3 | Reconciliation, settlement confirmation |

### **4.2 Wallet-to-Wallet Transfer Process**

| Step | Description | Stakeholders | Timing | Controls |
|------|-------------|--------------|--------|----------|
| 1 | Sender initiates transfer | Sender | T | Authentication, limit checks |
| 2 | Transfer validated | InversePay | T | Balance check, AML screening |
| 3 | Sender wallet debited | InversePay, Sender | T | Balance update, notification |
| 4 | Recipient wallet credited | InversePay, Recipient | T | Balance update, notification |
| 5 | Transaction recorded in ledger | InversePay | T | Audit trail, reporting |

### **4.3 Cash-Out Process**

| Step | Description | Stakeholders | Timing | Controls |
|------|-------------|--------------|--------|----------|
| 1 | Customer initiates withdrawal at agent | Customer, Agent | T | Authentication, limit checks |
| 2 | Transaction validated | InversePay | T | Balance check, AML screening |
| 3 | Customer wallet debited | InversePay, Customer | T | Balance update, notification |
| 4 | Agent authorized to disburse cash | InversePay, Agent | T | Authorization code, transaction ID |
| 5 | Agent provides cash to customer | Agent, Customer | T | Receipt, confirmation |
| 6 | Agent float account credited | InversePay, Agent | T | Float balance update |
| 7 | Settlement with agent | InversePay, Agent, Bank | T+1 | Reconciliation, bank transfer |

### **4.4 International Remittance Process**

| Step | Description | Stakeholders | Timing | Controls |
|------|-------------|--------------|--------|----------|
| 1 | Sender initiates remittance with partner | Sender, Partner | T | KYC, limit checks |
| 2 | Partner forwards transaction to InversePay | Partner, InversePay | T | API validation, compliance checks |
| 3 | Currency conversion executed | InversePay | T | Exchange rate application, treasury management |
| 4 | Recipient wallet credited | InversePay, Recipient | T | Balance update, notification |
| 5 | Settlement with remittance partner | InversePay, Partner | T+1 to T+3 | Nostro/vostro reconciliation |

### **4.5 Currency Exchange Process**

| Step | Description | Stakeholders | Timing | Controls |
|------|-------------|--------------|--------|----------|
| 1 | Customer requests currency exchange | Customer | T | Rate display, confirmation |
| 2 | Source currency wallet debited | InversePay, Customer | T | Balance check, update |
| 3 | Exchange rate applied with margin | InversePay | T | Rate verification, profit calculation |
| 4 | Destination currency wallet credited | InversePay, Customer | T | Balance update, notification |
| 5 | Treasury position updated | InversePay | T | Position monitoring, risk management |
| 6 | External FX settlement (if needed) | InversePay, Banks | T+2 | Correspondent banking settlement |

---

## **5. Settlement and Reconciliation**

### **5.1 Settlement Cycles**

| Settlement Type | Frequency | Participants | Settlement Method |
|----------------|-----------|--------------|-------------------|
| Agent Settlement | Daily (T+1) | InversePay, Agents, Banks | Bank transfer to agent accounts |
| Mobile Money Settlement | Daily (T+1) | InversePay, Mobile Money Providers | Net settlement via bank transfer |
| Bank Settlement | Daily (T+1) | InversePay, Partner Banks | RTGS or ACH transfer |
| International Partner Settlement | Weekly (T+5) | InversePay, Remittance Partners | SWIFT transfer, correspondent banking |
| Merchant Settlement | Daily or Weekly | InversePay, Merchants | Direct deposit to merchant accounts |

### **5.2 Reconciliation Processes**

| Reconciliation Type | Frequency | Method | Resolution Process |
|--------------------|-----------|--------|-------------------|
| Transaction Reconciliation | Real-time and End-of-day | Automated matching | Exception handling workflow |
| Agent Float Reconciliation | Daily | Automated with manual verification | Agent support team intervention |
| Bank Account Reconciliation | Daily | Automated with bank statements | Finance team investigation |
| Partner Reconciliation | Daily and Monthly | API-based data exchange | Joint resolution committee |
| General Ledger Reconciliation | Daily | Automated accounting system | Finance team review |

---

## **6. Liquidity Management**

### **6.1 Float Management**

| Float Type | Purpose | Monitoring | Replenishment Trigger |
|-----------|---------|------------|----------------------|
| Agent Float | Enable cash-out transactions | Real-time dashboard | 20% of maximum float capacity |
| Mobile Money Float | Enable mobile money withdrawals | Hourly monitoring | 30% of average daily requirement |
| Bank Float | Enable bank withdrawals | Daily monitoring | 40% of average daily requirement |
| International Float | Enable cross-border payments | Daily monitoring | Currency-specific thresholds |

### **6.2 Treasury Management**

| Activity | Frequency | Responsibility | Risk Controls |
|---------|-----------|----------------|--------------|
| Cash Position Forecasting | Daily | Treasury Team | Minimum liquidity thresholds |
| FX Position Management | Real-time | Treasury System | Position limits, hedging policies |
| Liquidity Stress Testing | Weekly | Risk Management | Scenario analysis, contingency funding |
| Interbank Market Operations | As needed | Treasury Team | Counterparty limits, dealing authority |

---

## **7. Risk Management in Fund Flows**

### **7.1 Operational Risk Controls**

| Risk Type | Control Measure | Monitoring | Responsibility |
|----------|----------------|------------|----------------|
| Settlement Risk | Pre-funding requirements, exposure limits | Real-time | Risk Management |
| Liquidity Risk | Buffer requirements, credit lines | Daily | Treasury |
| Agent Risk | Float limits, transaction monitoring | Real-time | Agent Management |
| Fraud Risk | Pattern detection, velocity checks | Real-time | Fraud Team |
| Technology Risk | System redundancy, failover procedures | Continuous | IT Operations |

### **7.2 Financial Risk Controls**

| Risk Type | Control Measure | Monitoring | Responsibility |
|----------|----------------|------------|----------------|
| FX Risk | Hedging, position limits | Real-time | Treasury |
| Credit Risk | Counterparty limits, collateral | Daily | Risk Management |
| Interest Rate Risk | Gap analysis, duration matching | Weekly | Treasury |
| Concentration Risk | Diversification requirements | Monthly | Risk Management |
| Systemic Risk | Stress testing, contingency planning | Quarterly | Executive Committee |

---

## **8. Regulatory Reporting on Fund Flows**

| Report | Frequency | Recipient | Content |
|--------|-----------|-----------|---------|
| Transaction Volume and Value | Daily | Central Bank | Aggregated transaction data by type |
| Float Balance Report | Daily | Central Bank | Agent and system float positions |
| Suspicious Transaction Report | As needed | Financial Intelligence Unit | Details of suspicious transactions |
| Cross-Border Flow Report | Monthly | Central Bank, Foreign Exchange Authority | International payment flows |
| Liquidity Position Report | Weekly | Central Bank | System liquidity status |

---

## **9. Contingency Arrangements**

| Scenario | Contingency Measure | Activation Procedure | Recovery Time Objective |
|---------|---------------------|---------------------|--------------------------|
| Settlement Bank Failure | Alternate bank relationships | Crisis Management Team activation | 4 hours |
| Agent Liquidity Crisis | Emergency float provision | Agent Support escalation | 2 hours |
| System Outage | Manual processing procedures | IT Incident response | 1 hour |
| Cross-Border Settlement Failure | Alternative corridor activation | Treasury escalation | 24 hours |
| Regulatory Restriction | Compliance contingency plan | Compliance Officer notification | As required |

---

## **10. Document Control**

| Version | Date | Author | Approved By | Changes |
|---------|------|--------|-------------|---------|
| 1.0 | June 7, 2025 | Treasury Department | [Chief Financial Officer, Head of Compliance] | Initial document |

---

## **Appendices**

### **Appendix A: Detailed Account Structure**
### **Appendix B: Settlement Bank Details**
### **Appendix C: Reconciliation Procedures**
### **Appendix D: Regulatory References**
### **Appendix E: System Integration Specifications**
