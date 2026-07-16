# Yani-Donation-2024-Tracker-Dashboard
Track public donation made to support people affected by Typhoon Yagi in 2024, based on publicly bank statements of The Vietnam Fatherland Front (VFF) Central Committee.
## Methodology
### 1. Data collection
Vietnam goverment released their charity bank statement for typhoon Yagi with more than 12,000 pdf pages. Because parsing such a large volume of PDF files is time‑consuming, I used an already‑parsed Excel dataset to build the dashboard
### 2. Data processing
To save time, I applied a rule-based method for `Note` column to extract these meaningful features from text:
- Segment (Organization vs. Individual/Unknown)
- Clean message (remove redundant text, transaction ID, prefix- or sufix- parts)
- Name of donators

For more accurate pre‑processing, we can apply NLP libraries such as SpaCy, using its Named Entity Recognition (NER) capability to extract donor names and perform sentiment analysis on the text to identify warm, supportive messages.
### 3. Analysis method
- Apply logarithm method to scale donated amount into groups (1k-10k, 10k-100k, 100k-1m, 1m-10m,...) for analysis, as amount has highly skew distribution.
- Flag a donation as suspicious if the donation is from organization but donated amount is significantly low (e.g., <= 50k VND).
## Key findings
Donation behavior:
- Donation increased significantly from 10/09/2024 which is the first date of officially lauching the donation campaign. Before 10/09/2024, there were also a small numbers of early transfer from donators although the campaign has not been officially launched yet.
- People usually donated from 100k VND to 1 millions VND, with 100K VND is the most popular amount.
- There're a few of organizations that donated a very low amount - that is suspicious and may need to check further if those organizations have fake or stolen charity money
## Disclaimer
The data presented in this dashboard is the result of my independent development work with limitation, it is intended as a reference for the methodology and idea. I will not be responsible for any conclusions, decisions, or actions taken based on my dashboard.
