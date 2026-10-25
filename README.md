# KDC-AgentPay-Mastercard---XRPL-Swell-Hackathon
KDC AgentPay  Mastercard Payment

KDC AgentPay — Mastercard × XRPL Swell Hackathon
Hackathon project concept :
Build KDC AgentPay, an autonomous AI payment agent that uses Mastercard's AP4M payment primitive and RLUSD on the XRP Ledger (XRPL).

The goal is to demonstrate that an AI agent can discover a service, evaluate its price, authorize a payment under predefined rules, and settle the transaction using RLUSD — without asking a human to approve each payment.

The system will use a pre-funded XRPL wallet, configurable spending limits, a transaction policy engine, and a payment history dashboard.
Proposed architecture : Attached as an image --> .

Hackathon demonstration
1. An AI agent identifies an API service costing 0.25 RLUSD.
2. It checks the merchant against an allowlist and verifies its remaining budget.
3. The AP4M integration prepares the agentic payment request.
4. The XRPL wallet signs and submits the RLUSD payment.
5. The agent verifies ledger settlement and receives a receipt.
6. The dashboard records the transaction hash, merchant, amount, and status.
The agent can repeat this process autonomously within its authorized limits. A kill switch, transaction caps, and daily budget prevent uncontrolled spending.

Download the project ( File Attached ) .

The ZIP contains a runnable local application with a payment dashboard, spending-policy engine, RLUSD Testnet transaction code, transaction audit history, and setup instructions.
Current implementation status
Component	Status
Payment dashboard	Built
Autonomous spending rules	Built
Merchant allowlist	Built
XRPL Testnet transaction submission	Implemented, requires configuration
RLUSD settlement verification	Implemented, not yet tested live
Mastercard AP4M integration	Awaiting official API access
Production deployment	Not ready

Mastercard describes AP4M as infrastructure for permissioned machine-to-machine payments. 

Mastercard Investor Relations


 Ripple provides the RLUSD Testnet issuer and setup instructions required to run the blockchain portion. 

Ripple Docs



How to run it
Extract the ZIP, open a terminal inside kdc-agentpay, and run:

<> Bash :
npm install

npm start

Open http://localhost:3000.

The application starts in simulation mode. To submit actual Testnet transactions, follow the included wallet funding and RLUSD trust-line instructions.

Important: This is a working starter, not a completed AP4M integration or proof of a settled transaction. The next development milestone is connecting Mastercard's official AP4M sandbox, followed by demonstrating an independently authorized RLUSD payment with a verifiable XRPL transaction hash.

------------------------------------------------------------------------------------------------------------------------------------------------


I'll use https://hackathon.ap4m.build as the Mastercard AP4M API base URL for KDC AgentPay.

I attempted to open the official API reference, but the documentation endpoint returned 401 Unauthorized. That means I can't yet verify the exact authentication, payment, or settlement request formats.

The integration should support:
1. Authentication: Obtain the AP4M bearer token using the documented step 1.
2. Autonomous authorization: Check the agent's merchant allowlist, per-payment limit, and daily budget.
3. AP4M payment: Submit the documented payment request using the bearer token.
4. XRPL settlement: Verify the resulting RLUSD transaction on XRPL.
5. Audit dashboard: Display payment status, transaction hash, and any API errors.
I'll keep simulation mode available so the project can be tested without risking funds.
Download the updated project
 Download KDC AgentPay — AP4M API Adapter Update (ZIP)

This update includes the AP4M API base URL, configurable authentication and payment endpoints, bearer-token request handling, timeout handling, and API error reporting. The original XRPL Testnet functionality remains included.

One thing I need from you: Please open the AP4M API reference in your browser and upload the Markdown file here, or paste its contents.

With the exact API specification, I can complete the authentication and autonomous payment integration rather than relying on unverified endpoint names.


KDC AgentPay — Autonomous Agentic Payments Solution
Mastercard AP4M × RLUSD × XRP Ledger

KDC AgentPay is a proposed financial technology platform that enables AI agents to make payments independently, without requiring a human to approve every transaction.

It combines Mastercard's Agent Pay for Machines (AP4M) framework for machine identity, authorization, and payment orchestration with RLUSD on the XRP Ledger for blockchain settlement.

Mastercard describes AP4M around four capabilities: credentialing, permissioning, transacting, and settling. 

Mastercard US


1. What problem does KDC AgentPay solve?
Traditional payment systems are designed primarily for humans. A customer chooses a product, confirms the amount, and authorizes payment.

AI agents operate differently. They may need to purchase computing resources, access APIs, renew services, or pay suppliers continuously.

KDC AgentPay removes the need for repetitive manual approvals while maintaining financial controls.

The human establishes the rules in advance. The AI agent makes individual payment decisions within those rules.
2. How Mastercard AP4M is used
AP4M capability	KDC AgentPay implementation
Credentialing	Establish the AI agent's verified payment identity
Permissioning	Enforce authorized merchants, payment limits, and spending budgets
Transacting	Initiate agent-to-merchant payments through the AP4M integration
Settling	Coordinate RLUSD payments and verify settlement on XRPL

The important distinction is that Mastercard AP4M provides the agentic payment framework, while XRPL provides the blockchain infrastructure used to transfer RLUSD.
3. Interactive example of the outcome
The following is an illustrative demonstration of how the completed system would operate.
KDC AgentPay
Autonomous Payment Control Center
Simulation

Agent wallet25.00
RLUSD

Daily spent0.00
of 10.00 RLUSD

Autonomous payments
Agent authorized within policy
Stop agent
Maximum payment2.00 RLUSD


AI service purchase requests
Select a service to simulate an autonomous payment decision. The agent applies the configured spending rules.AI Data API

0.25 RLUSD

Run agent 
Cloud Compute

0.75 RLUSD

Run agent 
Market Analytics

1.50 RLUSD

Run agent 
Premium Service

4.00 RLUSD

Run agent 

Payment activity
Reset demo
No transactions yet. Run an agent above.

This interactive demonstration shows policy decisions and a simulated wallet balance. It does not contact Mastercard, transfer RLUSD, or produce real transaction hashes.
4. Expected real-world transaction outcome
AI agent purchases an API service

1. Service discovered
   
   The agent identifies an approved merchant offering market data for 0.25 RLUSD.
2. AP4M permission checked
   
   The payment request is associated with the agent's credentials and evaluated against its authorization rules.
3. Payment initiated
   
   The application submits the payment through the documented AP4M workflow.
4. RLUSD settled on XRPL
   
   An authorized wallet signs the transaction. The system waits for validated ledger confirmation.
5. Service delivered
   
   The merchant verifies the payment and provides the requested data to the AI agent.

XRPL's agentic transaction documentation describes deterministic transaction confirmation and native support for issued currencies such as RLUSD. 

XRP Ledger

5. Business applications

Autonomous cloud purchasing
AI agents purchase computing time, storage, or inference services according to demand and budget.

Financial data and API payments
Agents pay for market information, business intelligence, and API access without repetitive checkout procedures.


Machine-to-machine commerce
Connected machines and business systems automatically pay approved suppliers for services or resources.



6. Hackathon deliverables and completion status
Deliverable	Expected outcome
AI payment agent	Independently decides when an eligible payment is necessary
Mastercard AP4M	Authenticated payment requests using the official API
RLUSD wallet	Pre-funded wallet capable of authorized payments
XRPL integration	Validated blockchain transaction and transaction hash
Risk management	Budget limits, merchant allowlist, duplicate prevention, emergency stop
Dashboard	Payment activity, balances, policy decisions, receipts

The previous KDC AgentPay starter provides a foundation for this system. However, the AP4M API documentation still returns 401 from my environment, so its endpoint-level integration remains unverified. No live AP4M payment or XRPL settlement has been demonstrated here.
7. Project pitch for Mastercard × XRPL Swell
KDC AgentPay — Giving AI Agents the Ability to Pay, Safely and Autonomously.

KDC AgentPay enables AI agents to become trusted participants in digital commerce. By combining Mastercard Agent Pay for Machines with RLUSD settlement on the XRP Ledger, the platform allows autonomous software to purchase services, pay suppliers, and complete machine-to-machine transactions without individual human approvals.

Businesses define spending policies and authorized recipients in advance. AI agents operate independently within those limits, while every completed payment produces a verifiable settlement record.

Our vision is to create a secure, scalable financial infrastructure where AI agents can manage routine economic transactions at machine speed.

The strongest hackathon proof will be one genuine end-to-end transaction: an AI agent independently chooses an approved service, uses the authenticated Mastercard AP4M workflow, settles RLUSD on XRPL, and displays a verified transaction hash without human approval at payment time.

That result would distinguish KDC AgentPay from a wallet demonstration or an ordinary automated payment script.

---------------------------------------------------------------------------------------------------------------------------------------


  # KDC AgentPay
**Autonomous AI Payments Powered by Mastercard AP4M and RLUSD on the XRP Ledger**

KDC AgentPay is an agentic payment platform designed to enable artificial intelligence agents to autonomously purchase digital services, access APIs, and pay approved merchants using RLUSD on the XRP Ledger (XRPL).

The project combines Mastercard's Agent Pay for Machines (AP4M) framework with blockchain settlement to create a secure, programmable financial infrastructure for AI-driven commerce.

**The Problem**

Traditional digital payments depend on human interaction and approval. As AI agents become capable of performing increasingly complex business tasks, they need a secure way to transact independently while remaining within authorized financial limits.

**Our Solution**

KDC AgentPay allows businesses to assign an AI agent a payment identity, a spending budget, approved merchants, and transaction rules. The agent can then discover services, evaluate costs, initiate authorized payments, and verify settlement without requesting manual approval for each transaction.

**How It Works**

1. A business configures its AI agent and spending permissions.
2. The agent discovers a service and determines whether a purchase is necessary.
3. The policy engine checks the merchant, payment amount, and available budget.
4. The Mastercard AP4M integration coordinates the agentic payment workflow.
5. RLUSD is transferred on XRPL through an authorized wallet.
6. The platform verifies settlement and records a transaction receipt.

**Key Features**

- Autonomous AI-to-business payments
- Mastercard AP4M payment integration
- RLUSD stablecoin transactions on XRPL
- Configurable spending limits and merchant permissions
- Automated payment verification and audit trails
- Real-time monitoring dashboard and emergency stop controls

**Target Customers**

AI application developers, cloud computing providers, API marketplaces, fintech companies, enterprise automation platforms, and machine-to-machine service operators.

**Business Model**

KDC AgentPay could generate revenue through enterprise subscriptions, developer API plans, usage-based platform fees, and managed payment orchestration services, subject to applicable commercial and regulatory requirements.

**Hackathon Objective**

Demonstrate a complete autonomous payment journey in which an AI agent selects an approved digital service, initiates payment through Mastercard AP4M, settles RLUSD on XRPL, and verifies the blockchain transaction without requiring human approval at the moment of payment.

**Current Stage**

Prototype development. The dashboard and policy-engine concepts are established, while authenticated AP4M integration and a verified end-to-end RLUSD settlement remain milestones to complete.

**Vision**

To build trusted financial infrastructure for the next generation of AI-powered commerce, where autonomous agents can transact securely, transparently, and efficiently.
