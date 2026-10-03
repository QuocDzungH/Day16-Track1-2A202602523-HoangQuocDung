# Memo Teardown — ElevenLabs

**Họ tên:** Hoàng Quốc Dũng

**Mã sinh viên:** 2A202602523

**Ngày phân tích:** 03/10/2026

**Khoảng dự đoán:** 04/2027–10/2027

**Vì sao chọn sản phẩm này:** ElevenLabs lấy AI âm thanh làm năng lực cốt lõi, có lịch sử công khai đủ dài và các công việc người dùng cần hoàn thành khá rõ: sản xuất lời thoại, bản địa hóa nội dung và xử lý cuộc gọi hỗ trợ. Sản phẩm phù hợp để nghiên cứu cách một lợi thế về chất lượng model được chuyển thành giá trị trong quy trình làm việc.

**Phạm vi và cách đọc:** Memo tập trung vào giọng nói, dubbing và agent hội thoại. Thời điểm và tính năng là dữ kiện từ các nguồn được dẫn; nguyên lý, phân tích người dùng và dự đoán là suy luận do AI hỗ trợ, không phải tuyên bố về ý định nội bộ của công ty. Đây là nghiên cứu nguồn công khai, chưa có trải nghiệm dùng thử hoặc phỏng vấn người dùng. Danh sách nguồn và mốc ứng viên nằm trong [sources.md](sources.md).

## §1. Timeline các cập nhật lớn

| Thời điểm | Cập nhật | Context lúc đó | Nguyên lý |
|---|---|---|---|
| **M1 · 23/01/2023** | Ra mắt nền tảng Beta: text-to-speech, voice cloning và API. [Nguồn](https://elevenlabs.io/blog/elevenlabs-raises-2m-pre-seed-and-announces-ai-speech-platform-promising-to-revolutionize-audio-storytelling) | Công ty mới đưa nghiên cứu riêng ra thị trường. Bài ra mắt mô tả creator và publisher phải chọn giữa chi phí thu âm với chất lượng của TTS cũ. | **x10:** tạo cơ hội làm bản thu và sửa lời thoại nhanh hơn cách thuê/thu âm lại. Đây là giả thuyết về cải thiện cả workflow; nguồn không chứng minh mọi tác vụ đều nhanh hơn đúng 10 lần. |
| **M2 · 22/08/2023** | Kết thúc Beta, ra Eleven Multilingual v2 hỗ trợ 28 ngôn ngữ. [Nguồn](https://elevenlabs.io/blog/elevenlabs-comes-out-of-beta-and-releases-eleven-multilingual-v2-a-foundational-ai-speech-model-for-nearly-30-languages) | Các use case đã mở sang sách nói, game và nội dung truyền thông; sản phẩm cần phục vụ nhiều thị trường hơn. | **Định nghĩa “tốt”:** chất lượng phải gồm khả năng giữ đặc trưng giọng nói khi đổi ngôn ngữ. “Tốt” được xác định theo việc đưa nội dung đến người nghe mới, không chỉ một bản demo tiếng Anh. |
| **M3 · 10/10/2023** | Ra AI Dubbing, chuyển lời nói sang ngôn ngữ khác và giữ giọng người nói. [Nguồn](https://elevenlabs.io/blog/elevenlabs-launches-voice-translation-tool-to-break-down-language-barriers-for-content) | Năng lực tổng hợp đa ngôn ngữ đã có; việc dịch và làm lại bản thu vẫn là một quy trình riêng của creator, educator và công ty media. | **Vertical AI — AI Expert + Domain Expert:** đưa năng lực âm thanh vào công việc bản địa hóa có yêu cầu cụ thể về người nói và bản dịch. Đây là bước tiếp cận workflow chuyên môn, chưa đủ để kết luận đã có moat bền vững. |
| **M4 · 11/11/2024** | Công bố Conversational AI: xây agent với knowledge base, functions, triggers và lựa chọn LLM; cùng đợt có Workspaces nhiều chỗ ngồi. [Nguồn](https://elevenlabs.io/blog/introducing-conversational-ai-genfm-market-expansion-and-more) | ElevenLabs đã phục vụ nội dung được tạo trước; hội thoại trực tiếp cần kết nối giọng nói với thông tin và hành động. | **Wrapper/moat:** mở rộng từ tạo file âm thanh sang điều phối tương tác. Tích hợp công cụ và dữ liệu công việc có thể tạo lợi thế khó thay hơn một giao diện gọi TTS; mức độ lợi thế phụ thuộc triển khai thực tế. |
| **M5 · 06/10/2025** | Ra Agent Workflows: sơ đồ hội thoại, subagent chuyên trách và chuyển tiếp sang người thật. [Nguồn](https://elevenlabs.io/blog/introducing-agent-workflows) | Agent xử lý nghiệp vụ phức tạp cần quy tắc và quyền truy cập rõ. Trước đó, ngày 09/09/2025, công ty đã công bố [Tests](https://elevenlabs.io/blog/tests-for-elevenlabs-agents). | **Vòng lặp học:** biến luồng xử lý thành thứ có thể kiểm tra và sửa; dùng tình huống hội thoại làm test để phát hiện lỗi khi thay prompt/workflow. Đây là vòng lặp cải thiện ứng dụng của khách hàng, không phải bằng chứng dữ liệu tự động được dùng huấn luyện model. |
| **M6 · 09/04/2026** | Công bố hướng triển khai on-premise và on-device bên cạnh cloud/VPC. Bài ghi hai lựa chọn mới ở **early access**. [Nguồn](https://elevenlabs.io/blog/enterprise-voice-ai-deployed-locally) | Một số tổ chức cần giữ dữ liệu trong môi trường riêng; thiết bị như xe hoặc wearable cần chạy ngoại tuyến. | **Định nghĩa “tốt”:** đáp ứng môi trường triển khai trở thành điều kiện mua. Giọng hay vẫn chưa đủ nếu không thể chạy trong hạ tầng được phép sử dụng. Không suy diễn early access thành đã phổ biến rộng rãi. |
| **M7 · 30/06/2026** | Công bố Procedures cho ElevenAgents; SOP có thể chuyển thành hướng dẫn xử lý theo tác vụ. Bài cập nhật 31/08 ghi tính năng còn ở **Alpha**. [Nguồn](https://elevenlabs.io/blog/procedures) | Các việc như hoàn tiền, xử lý hóa đơn và troubleshooting đòi hỏi nhân viên nghiệp vụ kiểm soát cách agent hành động. | **Vertical AI — AI Expert + Domain Expert:** chuyên gia nghiệp vụ cung cấp quy trình, AI thực hiện trong phạm vi đó. SOP và tích hợp có thể tạo switching cost, nhưng tài liệu có thể xuất/chuyển nên chưa phải khóa chặt tuyệt đối. |
| **M8 · 28/09/2026** | Ra Eleven v4 và v4 Turbo, nhấn mạnh biểu cảm, giữ bản sắc giọng và biến thể cho tác vụ độ trễ thấp. [Nguồn](https://elevenlabs.io/blog/eleven-v4) | Công ty đồng thời phục vụ sáng tạo nội dung và hội thoại trực tiếp; hai việc có ưu tiên khác nhau về biểu cảm và tốc độ. | **Định nghĩa “tốt”:** tách lựa chọn theo JTBD. Người dựng nội dung cần biểu đạt phù hợp; agent cuộc gọi cần phản hồi kịp thời. Model mới phải cải thiện kết quả của từng việc, không chỉ có tên phiên bản cao hơn. |

**Vì sao chọn những mốc này:** Tám mốc thể hiện thay đổi ở công việc có thể hoàn thành, tệp khách hàng hoặc điều kiện triển khai, từ tạo giọng đến vận hành hội thoại. [Multilingual v1](https://elevenlabs.io/blog/eleven-multilingual-v1) là mốc có giá trị nhưng được loại để tránh lặp cùng bước mở rộng ngôn ngữ đã thể hiện rõ ở M2; [Tests](https://elevenlabs.io/blog/tests-for-elevenlabs-agents) được giữ làm context của M5. [Series B](https://elevenlabs.io/blog/series-b) bị loại với tư cách mốc gọi vốn; các tính năng công bố cùng đợt như Dubbing Studio và Voice Library marketplace vẫn là những ứng viên hợp lệ, nhưng nhường chỗ cho chuỗi quyết định về agent.

**Nhận định chính:** ElevenLabs phát triển hai hướng bổ sung: giúp tạo nội dung âm thanh và giúp doanh nghiệp hoàn thành công việc qua hội thoại. Năng lực model riêng tạo lợi thế ban đầu; sức bền của lợi thế về sau còn phụ thuộc tích hợp, kiểm thử và mức độ ăn sâu vào quy trình khách hàng.

## §2. Tệp user & JTBD

### So sánh hai tệp đại diện

| | Early adopters | Tệp hiện tại được tập trung phân tích |
|---|---|---|
| **Đặc điểm** | Creator YouTube độc lập hoặc nhóm nhỏ, có kịch bản và thường xuyên cần voiceover; trực tiếp chọn giọng, tạo bản thu và sửa nội dung. Đây là chân dung đại diện suy ra từ nhóm tester được công bố khi ra mắt. | Người phụ trách CX/AI Product và kỹ sư tích hợp tại doanh nghiệp tài chính có nhiều cuộc gọi đa ngôn ngữ; cần nối agent với dữ liệu khách hàng và bộ phận hỗ trợ. Không đại diện cho toàn bộ user ElevenLabs. |
| **JTBD chính** | “Khi đã có kịch bản, tôi muốn làm lời dẫn phù hợp và sửa nhanh để xuất bản video theo lịch với ngân sách nhóm nhỏ.” | “Khi khách gọi hỏi trạng thái thanh toán hoặc vấn đề tài khoản, tôi muốn giải quyết yêu cầu thông thường ngay và chuyển đúng người khi cần.” |
| **Trước đó làm bằng cách nào** | Tự thu âm, thuê người đọc hoặc dùng TTS cũ; chỉnh kịch bản có thể kéo theo thu và dựng lại. | Nhân viên trực tổng đài, menu IVR và phần mềm hỗ trợ; hoặc đội kỹ thuật tự ghép nhận dạng giọng nói, LLM, TTS và hệ thống giám sát. |
| **Tiêu chuẩn thành công** | Bản thu sử dụng được, ít lần sửa, chi phí và thời gian phù hợp lịch xuất bản. | Yêu cầu được giải quyết chính xác, độ trễ chấp nhận được, tuân thủ chính sách và chuyển tiếp trơn tru. |
| **Mốc liên quan** | M1 mở khả năng tạo lời dẫn; M2–M3 mở thêm công việc đa ngôn ngữ. | M4 mở agent; M5 làm rõ luồng xử lý; M6–M7 đáp ứng triển khai và nghiệp vụ. |

**Bằng chứng về tệp:** [Thông báo ra mắt](https://elevenlabs.io/blog/elevenlabs-raises-2m-pre-seed-and-announces-ai-speech-platform-promising-to-revolutionize-audio-storytelling) nêu tester gồm YouTube creator, publisher và developer. [Thread Reddit tháng 01/2023](https://www.reddit.com/r/singularity/comments/10muooy/im_blown_away/) cho thấy phản ứng sớm với chất lượng TTS, nhưng không đủ để xác định cơ cấu người dùng. Với tệp doanh nghiệp, [case Revolut](https://elevenlabs.io/blog/revolut) mô tả việc từ prototype tự xây sang nền tảng để triển khai voice support; [case Klarna](https://elevenlabs.io/blog/klarna) mô tả agent tuyến đầu và chuyển sang người thật. Đây là case do nhà cung cấp công bố, không phải đánh giá độc lập.

**Dịch chuyển tệp:** M4 là điểm mở rộng quan trọng: đầu ra chuyển từ bản thu sang tương tác có thể truy cập thông tin và gọi công cụ. M5–M7 giúp CX, kỹ sư và người quản lý nghiệp vụ cùng tham gia triển khai. Đây là mở rộng thêm tệp doanh nghiệp; creator vẫn là tệp đang được phục vụ, thể hiện qua [Ads Engine](https://elevenlabs.io/blog/introducing-ads-engine-in-elevencreative) dành cho công việc bản địa hóa quảng cáo.

### Switching cost và 4 forces

**Chiều chuyển đổi được xét:** từ cách làm cũ sang ElevenLabs; khi xét rời ElevenLabs, giải pháp mới là một nhà cung cấp thay thế.

| Lực | Creator | Doanh nghiệp vận hành voice agent |
|---|---|---|
| **Push — vấn đề của cách đang dùng** | Thu âm và sửa tốn công; TTS cũ có thể không đạt chất lượng mong muốn. | Cuộc gọi lặp lại làm tăng hàng đợi; tự xây hệ thống hội thoại cần nhiều công sức tích hợp. |
| **Pull — sức hút giải pháp mới** | Tạo bản thu từ kịch bản, giữ giọng và thêm phiên bản ngôn ngữ. | Hội thoại trực tiếp, truy cập dữ liệu theo ngữ cảnh và chuyển người thật; gắn với công việc hỗ trợ cụ thể. |
| **Habit — thói quen và quy trình đã có** | Ban đầu là quy trình dựng/thu cũ. Sau khi dùng, giọng quen thuộc của kênh và cách chỉnh audio có thể giữ creator ở lại. | Ban đầu là SOP và hệ thống tổng đài cũ. Sau triển khai, workflow, test và cách đội vận hành quản lý agent tạo quán tính ở lại. |
| **Anxiety — nỗi lo khi chuyển đổi** | Lo sai phát âm, lệch cảm xúc hoặc tốn nhiều lượt tạo lại. Khi đổi nhà cung cấp, lo mất tính nhất quán của giọng. | Lo lỗi nghiệp vụ, gián đoạn dịch vụ và không đạt yêu cầu dữ liệu. Khi đổi nhà cung cấp, phải kiểm định lại tích hợp và các tình huống xử lý. |

**Phản chứng cần giữ:** [Một thread phê bình Dubbing Studio năm 2024](https://www.reddit.com/r/ElevenLabs/comments/1fvyaw5/psa_do_not_trust_the_dubbing_studio/) phản ánh lỗi dịch, sắc thái và công sửa. Phản hồi này cho thấy JTBD là “có bản địa hóa dùng được”, vượt quá “tạo ra tiếng nói tự nhiên”. Đây là trải nghiệm cá nhân ở phiên bản cũ; không thể dùng để kết luận tỷ lệ lỗi của model năm 2026.

**Lực giữ mạnh nhất:** Với tệp doanh nghiệp được chọn, tôi đánh giá **anxiety khi thay hệ thống đang vận hành** mạnh nhất: chi phí kiểm định lại quy trình và rủi ro gián đoạn có thể lớn hơn chi phí đổi một API. Moat tiềm năng nằm ở công sức tích hợp và vận hành đã tích lũy; không có bằng chứng rằng dữ liệu khách hàng bị giữ độc quyền. Nếu cấu hình, test và tích hợp có thể chuyển sang đối thủ với chi phí thấp, switching cost giảm mạnh và chất lượng/giá lại quyết định lựa chọn. Với creator chỉ tạo clip ngắn, lực giữ có thể yếu hơn nhiều.

## §3. Ba dự đoán hướng đi (6–12 tháng tới)

**Dự đoán 1 — Mở rộng tính năng**
- **Dự đoán:** Đến 10/2027, ElevenAgents sẽ bổ sung khả năng quản lý phiên bản và kiểm thử hồi quy gắn trực tiếp với thay đổi SOP/Procedure, giúp đội nghiệp vụ duyệt thay đổi trước khi áp dụng.
- **Lập luận:** M5 đã làm rõ workflow và M7 đưa SOP vào agent; tệp CX ở §2 cần tránh lỗi khi cập nhật nghiệp vụ. Bước tiếp theo hợp lý là quản lý vòng đời thay đổi. Dự đoán nói về mức tích hợp và quản trị sâu hơn, vì [Tests](https://elevenlabs.io/blog/tests-for-elevenlabs-agents) đã tồn tại.

**Dự đoán 2 — Mở rộng segment**
- **Dự đoán:** Đến 10/2027, ElevenLabs sẽ đóng gói thêm giải pháp voice agent chuyên biệt cho đơn vị tài chính quy mô vừa, có mẫu quy trình và hướng dẫn triển khai cho yêu cầu thanh toán/tài khoản.
- **Lập luận:** M6–M7 xử lý yêu cầu môi trường và SOP; [Revolut](https://elevenlabs.io/blog/revolut) và [Klarna](https://elevenlabs.io/blog/klarna) là bằng chứng có use case ở tài chính. Tệp §2 cần giảm công tích hợp, nên tái sử dụng kinh nghiệm khách hàng lớn cho đơn vị nhỏ hơn là hướng hợp lý; không dự đoán “bắt đầu vào tài chính”, vì đã vào rồi.

**Dự đoán 3 — Thay đổi mô hình kiếm tiền**
- **Dự đoán:** Đến 10/2027, ElevenLabs sẽ bổ sung lựa chọn hợp đồng ElevenAgents có phần phí riêng cho triển khai, quản trị và bảo đảm dịch vụ, bên cạnh phí theo lượng sử dụng.
- **Lập luận:** M5–M7 tăng giá trị của vận hành và kiểm soát; tệp doanh nghiệp §2 mua khả năng duy trì dịch vụ. [Trang pricing](https://elevenlabs.io/pricing) đã có Enterprise tùy chỉnh và SLA, nên dự đoán là tách/đóng gói rõ hơn phần dịch vụ của Agents, không phải lần đầu có Enterprise hoặc bỏ hoàn toàn phí sử dụng.

**Tự tin nhất:** Dự đoán 1, vì nối trực tiếp workflow, test và SOP đã có. Giả định then chốt là khách hàng muốn quản lý thay đổi ngay trong ElevenAgents; nếu họ giữ việc này ở hệ thống nội bộ và ElevenLabs chỉ cung cấp API, lập luận đó yếu đi. Dự đoán 2 phụ thuộc khả năng chuẩn hóa nghiệp vụ; dự đoán 3 có độ tự tin thấp hơn vì nguồn công khai chưa chứng minh khách hàng muốn cách tính phí mới.

## §4. AI Log

| Việc | AI làm hay bạn làm? | Kiểm chứng/phán đoán lại thế nào? |
|---|---|---|
| Chọn sản phẩm | Người học chọn ElevenLabs. | AI kiểm tra có năng lực AI cốt lõi, lịch sử 6+ mốc và use case rõ qua nguồn công khai. |
| Tìm nguồn và gom mốc ứng viên | AI thực hiện tìm kiếm, mở blog, Product Hunt và Reddit. | AI đọc trang trực tiếp cho 8 mốc chính; nguồn mới phát hiện từ chỉ mục được ghi riêng trong sources.md. Người học chưa xác nhận đã tự mở nguồn. |
| Chọn 8 mốc và giải thích mốc loại | AI đề xuất. | AI lọc theo thay đổi công việc, segment và điều kiện triển khai; nêu mốc hợp lệ bị loại vì giới hạn dung lượng. Người học chưa tự đánh giá lại lựa chọn. |
| Revert nguyên lý | AI viết lập luận dựa trên khái niệm trong đề bài. | AI phân biệt suy luận với dữ kiện, không khẳng định x10 đã đo được hoặc dữ liệu hội thoại tự động huấn luyện model. Chưa có slide lý thuyết đầy đủ để đối chiếu cách giảng từng framework. |
| Tệp user, JTBD và 4 forces | AI tổng hợp và xây chân dung đại diện. | AI đối chiếu bài ra mắt, case khách hàng và phản hồi tiêu cực; không xem một thread là đại diện toàn bộ user. Chưa phỏng vấn hoặc tự dùng thử. |
| Ba dự đoán | AI đề xuất và viết lý do. | AI nối mỗi dự đoán với mốc cụ thể và tệp user; phân biệt khả năng đã có với phần dự đoán bổ sung. Chưa có xác nhận độc lập về roadmap nội bộ. |
| Viết và rà soát memo | AI soạn toàn bộ bản này. | AI kiểm tra đủ 4 phần, 8 mốc có link, 3 dự đoán và AI log. Họ tên/MSV lấy từ tên workspace; người học cần xác nhận thông tin và đọc lại lập luận trước khi nộp. |

**Ranh giới trách nhiệm:** AI hỗ trợ nhiều nhất ở tìm nguồn, diễn giải nguyên lý và đưa dự đoán. Bản này chưa ghi nhận việc người học đã tự kiểm chứng; chỉ bổ sung điều đó sau khi thực sự thực hiện. Trước khi nộp, người học cần tự giải thích được vì sao M4 mở thêm tệp doanh nghiệp, tại sao dữ liệu/tích hợp chưa đương nhiên là moat, và điều kiện nào làm ba dự đoán sai.
