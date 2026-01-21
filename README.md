# AI-Powered Sales Call Evaluation & Agent Dashboard (n8n Workflow)

## Overview
This **n8n workflow** automates the evaluation of sales calls using AI scoring and generates a performance summary for each agent. It leverages **LLaMA 3 AI** to analyze call transcripts and provide:

- Call quality scoring across key sales skills  
- Conversion tracking  
- Agent performance aggregation  
- Personalized 2-sentence reviews  

The workflow is ideal for **call centers, sales teams, or customer service managers** who want actionable insights into agent performance.

---

## Features

- **Automated Data Processing**: Evaluate multiple calls in batches.  
- **AI Scoring**: Calls are scored (0–10 per category) for:
  - Greeting
  - Discovery
  - Pitch
  - Objection Handling
  - Closing  
  Maximum total score = 50.

- **Call Outcome Tracking**: Determines if a call resulted in a **Closed** sale.  
- **Agent-Level Aggregation**: Calculates:
  - Average call quality  
  - Conversion rate (%)  
  - Final weighted performance score  
  - Verdict: Top Performer / Average Performer / Needs Improvement  

- **HTML Dashboard Generation**: Prepares visual HTML blocks for each agent’s performance.  
- **AI-Generated Reviews**: Generates a concise 2-sentence review for each agent.  

---

## Workflow Steps

1. **Manual Trigger**  
   - Starts the workflow manually (or can be scheduled automatically).  

2. **Load Sample Data**  
   - Simulates sales call transcripts with agent names, transcripts, and outcomes.  

3. **Split Calls**  
   - Processes calls one by one to allow batch evaluation.  

4. **HTTP Request (AI Scoring)**  
   - Sends each transcript to **LLaMA 3 AI** to score calls on the 5 key categories.  

5. **Calculate Call Quality**  
   - Aggregates scores from AI response.  
   - Determines call quality (0–50) and checks if the call is closed.  

6. **Aggregate Agent Data**  
   - Groups calls by agent and calculates:
     - Average quality score  
     - Conversion rate  
     - Final performance score (weighted formula: 60% quality, 40% conversion)  
     - Verdict  

7. **Final Score & Dashboard HTML**  
   - Generates formatted HTML for agent dashboards showing scores, metrics, and verdict.  

8. **HTTP Request (AI Review)**  
   - Generates a 2-sentence AI review for each agent based on performance metrics.

---

## Tech Stack

| Component        | Purpose                                           |
|-----------------|---------------------------------------------------|
| **n8n**          | Workflow automation platform                       |
| **LLaMA 3 AI**   | AI model for scoring call quality and writing reviews |
| **JavaScript**   | Data processing, aggregation, and HTML formatting |
| **HTML**         | Agent dashboard generation                         |
| **HTTP Request** | API calls to LLaMA 3 for scoring and review       |

---

## Setup Instructions

1. **Install n8n**  
   Follow the [n8n installation guide](https://docs.n8n.io/getting-started/installation/).

2. **Import Workflow**  
   - Import the workflow JSON into n8n.

3. **Configure Credentials**  
   - **HTTP Header/Bearer Auth** for AI API access.  

4. **Adjust Parameters**  
   - Replace sample data with actual sales call transcripts.  
   - Update AI model, endpoint, or scoring categories if needed.  

5. **Run Workflow**  
   - Trigger manually or schedule to run daily/weekly for automated call evaluation.  

---

## Example Dashboard Output
```html
<div style="font-family: Arial; border: 1px solid #ccc; padding: 15px; border-radius: 8px;">
  <h2 style="color: green;">Ali Khan - Top Performer</h2>
  <p><b>Performance Score:</b> 92.50 / 100</p>
  <p><b>Metrics:</b> Quality 48.0/50 | Conversion 95.0%</p>
</div>

<div style="font-family: Arial; border: 1px solid #ccc; padding: 15px; border-radius: 8px;">
  <h2 style="color: orange;">Sara Ahmed - Average Performer</h2>
  <p><b>Performance Score:</b> 68.30 / 100</p>
  <p><b>Metrics:</b> Quality 35.5/50 | Conversion 75.0%</p>
</div>

---


Contact:ihsanmehmood384@gmail.com
