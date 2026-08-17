# Lab 17 Benchmark Report

- Implementation: `student`
- Kind: `practice`
- Cases: **11**
- Passed: **11/11**
- Evidence hit rate: **100.0%**
- Average retrieval latency: **1208.1 ms**
- Average token reduction vs full source context: **19.1%**

| Case | Layer | Pass | Latency ms | Retrieved tokens | Token reduction | Missing / Error |
| --- | --- | --- | ---: | ---: | ---: | --- |
| E01 | short_term | PASS | 0.0 | 133 | 0.0% |  |
| E06 | semantic | PASS | 2103.8 | 148 | 67.8% |  |
| E09 | long_term | PASS | 2322.9 | 603 | 0.0% |  |
| E10 | short_term | PASS | 0.3 | 195 | 0.0% |  |
| E02 | long_term | PASS | 1900.1 | 899 | 0.0% |  |
| E03 | long_term | PASS | 2597.1 | 908 | 0.0% |  |
| E04 | episodic | PASS | 300.4 | 166 | 24.9% |  |
| E05 | episodic | PASS | 304.6 | 156 | 29.4% |  |
| E07 | mixed | PASS | 2036.3 | 485 | 14.2% |  |
| E11 | semantic | PASS | 269.5 | 146 | 74.2% |  |
| E08 | long_term | PASS | 1454.5 | 901 | 0.0% |  |

## Evidence excerpts

### E01 - short_term

`<RECENT_TURNS> user: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. assistant: Da hieu: demo ca nhan ORCHID-27, uu tien Python, tranh Java, vi du ngan. user: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeline. assistant: Toi se uu tien timeline khi giai thich coroutine va Task. user: TODO: hoan thanh benchmark report truoc thu Sau luc 16:00. Day la open loop LAB-REPORT-1600. </RECENT_TURNS>`

### E06 - semantic

`EPISODE: {"id":"kb-payment-retry","entity":"Payment API Retry Policy","summary":"For POST /payments, every retryable request MUST send the same Idempotency-Key. Retry only HTTP 429 or transient 5xx errors, use exponential-backoff, and stop after max-3-retries. Marker: PAYMENT-RULE-3.","source":"internal-api-guideline-v3","updated_at":"2026-08-10T00:00:00Z"} metadata= EPISODE: For POST /payments, every retryable request MUST send the same Idempotency-Key. Retry only HTTP 429 or transient 5xx errors, use exponential-backoff, and stop after max-3-retries. Marker: PAYMENT-RULE-3. metadata=`

### E09 - long_term

`<USER_SUMMARY> Lan's main pursuit is the LOTUS-88 project. They prioritize using Java and Spring Boot for backend development and do not use Python.  Lan prefers Java and Spring Boot for backend development. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-01 11:00:20     Source: message     Content: Lab Assistant (assistant): Da hieu: LOTUS-88, Java + Spring Boot cho backend examples.   - Created At: 2026-08-01 11:00:00     Source: message     Content: [user] {   "user_id": "lan-lab17",   "first_name": "Lan",   "last_name": "Tran",   "user_alias": "Lan Tran" }: Toi la Lan. Du an cua toi la LOTUS-88. Toi uu tien Ja`

### E10 - short_term

`<SESSION_SUMMARY> user: Constraint: REVIEW-DEADLINE-1600 - project review is Friday at 16:00 and must not be forgotten. | assistant: Acknowledged review constraint. | user: Filler turn 1 about UI spacing. | assistant: Filler answer 1. | user: Filler turn 2 about naming. | assistant: Filler answer 2. | user: Filler turn 3 about logging. | assistant: Filler answer 3. </SESSION_SUMMARY> <DURABLE_NOTES> - user: Constraint: REVIEW-DEADLINE-1600 - project review is Friday at 16:00 and must not be forgotten. - assistant: Acknowledged review constraint. </DURABLE_NOTES> <RECENT_TURNS> user: Filler turn 4 about tests. assistant: Filler answer 4. user: Filler turn 5 about docs. assistant: Filler answe`

### E02 - long_term

`<USER_SUMMARY> The user is learning about async/await in programming and sometimes confuses coroutines with Tasks. Their personal project is named ORCHID-27. They have a task to complete a benchmark report by Friday at 16:00, which is an open loop LAB-REPORT-1600. Today, they are debugging async HTTP and have tried increasing the timeout to 60s without success. The user has been asked to check the connection pool, client lifecycle, and concurrency. The effective solution for a current issue is to reuse an aiohttp ClientSession and set concurrency to 20, with the root cause identified as connection churn rather than timeout threshold. This is related to incident ASYNC-FIX-20. For the company `

### E03 - long_term

`<USER_SUMMARY> The user is learning about async/await in programming and sometimes confuses coroutines with Tasks. Their personal project is named ORCHID-27, for which Python is preferred. They have a task to complete a benchmark report by Friday at 16:00. The user is debugging async HTTP and has tried increasing the timeout to 60s without success. The effective solution for a current issue is to reuse an aiohttp ClientSession and set concurrency to 20, with the root cause identified as connection churn rather than timeout threshold. This is related to incident ASYNC-FIX-20. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for thi`

### E04 - episodic

`EPISODE: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeline. metadata= EPISODE: TODO: hoan thanh benchmark report truoc thu Sau luc 16:00. Day la open loop LAB-REPORT-1600. metadata= EPISODE: Hom nay toi debug async HTTP. Toi da thu tang timeout len 60s nhung van fail. metadata= EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection churn, khong phai timeout threshold. Ma su co ASYNC-FIX-20. metadata= EPISODE: Da ghi nhan trajectory: increase timeout khong hieu qua; ClientSession + concurrency=20 giai quyet connection churn. metadata=`

### E05 - episodic

`EPISODE: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. metadata= EPISODE: Hom nay toi debug async HTTP. Toi da thu tang timeout len 60s nhung van fail. metadata= EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection churn, khong phai timeout threshold. Ma su co ASYNC-FIX-20. metadata= EPISODE: Da ghi nhan trajectory: increase timeout khong hieu qua; ClientSession + concurrency=20 giai quyet connection churn. metadata= EPISODE: Voi demo ca nhan cua Minh, ngon ngu uu tien la gi? metadata=`

### E07 - mixed

`<LONG_TERM> <USER_SUMMARY> The user is learning about async/await in programming and sometimes confuses coroutines with Tasks. Their personal project is named ORCHID-27, for which Python is preferred. They have a task to complete a benchmark report by Friday at 16:00. The user is debugging async HTTP and has tried increasing the timeout to 60s without success. The effective solution for a current issue is to reuse an aiohttp ClientSession and set concurrency to 20, with the root cause identified as connection churn rather than timeout threshold. This is related to incident ASYNC-FIX-20. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be `

### E11 - semantic

`EPISODE: {"id":"kb-async-http","entity":"Async HTTP Incident Playbook","summary":"When async HTTP calls time out, inspect connection pooling, downstream saturation and concurrency before increasing timeout. Reuse a long-lived client session where possible. Marker: CONN-POOL-FIRST.","source":"incident-playbook-2026","updated_at":"2026-08-11T00:00:00Z"} metadata= EPISODE: When async HTTP calls time out, inspect connection pooling, downstream saturation and concurrency before increasing timeout. Reuse a long-lived client session where possible. Marker: CONN-POOL-FIRST. metadata=`

### E08 - long_term

`<USER_SUMMARY> The user is learning about async/await in programming and sometimes confuses coroutines with Tasks. Their personal project is named ORCHID-27, for which Python is preferred. They have a task to complete a benchmark report by Friday at 16:00. The user is debugging async HTTP and has tried increasing the timeout to 60s without success. The effective solution for a current issue is to reuse an aiohttp ClientSession and set concurrency to 20, with the root cause identified as connection churn rather than timeout threshold. This is related to incident ASYNC-FIX-20. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for thi`
