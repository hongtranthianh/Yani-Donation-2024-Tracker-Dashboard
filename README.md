# Yani-Donation-2024-Tracker-Dashboard
Track public donation made to support people affected by Typhoon Yagi in 2024, based on publicly bank statements of The Vietnam Fatherland Front (VFF) Central Committee.
## Methodology
### 1. Data collection
Vietnam goverment released their charity bank statement for typhoon Yagi with more than 12,000 pdf pages. However, parsing data from pdf is time consuming, from the internet I collected data already parsed in excel to build dashboard.
### 2. Data processing
For time saving, I'm applying rule-based method for `Note` column to extract these meaningful features from text:
- Segment (Organization vs. Individual/Unknown)
- Clean message (remove redundant text, transaction ID, prefix- or sufix- parts)
- Name of donators

However, for more accurate pre-processing we can apply NLP libraries such as Spacy with NER (Name Entity Recognition) capability to extract donator name and analyze sentitment from text to define warm messages.
### 3. Analysis method
- Apply logarithm method to scale donated amount into groups (1k-10k, 10k-100k, 100k-1m, 1m-10m,...) for analysis, as amount has highly skew distribution.
- Flag a donation as suspicious if the donation is from organization but donated amount is significantly low (e.g., <= 50k VND)
## Key findings
Donation behavior:
- Donation increased significantly from 10/09/2024 which is the first date of officially lauching the donation campaign. Before 10/09/2024, there were only a small numbers of early transfer from donators. 
- People donated 100K VND the most.
- There're proportion of organization that donated a very low amount - that is weird and may need to check further if those organizations have fake or stolen charity money
## Disclaimer
