flowchart TD
    %% 1. Input & Data Central
    DB[(Google Sheets / Airtable\nCentral Database)] 
    DB -->|Product, Inventory, Customer, Content Calendar| Core

    subgraph Core [Core Automation Engine]
        N[n8n / Make.com\nOrchestrator]
    end

    subgraph AI [AI Intelligence Layer]
        Claude[Claude 3.5 Sonnet / Opus API]
        NB[NotebookLM]
        GPT[GPT-4o / Gemini 2.5]
        AItools[ElevenLabs • Flux • Kling • CapCut API]
    end

    N <--> AI
    N <--> DB

    %% 2. Main Pipelines
    subgraph Research [1. Research & Idea Pipeline - Daily/Weekly]
        R1[Scan Trending\nGoogle Trends, TikTok Creative Center,\nYouTube Search, Shopee Hot]
        R2[Tìm Viral Content\nCà phê Khe Sanh, Brewing, Farm Story, ASMR]
        R3[Competitor Analysis\nKhe Sanh competitors]
        R1 & R2 & R3 --> Claude
    end

    subgraph Content [2. Content Creation Pipeline]
        C1[Generate Ideas + Script\nReels/TikTok/Carousel/Blog]
        C2[Visual Generation\nFlux / Leonardo / Midjourney]
        C3[Video Production\nKling AI / Runway / CapCut Auto-edit]
        C4[Voiceover + Music\nElevenLabs Vietnamese]
        C5[SEO Blog Post\nSurferSEO / Claude]
        Claude --> C1 --> C2 --> C3 --> C4 --> C5
    end

    subgraph Approval [3. Human Review & Approval]
        H[Bạn + Vợ Review\n(15-30 phút/ngày)\nApprove / Edit nhẹ]
    end

    subgraph Distribution [4. Distribution & Scheduling]
        S1[Multi-platform Scheduler\nn8n → Meta + TikTok + YT + Zalo]
        S2[Website Auto Publish\nWordPress]
        S3[Shopee/Lazada Sync]
        S4[Email + Zalo OA Sequence]
        H --> S1 & S2 & S3 & S4
    end

    subgraph Sales [5. Sales & CRM Pipeline]
        Sale1[Lead Capture\nWebsite + Social + Zalo]
        Sale2[Chatbot Auto Reply + Qualify]
        Sale3[Nurturing Sequence\nAbandoned Cart, Follow-up, Loyalty]
        Sale4[Order Processing\nSync Inventory + GHTK/GHN]
        Sale5[Upsell / Cross-sell]
    end

    subgraph Analytics [6. Analytics & Optimization]
        Ana[Looker Studio Dashboard\nReal-time Sales + Content Performance]
        Ana -->|Feedback Loop| DB
        Ana -->|Insight| Claude
    end

    Research --> Content --> Approval --> Distribution --> Sales --> Analytics
    Analytics --> Research

    style Core fill:#fff3e0
    style AI fill:#e3f2fd
    style Approval fill:#fce4ec
