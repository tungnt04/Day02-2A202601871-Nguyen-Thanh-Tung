# Group Report — Day 02

## Thành viên nhóm

| STT | Họ và tên | Mã học viên |
|-----|-----------|-------------|
| 1   |Nguyễn Hoài Nam| 2A202602016 | Bảo vệ & phản biện candidate problem được chọn, giữ focus vào bottleneck thật
| 2   |Lê Kim Nam| 2A202601803 |  Ghi chép thảo luận, soạn group report, đảm bảo format đúng yêu cầu
| 3   |Nguyễn Thanh Tùng| 2A202601871 | Vẽ current workflow chi tiết (bước, actor, input/output, thời gian)
| 4   |Phan Trần Tường Vy| 2A202601701 | Phản biện Problem Statement, đảm bảo actor/metric/boundary đủ cụ thể
| 5   |Vũ Ngọc Thiện| 2A202601793 | Vẽ future workflow (AI intervention point, human boundary, fallback)
| 6   |Nguyễn Quốc Hiệu| 2A202601627 | Vẽ current workflow chi tiết (bước, actor, input/output, thời gian)
| 7   |Nguyễn Duy Lâm| 2A202601073 | Tìm existing solutions/tools
| 8   |Nguyễn Khắc Huy| 2A202602036 | Tìm case study/pattern tương tự, phân tích điểm mạnh/khoảng trống
| 9   |Nguyễn Minh Hoàng| 2A202601609 | Quan sát Discord ticket, đo first response time, đếm re-open rate
| 10   |Nguyễn Tuấn Anh| 2A202601775 | ổng hợp kết quả validation, xác nhận/phản bác giả định nhóm
| 11   |Trần Đoàn Quang Vũ| 2A202601999 | So sánh Rule / Workflow / Agent, lập luận chọn/không chọn từng mức
| 12   |Lê Mạnh Cương| 2A202601137 |  Phản biện quyết định AI: "Có thật sự cần AI không?", challenge nhóm
| 13   |Lê Ngọc Khánh| 2A202601487 | Review Report trước khi nộp
| 14   |Đoàn Ngọc Chung| 2A202601869 | Hỗ trợ điều phối, theo dõi checklist nộp bài, đảm bảo đủ deliverable
| 15   |Nguyễn Minh Hiếu| 2A202601685 | So sánh before/after, tính impact metric, vẽ sơ đồ Mermaid/ASCII
| 16   |Bùi Đức Lân| 2A202602037 | Điều phối thảo luận, giữ timeline, chốt quyết định khi nhóm bế tắc

---

# Phase 3 — Group Convergence

## Candidate problem nhóm chọn

```text
TA mất 15-20 phút/ticket trên Discord để đọc 10-20 tin nhắn rải rác, tra cứu thông tin và soạn câu trả lời hướng dẫn kỹ thuật; khiến 50 ticket/ngày ngốn 15h công của 3 TAs và học viên phải chờ trung bình 2.8h mới nhận được phản hồi.
```

Vì sao chọn:

```text
- Actor cực kỳ rõ: TA trực kênh hỗ trợ Discord.
- Workflow lặp lại 50 lần/ngày với pattern gần như giống nhau.
- Bottleneck đo được bằng thời gian cụ thể (15-20 phút/ticket).
- Impact lớn: 15h công/ngày cho 3 TAs + học viên chờ 2.8h.
- Có thể so sánh No AI / Rule / Workflow / Agent rất rõ.
- Nhóm hiểu domain vì đang là thực tập sinh trong chương trình đào tạo này.
```

Vì sao không chọn các candidate còn lại:

```text
- Các bài toán cá nhân (đọc worksheet, tổng hợp ghi chú) có impact nhỏ hơn nhiều so với bài toán TA support (50 ticket/ngày × 3 TAs).
- Bài toán TA support có dấu hiệu thật rõ nhất: thời gian chờ 2.8h có thể đo trực tiếp từ Discord timestamp.
- Các bài toán khác khó vẽ before/after workflow rõ ràng bằng.
```

---

# Phase 4 — Quick Validation + Research giải pháp

## Bước 4.1 — Quick validation

### Option A — Quick interviews

Nhóm hỏi nhanh 2-3 TA/lab coach trong chương trình:

- **Lần gần nhất bạn gặp vấn đề này là khi nào?**
  → Mỗi ngày, liên tục. Đặc biệt nặng đầu tuần khi lab mới bắt đầu.

- **Bạn đang xử lý bằng workflow nào?**
  → Đọc hết thread ticket, mở tab tài liệu/Notion, tự gõ câu trả lời. Đôi khi copy-paste từ câu trả lời cũ nhưng phải sửa lại cho khớp context.

- **Bước nào mất thời gian hoặc khó chịu nhất?**
  → Đọc thread dài để hiểu context lỗi (tin nhắn rải rác, thiếu log, thiếu screenshot). Sau đó phải tự compose câu trả lời kỹ thuật.

- **Bạn mất khoảng bao lâu?**
  → Trung bình 15-20 phút/ticket. Ticket phức tạp có thể 30 phút.

- **Nếu tốt hơn, bạn muốn điều gì thay đổi?**
  → Muốn có ai/cái gì đọc thread giùm và tóm tắt vấn đề. Hoặc tự tra cứu tài liệu và gợi ý hướng trả lời để TA chỉ cần review.

### Option B — Quan sát thực tế trên Discord

- Đếm ticket trên kênh Discord support trong 3 ngày gần nhất: trung bình 45-55 ticket/ngày.
- Đo first response time từ timestamp: trung bình 2.5-3h (xác nhận con số 2.8h).
- Đếm số ticket phải hỏi lại vì thiếu context hoặc câu trả lời chưa rõ: khoảng 8-12%.

### Kết quả validation

| Nguồn | Số người / số mẫu | Tín hiệu xác nhận | Tín hiệu phản bác | Nhóm sửa problem thế nào |
|---|---:|---|---|---|
| Quick interview TA | 2-3 TA | 3/3 xác nhận đau nhất ở bước đọc context + gõ câu trả lời; ước tính 15-20 phút/ticket | 1 TA nói một số ticket đơn giản chỉ mất 3-5 phút (FAQ lặp lại) | Phân loại ticket: FAQ đơn giản (Rule) vs kỹ thuật phức tạp (Workflow + AI). Không cần AI cho tất cả. |
| Quan sát Discord | 3 ngày, ~150 tickets | 45-55 ticket/ngày, first response 2.5-3h, re-open rate ~10% | Một số ticket được trả lời nhanh (<30 phút) bởi TA đang online | Thu hẹp scope: tập trung giảm thời gian cho ticket kỹ thuật (chiếm ~70%), FAQ dùng rule/template |
| Hỏi học viên | 5-6 học viên | 5/6 nói chờ quá lâu, 3/6 nói phải tự tìm giải pháp trong lúc chờ | 1 học viên nói đã quen chờ, không thấy cần cải thiện | Thêm metric phụ: số học viên tự tìm workaround vs chờ TA |

### Insight sau validation

```text
1. Pain thật nằm ở 2 bước: đọc context rải rác (5 phút) + compose câu trả lời kỹ thuật (6-8 phút). Hai bước này chiếm ~65-70% thời gian mỗi ticket.
2. Khoảng 30% ticket là FAQ lặp lại — có thể xử lý bằng Rule/template mà không cần AI.
3. 70% ticket còn lại cần hiểu context code cụ thể của học viên — đây là phần AI có thể giúp nhất (tóm tắt context + tra cứu tài liệu + draft câu trả lời).
4. TA vẫn phải là người review và approve — không ai muốn bot tự trả lời trực tiếp cho học viên mà không qua TA.
```

---

## Bước 4.2 — Research giải pháp đã có

| Nguồn / tool / case | Link | Họ giải quyết phần nào? | Điểm mạnh | Khoảng trống / rủi ro | Bài học cho nhóm |
|---|---|---|---|---|---|
| **Discord AutoMod + Saved Replies** | https://support.discord.com/hc/en-us/articles/4421269296535 | FAQ lặp lại: TA dùng saved reply gắn sẵn | Nhanh cho câu hỏi cố định, không cần AI | Không xử lý được ticket cần hiểu context code cụ thể; câu trả lời cứng nhắc | Dùng Rule cho 30% ticket FAQ, không cần AI cho phần này |
| **Intercom Fin AI Agent** | https://www.intercom.com/fin | Trả lời tự động dựa trên knowledge base; escalate khi không chắc | RAG từ docs, tự reply hoặc draft cho agent | Thiết kế cho customer support SaaS, không native Discord; cần knowledge base chất lượng cao | Pattern tốt: AI draft → human review. Nhưng cần adapt cho Discord + technical context |
| **Stack Overflow for Teams + AI** | https://stackoverflow.co/teams/ | Knowledge base nội bộ, AI gợi ý câu trả lời từ Q&A cũ | Tái sử dụng kiến thức từ ticket cũ | Cần thời gian xây dựng knowledge base; không real-time trên Discord | Có thể dùng vector DB từ câu trả lời cũ làm source cho RAG |
| **n8n Discord Bot + OpenAI** | https://n8n.io/integrations/discord/ | Workflow automation: trigger từ Discord → xử lý → trả về Discord | Open-source, tuỳ biến cao, kết nối được nhiều nguồn (Notion, GitHub) | Cần self-host, cần setup vector DB riêng, cần maintain | Stack phù hợp nhất cho bài toán nhóm: n8n + Discord Bot + RAG + TA review |
| **Zendesk Answer Bot** | https://www.zendesk.com/service/ai/ | Auto-suggest articles từ knowledge base khi user hỏi | Mature product, có confidence scoring | Không free, không native Discord, thiết kế cho B2C support | Pattern confidence scoring tốt: chỉ gửi draft cho TA khi confidence thấp |

### Research takeaway

```text
1. Không cần build from scratch. Pattern đã được validate bởi Intercom, Zendesk: AI draft → human review → publish.
2. Cho bài toán Discord cụ thể, stack hợp lý nhất là: n8n/Zapier + Discord Bot API + Vector DB (từ Notion/GitHub tài liệu) + LLM (GPT-4o-mini) + TA review channel.
3. 30% ticket FAQ nên dùng Rule (saved replies/template) — không cần AI, tiết kiệm chi phí.
4. 70% ticket kỹ thuật cần Workflow: bot tóm tắt context → RAG tra cứu tài liệu → LLM draft → TA review → publish.
5. Không nên dùng Agent tự reply trực tiếp vì: (a) risk hallucination khi hướng dẫn code sai, (b) học viên mất tin tưởng nếu nhận câu trả lời sai, (c) TA mất kiểm soát chất lượng.
```

---

# Phase 5 — Workflow + Problem Statement

## Bước 5.1 — Current workflow bản nhóm

```text
CURRENT STATE — 7 bước, 18 phút/ticket, 50 ticket/ngày

[1 Học viên tạo ticket: 0']
→ [2 TA nhận notification: 0.5']
→ [3 TA đọc 10-20 tin nhắn rải rác để tìm context lỗi: 5']    <-- bottleneck #1
→ [4 TA mở tab tra cứu tài liệu/Notion/bài giảng: 4']
→ [5 TA gõ câu trả lời + giải thích hướng sửa lỗi: 6']        <-- bottleneck #2
→ [6 TA rà soát lại nội dung: 2']
→ [7 TA gửi phản hồi lên Discord: 0.5']
```

| Bước | Actor | Input | Output | Thời gian/tần suất | Ghi chú |
|---|---|---|---|---|---|
| 1 | Học viên | Mô tả lỗi/câu hỏi (thường rải rác 10-20 tin nhắn) | Ticket trên Discord | 0' (TA chưa tham gia) | Tin nhắn thiếu cấu trúc: thiếu log, thiếu screenshot, thiếu version |
| 2 | TA | Notification từ Discord | Biết có ticket mới | 0.5' | Phụ thuộc TA đang online hay không → gây delay |
| 3 | TA | 10-20 tin nhắn rải rác | Hiểu context: lỗi gì, bước nào, môi trường gì | 5'/ticket | **Bottleneck #1**: tin nhắn không có cấu trúc, phải scroll và đọc kỹ |
| 4 | TA | Từ khóa lỗi + kiến thức | Đoạn tài liệu/code mẫu liên quan | 4'/ticket | Phải mở nhiều tab: Notion, GitHub, slides bài giảng |
| 5 | TA | Context lỗi + tài liệu tham khảo | Câu trả lời kỹ thuật hoàn chỉnh | 6'/ticket | **Bottleneck #2**: phải tự compose, giải thích rõ cho học viên hiểu |
| 6 | TA | Bản nháp câu trả lời | Câu trả lời đã rà soát | 2'/ticket | Kiểm tra chính tả, link, code snippet |
| 7 | TA | Câu trả lời final | Phản hồi trên Discord | 0.5'/ticket | Copy-paste hoặc gõ trực tiếp |

Bottleneck chính:

```text
Hai bước chiếm ~65% thời gian mỗi ticket:
1. Đọc hiểu context từ 10-20 tin nhắn rải rác (5 phút) — vì học viên không dùng template, tin nhắn thiếu cấu trúc.
2. Compose câu trả lời kỹ thuật (6 phút) — vì mỗi ticket có context code riêng, không thể copy-paste từ câu cũ.

Ngoài ra, thời gian chờ (first response time 2.8h) là do TA không trực 24/7 và ticket queue dài.
```

## Bước 5.2 — Future workflow bản nhóm

```text
FUTURE STATE — 7 bước, ~4 phút effort TA/ticket (FAQ: 0.5 phút, Kỹ thuật: 4 phút)

[1 Học viên tạo ticket trên Discord: 0']
→ [2 Discord Bot trích xuất log & tóm tắt context tin nhắn: auto, <10s]  -- Rule + NLP
→ [3 Phân loại: FAQ hay Kỹ thuật?]
    ├── FAQ (30%): [Auto-reply từ saved template → Done]                  -- Rule
    └── Kỹ thuật (70%):
        → [4 AI RAG tra cứu tài liệu Notion/GitHub/bài giảng: auto, <15s]  -- Workflow step
        → [5 LLM soạn draft response từ context + tài liệu: auto, <20s]     -- Workflow step
        → [6 Bot gửi draft vào Admin Channel cho TA: auto]
        → [7 TA review: Approve / Edit / Reject: 3-4']                      -- Human boundary
        → [8 Bot publish phản hồi đã duyệt lên ticket: auto, <5s]

Fallback:
- AI draft tệ / TA Reject → TA tự viết câu trả lời (quay về workflow cũ cho ticket đó).
- AI không tìm được tài liệu phù hợp → Flag cho TA biết "không có source", TA tự xử lý.
- Ticket quá phức tạp / ngoài scope → Bot tag TA senior hoặc mentor trực tiếp.
```

### Before/after impact

| Metric | Trước | Sau kỳ vọng | Ghi chú |
|---|---:|---:|---|
| Số bước TA phải làm thủ công | 5/7 bước | 1/8 bước (chỉ review) | TA chỉ Approve/Edit/Reject |
| Thời gian TA/ticket (kỹ thuật) | 18 phút | ~4 phút (review + edit) | Giảm ~78% |
| Thời gian TA/ticket (FAQ) | 5-8 phút | ~0.5 phút (auto-reply) | Rule xử lý, TA không cần tham gia |
| Tổng thời gian/ngày cho 3 TAs | ~15 giờ | ~3-4 giờ | Giải phóng ~11 giờ công/ngày |
| First Response Time | 2.8 giờ | < 15 phút (FAQ: instant) | Bot phản hồi ngay, TA review sau |
| Bottleneck chính | Đọc context + gõ câu trả lời | TA review & edit draft | Bottleneck mới chấp nhận được vì là quality gate |
| Risk mới | Không có AI hallucination | Có hallucination risk | TA review trước khi publish; draft sai bị Reject |

## Bước 5.3 — Problem Statement v0

| Field | Nội dung |
|---|---|
| **Actor** | Trợ giảng (TA) trực kênh hỗ trợ kỹ thuật trên Discord cho chương trình đào tạo AI thực chiến (~50 học viên). |
| **Workflow** | Khi học viên tạo ticket, TA đọc 10-20 tin nhắn rải rác để hiểu context lỗi → tra cứu tài liệu hướng dẫn → compose câu trả lời kỹ thuật → rà soát → gửi phản hồi. |
| **Bottleneck** | Bước đọc context (5') và compose câu trả lời (6') chiếm ~65% thời gian mỗi ticket. Tin nhắn thiếu cấu trúc và mỗi ticket có context code khác nhau. |
| **Impact** | 50 ticket/ngày × 18 phút = ~15h công/ngày cho 3 TAs. Học viên chờ trung bình 2.8h. CSAT giảm xuống 3.8/5. |
| **Success Metric** | Giảm thời gian xử lý ticket từ 18 phút xuống dưới 4 phút; First Response Time < 15 phút; Draft Acceptance Rate > 85%; Re-open rate < 5%. |
| **Boundary** | AI không tự gửi câu trả lời trực tiếp cho ticket kỹ thuật (phải qua TA review). AI không bịa code/giải pháp ngoài tài liệu nguồn. AI không thay TA quyết định escalate. |

---

# Phase 6 — Rule / Workflow / Agent + Decision

## Bước 6.0 — Ma trận độ phù hợp với AI

Bài toán của nhóm nằm ở ô nào?

```text
Độ phức tạp CAO × Độ mơ hồ CAO → Nhưng nhóm chọn WORKFLOW, không chọn Agent.
```

Vì sao?

```text
1. Độ phức tạp cao: nhiều bước (trích xuất context → tra cứu → draft → review → publish), nhiều nguồn dữ liệu (Discord, Notion, GitHub).
2. Độ mơ hồ cao: mỗi ticket có context code riêng, câu trả lời khác nhau, không có đáp án cố định.
3. Tuy nhiên, workflow TUYẾN TÍNH và CỐ ĐỊNH — không cần AI tự lập kế hoạch hay tự quyết bước tiếp theo.
4. Các bước đã rõ ràng: extract → retrieve → draft → review → publish. Thứ tự không thay đổi.
5. Vì vậy Workflow (có AI hỗ trợ ở các bước cụ thể) là đủ. Chưa cần Agent.
```

## Bước 6.1 — So sánh Rule / Workflow / Agent

| Mức | Phương án cho bài toán nhóm | Khi nào đủ | Rủi ro | Chọn? |
|---|---|---|---|---|
| **Rule** | Saved replies / template cố định / Discord AutoMod macros / FAQ tĩnh | Đủ cho ~30% ticket FAQ lặp lại (vd: "cách setup env", "link tài liệu") | Không xử lý được 70% ticket cần hiểu context code cụ thể; câu trả lời cứng nhắc không khớp tình huống | **Chọn cho FAQ layer**, không chọn làm toàn bộ |
| **Workflow** | Bot extract context → AI RAG tra cứu → LLM draft → TA review → publish. Workflow tuyến tính, cố định, AI hỗ trợ ở các bước rõ ràng | Hợp vì thứ tự bước cố định, AI chỉ hỗ trợ extract/retrieve/draft, TA vẫn kiểm soát output cuối | Draft sai/thiếu → TA reject → phải tự viết (quay về workflow cũ cho ticket đó). Cần RAG quality cao | **Chọn cho phần chính** |
| **Agent** | Agent tự đọc ticket, tự quyết tra cứu nguồn nào, tự lập kế hoạch trả lời, có thể tự hỏi lại học viên, tự gửi mà không qua TA | Chỉ cần nếu workflow có nhiều nhánh động, nhiều tool, AI phải tự quyết next step | Quá rộng: hallucination khi hướng dẫn code sai → học viên mất tin tưởng; TA mất kiểm soát; permission phức tạp | **Không chọn** |

### Phân tích kỹ

- **Rule có giải được 70-80% case không?**
  → Không. Rule chỉ giải ~30% (FAQ lặp lại). 70% ticket cần hiểu context code cụ thể.

- **Workflow có đủ vì các bước khá rõ không?**
  → Có. Workflow tuyến tính: extract → retrieve → draft → review → publish. Thứ tự không thay đổi theo ticket.

- **Có thật sự cần Agent tự lập kế hoạch/gọi công cụ/đổi bước tiếp theo không?**
  → Không. AI không cần tự quyết "nên tra Notion hay GitHub trước" — tra cả hai rồi rank kết quả là đủ. AI không cần tự hỏi lại học viên — nếu thiếu info thì flag cho TA.

- **Nếu AI sai, ai phát hiện và sửa?**
  → TA review ở bước 7 (Approve/Edit/Reject). Đây là human-in-the-loop bắt buộc.

- **Có thể hạ mức từ Workflow về Rule không?**
  → Không cho phần kỹ thuật. Mỗi ticket có context code khác nhau, template cố định không đủ.

### Mức chọn

```text
Workflow (kết hợp Rule cho FAQ layer)
```

Vì sao chọn:

```text
- Workflow tuyến tính, cố định, không cần AI tự lập kế hoạch.
- AI chỉ hỗ trợ 3 bước cụ thể: extract context, retrieve tài liệu, draft response.
- TA vẫn review 100% ticket kỹ thuật trước khi publish.
- FAQ (30%) dùng Rule riêng, tiết kiệm chi phí LLM.
```

Vì sao không chọn mức đơn giản hơn (chỉ Rule):

```text
- 70% ticket kỹ thuật có context code riêng biệt, không thể dùng template cố định.
- Rule không thể đọc hiểu 10-20 tin nhắn rải rác để tóm tắt context.
- Rule không thể tra cứu tài liệu theo ngữ cảnh cụ thể.
```

Vì sao không chọn mức phức tạp hơn (Agent):

```text
- Workflow đã cố định, không cần AI tự quyết bước tiếp theo.
- Agent tự reply trực tiếp quá rủi ro: hallucination khi hướng dẫn code sai gây hậu quả lớn (học viên làm theo hướng dẫn sai).
- TA mất kiểm soát nếu Agent tự gửi.
- Agent cần nhiều permission phức tạp (đọc/ghi Discord, gọi API, quyết định escalate) → khó vận hành và maintain.
```

## Bước 6.2 — Problem Statement v1

| Field | Nội dung |
|---|---|
| **Actor** | Trợ giảng (TA) trực kênh hỗ trợ kỹ thuật trên Discord cho chương trình đào tạo AI (~50 học viên, 3 TAs trực xoay ca). Có thể mở rộng cho Lab Coach. |
| **Workflow** | Học viên tạo ticket → TA đọc 10-20 tin nhắn → tra cứu tài liệu → compose câu trả lời kỹ thuật → rà soát → gửi phản hồi. Tổng 7 bước, ~18 phút/ticket. |
| **Bottleneck** | Đọc context rải rác (5') + compose câu trả lời (6') chiếm ~65% thời gian. Tin nhắn thiếu cấu trúc, mỗi ticket có context code riêng. |
| **Impact** | 50 ticket/ngày × 18' = ~15h công/ngày cho 3 TAs. First response time 2.8h. CSAT 3.8/5. Học viên bị block trong lúc chờ. |
| **Success Metric** | Primary: thời gian TA/ticket từ 18' → <4'. Secondary 1: First Response Time 2.8h → <15'. Secondary 2: Draft Acceptance Rate >85%. Guardrail: Re-open rate <5%. |
| **Boundary** | AI không tự gửi câu trả lời kỹ thuật (phải qua TA review). AI không bịa code/giải pháp ngoài nguồn tài liệu. AI không thay TA quyết định escalate. FAQ auto-reply chỉ cho câu hỏi đã được verify. |
| **AI intervention point** | Sau khi học viên tạo ticket, trước bước TA đọc context. AI xen vào 3 bước: (1) trích xuất & tóm tắt context, (2) RAG tra cứu tài liệu, (3) draft response. TA nhận draft đã có context + source. |
| **Mức chọn** | Workflow (Rule cho FAQ layer + AI Workflow cho ticket kỹ thuật). Stack: n8n + Discord Bot API + Vector DB (Notion/GitHub) + GPT-4o-mini + TA Review Channel. |
| **Rủi ro & người thật kiểm tra** | Risk: AI hallucination trong code guidance, trích dẫn tài liệu sai, draft thiếu context quan trọng. Người thật: TA review 100% draft kỹ thuật trước publish. Nếu TA reject >15% → cần retune RAG/prompt. |

## Bước 6.3 — Final decision

| Câu hỏi | Yes / Not Yet / No | Ghi chú |
|---|---|---|
| Actor và workflow đã rõ chưa? | **Yes** | TA trực Discord, workflow 7 bước cố định, 50 ticket/ngày |
| Baseline và success metric đã đo được chưa? | **Yes** | Baseline: 18'/ticket, 2.8h FRT. Target: <4'/ticket, <15' FRT. Có thể đo từ Discord timestamp + stopwatch |
| Có data/input đủ dùng chưa? | **Yes** | Tài liệu trên Notion/GitHub có sẵn; ticket history trên Discord có sẵn; có thể build vector DB từ nguồn hiện tại |
| Nếu AI sai, hậu quả có chấp nhận được không? | **Yes** | TA review trước publish nên AI sai → TA reject → tự viết lại. Hậu quả: mất thời gian nhưng không gửi thông tin sai cho học viên |
| Có người review/owner vận hành không? | **Yes** | TA trực ca là reviewer. Lead TA hoặc Program Manager là owner vận hành |
| Có cách non-AI đơn giản hơn không? | **Partially** | Saved replies/template đủ cho 30% FAQ. Nhưng 70% ticket kỹ thuật cần AI để xử lý context đa dạng |

### Decision

```text
Go với scope nhỏ.
```

### Lý do

```text
- Problem rõ, workflow rõ, metric rõ, data có sẵn.
- Có non-AI layer (Rule cho FAQ) và AI layer (Workflow cho kỹ thuật).
- Human-in-the-loop rõ ràng: TA review trước publish.
- Risk kiểm soát được: AI sai → TA reject → quay về manual.
- Stack có thể build được trong thời gian hợp lý (n8n + Discord Bot + RAG).
```

### Nếu Go, pilot nhỏ nhất là:

```text
1. Chọn 10-15 ticket kỹ thuật gần nhất làm test set.
2. Build RAG từ 2-3 tài liệu cốt lõi (lab guide, troubleshooting doc, FAQ list).
3. Chạy workflow bán thủ công: paste context ticket vào prompt chuẩn → LLM draft → so sánh với câu trả lời thật của TA.
4. Đo: (a) bao nhiêu % draft TA chấp nhận được (target >85%), (b) thời gian review+edit vs tự viết.
5. Nếu acceptance rate <70% trong 2 tuần → retune prompt/RAG trước khi scale.
```

### Exit / rollback criteria

```text
- Draft Acceptance Rate < 70% sau 2 tuần → dừng, retune RAG + prompt.
- Re-open rate > 10% → AI draft thiếu chất lượng, giảm scope.
- TA phản hồi "edit draft lâu hơn tự viết" → dừng, review lại usefulness.
- Tổng chi phí LLM > giá trị thời gian tiết kiệm → không kinh tế, quay về template.
```

---

*Group Report — Day 02 Lab*
