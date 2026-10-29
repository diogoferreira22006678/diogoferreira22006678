<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0F172A,50:1E293B,100:243B55&height=200&section=header&text=Diogo%20Ferreira&fontSize=48&fontColor=ffffff&fontAlignY=40" alt="Diogo Ferreira"/>
</p>

<h3 align="center">AI Engineer &nbsp;|&nbsp; LLM &amp; Agentic Systems &nbsp;|&nbsp; RAG</h3>

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=500&size=19&duration=2800&pause=900&color=7AA2F7&center=true&vCenter=true&width=640&lines=Multi-agent+LLM+pipelines+on+Amazon+Bedrock;Retrieval+grounded+in+real+knowledge;Evaluation+before+deployment;From+prototype+to+production" alt="typing"/>
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/diogo-ferreira-6731a1209/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white"/></a>
  <a href="https://www.closer.pt"><img src="https://img.shields.io/badge/Closer-AI%20Engineer-1E293B?style=flat-square"/></a>
  <img src="https://komarev.com/ghpvc/?username=diogoferreira22006678&style=flat-square&color=243B55&label=views"/>
</p>

<br/>

## <img src="https://api.iconify.design/lucide/user-round.svg?color=%237aa2f7" width="22" align="top"/> About

I build LLM systems that have to work in production, not just in a notebook. At **Closer** I design and develop agentic AI on AWS for enterprise clients, working across both implementation and architecture. My focus is on the parts that decide whether an AI system is actually useful: grounding, routing, evaluation and integration with the tools people already use.

MSc in Data Science.

<br/>

## <img src="https://api.iconify.design/lucide/cpu.svg?color=%237aa2f7" width="22" align="top"/> Current Work

### Enterprise Ticket Triage with AI Agents
<sub>Closer &nbsp;|&nbsp; client project &nbsp;|&nbsp; Amazon Bedrock &nbsp;|&nbsp; AWS Serverless</sub>

A multi-agent system that takes incoming Jira service tickets for an industrial client and handles them end to end: it checks that the ticket is complete, sends it to the right team and drafts an answer grounded in the client's own documentation and ticket history. I work on development and on the architecture decisions.

```mermaid
flowchart LR
    J[Jira ticket] --> Q[Qualification agent]
    Q -->|complete and classified| R[Routing agent]
    Q -->|missing fields| J
    R --> S[Support agent]
    R -.->|lookup| M[(Routing matrix)]
    S -.->|retrieval| KB[(Bedrock Knowledge Bases)]
    S --> C[Comment on ticket]
    R --> T[Teams notification]
```

<table>
<tr>
<td width="50%" valign="top">

**Agents**

<img src="https://api.iconify.design/lucide/chevron-right.svg?color=%2364748b" width="14"/> <b>Qualification</b> classifies the ticket and flags missing information<br/>
<img src="https://api.iconify.design/lucide/chevron-right.svg?color=%2364748b" width="14"/> <b>Routing</b> assigns it to the right resolver group from a rules matrix<br/>
<img src="https://api.iconify.design/lucide/chevron-right.svg?color=%2364748b" width="14"/> <b>Support</b> drafts a response using retrieval over documentation and past tickets<br/>

**Knowledge ingestion**

<img src="https://api.iconify.design/lucide/chevron-right.svg?color=%2364748b" width="14"/> Multi-source pipelines from Jira (Cloud and On-Prem), SharePoint and product documentation into Bedrock Knowledge Bases<br/>
<img src="https://api.iconify.design/lucide/chevron-right.svg?color=%2364748b" width="14"/> Two validation gates, PII redaction, deduplication and a quarantine and remediation loop for bad documents<br/>

</td>
<td width="50%" valign="top">

**Routing that business users can maintain**

<img src="https://api.iconify.design/lucide/chevron-right.svg?color=%2364748b" width="14"/> The issue-type to resolver mapping lives in an Excel file on SharePoint that non-technical staff edit directly<br/>
<img src="https://api.iconify.design/lucide/chevron-right.svg?color=%2364748b" width="14"/> Lambda + EventBridge poll it through the Microsoft Graph API, replacing an earlier Power Automate flow<br/>

**Safety and delivery**

<img src="https://api.iconify.design/lucide/chevron-right.svg?color=%2364748b" width="14"/> Bedrock Guardrails in front of the agents, with input tagging to stop false prompt-attack detections on legitimate ticket text<br/>
<img src="https://api.iconify.design/lucide/chevron-right.svg?color=%2364748b" width="14"/> Event-driven, serverless deployment with separate integration and agent repositories<br/>
<img src="https://api.iconify.design/lucide/chevron-right.svg?color=%2364748b" width="14"/> Validated in UAT on a test Jira project, now moving to production starting with the knowledge bases and the Qualification agent<br/>

</td>
</tr>
</table>

<p>
  <img src="https://img.shields.io/badge/Amazon%20Bedrock-232F3E?style=flat-square&logo=amazonwebservices&logoColor=white"/>
  <img src="https://img.shields.io/badge/Bedrock%20Knowledge%20Bases-232F3E?style=flat-square"/>
  <img src="https://img.shields.io/badge/Bedrock%20Guardrails-232F3E?style=flat-square"/>
  <img src="https://img.shields.io/badge/AWS%20Lambda-FF9900?style=flat-square&logo=awslambda&logoColor=white"/>
  <img src="https://img.shields.io/badge/EventBridge-E7157B?style=flat-square&logo=amazoneventbridge&logoColor=white"/>
  <img src="https://img.shields.io/badge/Jira-0052CC?style=flat-square&logo=jira&logoColor=white"/>
  <img src="https://img.shields.io/badge/Microsoft%20Graph-5E5E5E?style=flat-square&logo=microsoft&logoColor=white"/>
</p>

**Also exploring:** evaluation for agent and RAG reliability, multi-stage retrieval and inference, containerised AI services.

<br/>

## <img src="https://api.iconify.design/lucide/folder-git-2.svg?color=%237aa2f7" width="22" align="top"/> Selected Projects

<table>
<tr>
<td width="50%" valign="top">

### LusoChat
<sub>RAG academic assistant</sub>

Answers academic questions from a curated knowledge base instead of the model's memory, using a multi-stage inference pipeline and embedding-based semantic retrieval behind a FastAPI service.

`RAG` `Embeddings` `FastAPI` `Python`

</td>
<td width="50%" valign="top">

### Cyanotypes
<sub>AI matchmaking platform</sub>

Matches profiles by meaning rather than keywords, with NLP similarity and a vector ranking engine running as Dockerised inference services. Deployed in an EU research context.

`NLP` `Vector Ranking` `Docker` `Python`

</td>
</tr>
</table>

<br/>

## <img src="https://api.iconify.design/lucide/wrench.svg?color=%237aa2f7" width="22" align="top"/> Stack

**AI / LLM**

<p>
  <img src="https://img.shields.io/badge/Amazon%20Bedrock-232F3E?style=flat-square&logo=amazonwebservices&logoColor=white"/>
  <img src="https://img.shields.io/badge/Multi--Agent%20Systems-6E40C9?style=flat-square"/>
  <img src="https://img.shields.io/badge/RAG-8B5CF6?style=flat-square"/>
  <img src="https://img.shields.io/badge/Vector%20Search-2563EB?style=flat-square"/>
  <img src="https://img.shields.io/badge/Sentence%20Transformers-F97316?style=flat-square"/>
  <img src="https://img.shields.io/badge/Gemini%20API-4285F4?style=flat-square&logo=googlegemini&logoColor=white"/>
</p>

**Backend, Cloud & Data**

<p>
  <img src="https://skillicons.dev/icons?i=python,fastapi,aws,docker,laravel,php,mysql,sqlite,git,linux&perline=10&theme=dark"/>
</p>

<br/>

## <img src="https://api.iconify.design/lucide/globe.svg?color=%237aa2f7" width="22" align="top"/> International Presentations

Presented AI platforms and LLM systems at research and innovation events in

<img src="https://flagcdn.com/20x15/be.png" width="20"/> Belgium &nbsp;&nbsp;
<img src="https://flagcdn.com/20x15/it.png" width="20"/> Italy &nbsp;&nbsp;
<img src="https://flagcdn.com/20x15/cz.png" width="20"/> Czech Republic

<br/>

## <img src="https://api.iconify.design/lucide/activity.svg?color=%237aa2f7" width="22" align="top"/> Activity

<p align="center">
  <img src="https://streak-stats.demolab.com?user=diogoferreira22006678&theme=tokyonight&hide_border=true&background=0F172A" alt="GitHub streak"/>
</p>

<p align="center"><sub>Building production AI systems that go beyond demos.</sub></p>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:243B55,50:1E293B,100:0F172A&height=110&section=footer"/>
