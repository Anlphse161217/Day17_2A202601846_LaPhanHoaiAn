### Phân tích Benchmark
1. **Layer có hit rate thấp nhất:** Trong bản no-memory, Semantic và Long-term có hit rate thấp nhất (0%). Trong bản student của tôi, tất cả các layer đều đạt 100% PASS.
2. **Query retrieve nhiều token nhất:** Các case liên quan đến Long-term memory (E02, E03, E08) tiêu tốn nhiều token nhất (lên tới ~900 tokens) vì Context Block của Zep kéo theo rất nhiều fact của user.
3. **Case Mixed (E07):** Cần kết hợp bộ nhớ **Long-term** và **Semantic**. Evidence bắt buộc phải có là `Python` và `Idempotency-Key`.
4. **Token reduction:** Áp dụng token budget giúp tiết kiệm 19% số token thừa. Baseline `no-memory` có token reduction cực cao (81.8% vì xóa gần hết) nhưng hit rate rớt thảm hại xuống 18.2% do không truy hồi được lịch sử.
5. **E08 (Recency) & E10 (Compaction):** E08 cho thấy recency giải quyết conflict (chọn TypeScript thay vì fact cũ). E10 cho thấy compaction giữ lại được durable notes (REVIEW-DEADLINE-1600) kể cả khi vượt max recent messages.

### Câu hỏi báo cáo
1. **Layer quan trọng nhất trong bộ test này:** Long-term memory, vì nó xử lý nhiều test case nhất (E02, E03, E08, E09), giúp giải quyết bài toán recency và user isolation.
2. **Trade-off giữa Zep Cloud và Redis+Qdrant:** Zep cung cấp managed memory (Context Block, tự lo user graph, recency, privacy) giúp phát triển nhanh. Tuy nhiên Redis+Qdrant cho phép toàn quyền kiểm soát baseline, quản lý logic routing và không bị phụ thuộc vào cloud/API limit, đổi lại phải tự code rất nhiều boiler-plate.
3. **Guardrail chống memory poisoning:** Yêu cầu consent trước khi nạp dữ liệu (như data/consent.json), cô lập user_id (tránh leak data E09), và process heartbeat chỉ để de-duplicate, nghiêm cấm heartbeat tự ý tạo instruction mới.
