# Midterm 1: answers

GitHub username: devshyngys
Session code: zebra-28
Fingerprint:91488dd8

> Fill in the three lines above from `my_data/DATA.md`. Do not rename headings or table columns: a script reads the numbers.
> Write only in the empty cells and lines. Percentages as 0.78 or 78 %, money as plain numbers.

## AI-use declaration

(About half a page: which assistants or tools you used and for what. If you used none, say so.)

## Part 1: Retrieval and cost decision

### 1a. Metrics (all 60 questions)

| config | recall@1 | recall@3 | recall@5 | MRR@10 |
|---|---|---|---|---|
| A | 0.600 | 0.633 | 0.683 | 0.629 |
| B | 0.383 | 0.600 | 0.683 | 0.494 |

### 1b. Recall and 95 % Wilson interval of each candidate (recall at its own k)

| candidate | recall@k | lower | upper |
|---|---|---|---|
| A, k=3 | 0.633 | 0.507 | 0.744 |
| A, k=5 | 0.683 | 0.558 | 0.787 |
| B, k=3 | 0.600 | 0.474 | 0.714 |
| B, k=5 | 0.683 | 0.558 | 0.787 |

### 1c. Annual model cost in USD

| candidate | annual cost |
|---|---|
| A, k=3 | 29102.53 |
| A, k=5 | 38006.79 |
| B, k=3 | 19446.65 |
| B, k=5 | 21913.67 |

### 1d. Decision (at most 150 words)

Chosen candidate: B, k=3

(Decision, using your intervals and the budget. Give the recall of your choice for EN, RU and KK separately.)

By looking to A, k=5 costs $38,007 per year, which is over the $33,600 budget. so I exclude it, among the affordable candidates, B, k=5 has the highest recall, 0.683 [0.558, 0.787]. However, its interval overlaps with A, k=3 [0.507, 0.744] and B, k=3 [0.474, 0.714], so the difference is not proven. 
Because they are statistically tied, I choose the cheapest one, B, k=3, at $19,447 per year. Its recall by language: EN 0.60, RU 0.65, KK 0.55. Kazakh users are served worst, but with only 20 questions per language this gap is very uncertain.

### 1e. Next measurement (at most 60 words)

Test A, k=3, B, k=3 and B, k=5 on a larger set, for example 100 questions per language. Narrower intervals would show whether B, k=5 is really better and whether Kazakh recall is really lower. If B, k=5 clearly wins, I would switch to it, since it is still within budget

## Part 2: A document pipeline you can defend

### 2a. Numbers

| pipeline | overall accuracy | weakest cell (language, condition) | accuracy there | lower | upper | annual cost |
|---|---|---|---|---|---|---|
| H | 0.917 | RU, degraded | 0.867 | 0.703 | 0.947 | 33840.97 |
| L | 0.811 | KK, clean | 0.700 | 0.521 | 0.833 | 7200.00 |

Personal-data pages per year sent abroad under H: 204400

### 2b. Memo (at most 300 words)

To: Head of Operations. Subject: choosing the invoice pipeline.

Accuracy. Overall, H reads 91.7% of invoices exactly and L 81.1%, a real gap in favour of H. But the overall figure hides the weakest group: Kazakh clean scans under L, 70.0% [52.1%, 83.3%]. The same cell under H is 90.0% [74.4%, 96.5%]. With only 30 invoices per cell these intervals overlap, so the gap is not proven, but Kazakh invoices are the group to watch. H's weakest cell is Russian degraded scans, 86.7% [70.3%, 94.7%].

Personal data. 204,400 pages per year carry a person's name and ИИН, which Law No. 94-V covers.
- Where does the scan go? H: to a data centre abroad. L: stays on our server in Kazakhstan.
- Who stores it? H: the vendor; we do not know its sub-processors. L: we do.
- For how long? H: unknown. A vendor's statement is not a compliance review, so we must get retention terms in a signed contract. L: we decide.
For H we would still have to find out: the legal basis for the transfer, the retention period, and whether our data is used for training.

Safeguards we can verify: for H, mask the ИИН area before upload and audit a monthly sample of sent images. For L, delete scans after 30 days with a deletion log, and review the access log monthly. For both, send low-confidence Kazakh invoices to human review and re-test on 200 invoices per cell.

Choice: L. It costs $7,200 per year versus $33,841 for H and keeps the ИИН in Kazakhstan. Its overall accuracy is lower, so human review covers that gap. Remaining risk: Kazakh invoices are read worst, and we are responsible for the server's security ourselves.

## Part 3: Explain your own numbers

### Q1

Number:
Why (at most 40 words):

### Q2

Number:
Why (at most 40 words):

### Q3

Number:
Why (at most 40 words):

### Q4

Number:
Why (at most 40 words):

### Q5

Number:
Why (at most 40 words):
