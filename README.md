Production-Ready n8n AI Lead Qualification & CRM Alerting Workflow Architecture
An autonomous, enterprise-grade n8n automation pipeline engineered for real-time lead qualification, persistent database synchronization, and instant multi-channel sales alerting.

Built specifically to eliminate manual lead triaging and reduce lead-to-response times from hours to under 5 seconds, this workflow demonstrates how modern event-driven orchestration can integrate Large Language Models (LLMs) with relational databases and instant messaging APIs to power scalable sales operations.

🛠️ Tech Stack & Key Technologies
Orchestration & Workflow Engine: n8n (Event-driven Webhook execution)

AI Scoring & LLM Inference: Groq Cloud API running Llama 3

Database & Persistent Memory: Supabase (PostgreSQL with dynamic dual-branch upsert logic)

Instant Dispatch System: Meta WhatsApp Cloud API

Data Engineering & Formatting: Custom JavaScript Normalization Nodes

📐 End-to-End Pipeline Breakdown
1. Webhook Lead Ingestion
Captures incoming lead payloads in real time via custom HTTP POST Webhook endpoints.

Designed to ingest structured data directly from landing pages, contact forms, or ad campaign webhooks without network latency or payload drops.

2. Custom Data Normalization (JavaScript)
Passes raw JSON payloads through a custom JavaScript node to sanitize input formatting.

Strips trailing characters, handles missing field fallbacks, and restructures inconsistent key-value pairs to ensure zero execution failures downstream.

3. AI Lead Scoring & Intent Classification (Groq Llama 3)
Sends sanitized lead properties to Groq Cloud API for ultra-fast, multi-dimensional evaluation.

Evaluates buyer intent, budget thresholds, and response urgency.

Returns structured JSON output categorizing leads into actionable priority tiers (High-Intent vs. Low-Priority).

4. Dynamic Supabase Sync (PostgreSQL)
Utilizes dual-branch database logic to query existing contacts by unique identifiers (Email/Phone).

Executes automated dynamic upserts: updating existing profile records or inserting new lead entries seamlessly without primary key collisions.

5. High-Priority Alert Dispatch (WhatsApp Cloud API)
Triggers instant, rich-text WhatsApp notifications directly to designated sales representatives or alerting groups for warm leads.

Formats AI rationale, buyer background, budget details, and quick-action contact links into a single actionable alert message.

⚙️ How to Deploy & Setup
Clone the Repository:
git clone https://github.com/Nazuuu_Ali/n8n-ai-lead-qualification-agent.git

Import Workflow to n8n:

Open your n8n Instance or Cloud Dashboard.

Go to Workflows -> Import from File.

Select workflow.json from this repository.

Configure Environment Variables / Credentials:

Groq API Key: Add your Groq Cloud API credentials.

Supabase Credentials: Configure Host, Port, Database Name, and Service Role Keys.

Meta WhatsApp Cloud API: Add your Bearer Access Token and Phone Number ID.

Activate Workflow:

Toggle the workflow switch from Inactive to Active to begin listening to webhook events.

📄 License
This repository is open-source and available under the MIT License.
