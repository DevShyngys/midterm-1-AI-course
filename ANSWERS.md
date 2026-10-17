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
| H | | | | | | |
| L | | | | | | |

Personal-data pages per year sent abroad under H:

### 2b. Memo (at most 300 words)

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
