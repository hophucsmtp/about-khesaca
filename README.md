# Khesaca Coffee - Automation System

Hệ thống tự động hóa toàn diện cho thương hiệu cà phê Khesaca (Gia đình vận hành).

```mermaid
flowchart TD
    %% 1. Input & Data Central
    DB[(Google Sheets / Airtable\nCentral Database)] 
    DB -->|Product, Inventory, Customer, Content Calendar| N

    subgraph Core [Core Automation Engine]
        N[n8n / Make.com\nOrchestrator]
    end

    subgraph AI [AI Intelligence Layer]
        Claude[Claude 3.5 Sonnet API]
        NB[NotebookLM]
        GPT[GPT-4o + Gemini]
        Tools[Flux • Kling • ElevenLabs • CapCut]
    end

    N <--> AI
    N <--> DB

    %% Main Pipelines
    subgraph Research [1. Research Pipeline]
        R1[Trending Scan\nTikTok, YouTube, Google Trends]
        R1 --> Claude
    end

    subgraph Content [2. Content Creation]
        C1[Generate Script + Caption]
        C2[Visual & Video AI]
        C3[SEO Blog]
        Claude --> C1 --> C2 --> C3
    end

    subgraph Approval [3. Human Review]
        H[Bạn + Vợ Review & Approve]
    end

    subgraph Distribution [4. Distribution]
        S1[Facebook • Instagram • TikTok • YouTube]
        S2[Website + Shopee + Lazada]
        S3[Zalo OA + Email]
        H --> S1 & S2 & S3
    end

    subgraph Sales [5. Sales Funnel]
        Sale[Lead → Chatbot → Nurturing → Order → Loyalty]
    end

    subgraph Analytics [6. Analytics]
        Ana[Looker Studio Dashboard]
        Ana -->|Feedback| DB
    end

    Research --> Content --> Approval --> Distribution --> Sales --> Analytics
    Analytics --> Research

    style Core fill:#fff3e0, stroke:#f57c00
    style AI fill:#e3f2fd, stroke:#1976d2
    style Approval fill:#fce4ec, stroke:#d81b60
