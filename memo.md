# Memo Teardown — ElevenLabs

**Họ tên:** Hoàng Quốc Dũng

**Vì sao chọn sản phẩm này:** ElevenLabs lấy AI âm thanh làm năng lực cốt lõi, có lịch sử công khai đủ dài và các công việc người dùng cần hoàn thành khá rõ: sản xuất lời thoại, bản địa hóa nội dung và xử lý cuộc gọi hỗ trợ. Sản phẩm phù hợp để nghiên cứu cách một lợi thế về chất lượng model được chuyển thành giá trị trong quy trình làm việc.

**§1. Timeline các cập nhật lớn**

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

**§2. Tệp user & JTBD**

| | Early adopters | Tệp hiện tại |
|---|---|---|
| **Đặc điểm** | Creator YouTube độc lập hoặc nhóm nhỏ, có kịch bản và thường xuyên cần voiceover; trực tiếp chọn giọng, tạo bản thu và sửa nội dung. Chân dung đại diện dựa trên nhóm tester trong [bài ra mắt](https://elevenlabs.io/blog/elevenlabs-raises-2m-pre-seed-and-announces-ai-speech-platform-promising-to-revolutionize-audio-storytelling). | Người phụ trách CX/AI Product và kỹ sư tích hợp tại doanh nghiệp tài chính có nhiều cuộc gọi đa ngôn ngữ; cần nối agent với dữ liệu khách hàng và bộ phận hỗ trợ. Tệp đại diện được phân tích qua [Revolut](https://elevenlabs.io/blog/revolut) và [Klarna](https://elevenlabs.io/blog/klarna), không đại diện toàn bộ user ElevenLabs. |
| **JTBD chính** | “Khi đã có kịch bản, tôi muốn làm lời dẫn phù hợp và sửa nhanh để xuất bản video theo lịch với ngân sách nhóm nhỏ.” | “Khi khách gọi hỏi trạng thái thanh toán hoặc vấn đề tài khoản, tôi muốn giải quyết yêu cầu thông thường ngay và chuyển đúng người khi cần.” |
| **Trước đó làm bằng cách nào** | Tự thu âm, thuê người đọc hoặc dùng TTS cũ; chỉnh kịch bản có thể kéo theo thu và dựng lại. | Nhân viên trực tổng đài, menu IVR và phần mềm hỗ trợ; hoặc đội kỹ thuật tự ghép nhận dạng giọng nói, LLM, TTS và hệ thống giám sát. |

**Dịch chuyển tệp:** M4 là điểm mở rộng quan trọng: đầu ra chuyển từ bản thu sang tương tác có thể truy cập thông tin và gọi công cụ. M5–M7 giúp CX, kỹ sư và người quản lý nghiệp vụ cùng tham gia triển khai. Đây là mở rộng thêm tệp doanh nghiệp; creator vẫn là tệp đang được phục vụ, thể hiện qua [Ads Engine](https://elevenlabs.io/blog/introducing-ads-engine-in-elevencreative) dành cho công việc bản địa hóa quảng cáo.

**Switching cost (map 4 forces):** Xét việc chuyển từ cách làm cũ sang ElevenLabs; sau khi đã sử dụng, thói quen và nỗi lo thay đổi hệ thống trở thành lực giữ người dùng ở lại.

| Lực | Creator | Doanh nghiệp vận hành voice agent |
|---|---|---|
| **Push — vấn đề của cách đang dùng** | Thu âm và sửa tốn công; TTS cũ có thể không đạt chất lượng mong muốn. | Cuộc gọi lặp lại làm tăng hàng đợi; tự xây hệ thống hội thoại cần nhiều công sức tích hợp. |
| **Pull — sức hút giải pháp mới** | Tạo bản thu từ kịch bản, giữ giọng và thêm phiên bản ngôn ngữ. | Hội thoại trực tiếp, truy cập dữ liệu theo ngữ cảnh và chuyển người thật; gắn với công việc hỗ trợ cụ thể. |
| **Habit — thói quen và quy trình đã có** | Ban đầu là quy trình dựng/thu cũ. Sau khi dùng, giọng quen thuộc của kênh và cách chỉnh audio có thể giữ creator ở lại. | Ban đầu là SOP và hệ thống tổng đài cũ. Sau triển khai, workflow, test và cách đội vận hành quản lý agent tạo quán tính ở lại. |
| **Anxiety — nỗi lo khi chuyển đổi** | Lo sai phát âm, lệch cảm xúc hoặc tốn nhiều lượt tạo lại. Khi đổi nhà cung cấp, lo mất tính nhất quán của giọng. | Lo lỗi nghiệp vụ, gián đoạn dịch vụ và không đạt yêu cầu dữ liệu. Khi đổi nhà cung cấp, phải kiểm định lại tích hợp và các tình huống xử lý. |

Với tệp doanh nghiệp được chọn, tôi đánh giá **anxiety khi thay hệ thống đang vận hành** là lực giữ mạnh nhất: chi phí kiểm định lại quy trình và rủi ro gián đoạn có thể lớn hơn chi phí đổi một API. Nếu cấu hình, test và tích hợp có thể chuyển sang đối thủ với chi phí thấp, switching cost giảm mạnh và chất lượng/giá lại quyết định lựa chọn. Với creator, chất lượng bản dịch và công sửa vẫn có thể kéo họ đi: [phản hồi tiêu cực về Dubbing Studio năm 2024](https://www.reddit.com/r/ElevenLabs/comments/1fvyaw5/psa_do_not_trust_the_dubbing_studio/) cho thấy giọng tự nhiên chưa đủ để có bản địa hóa dùng được; phản hồi cũ này không phải kiểm định model năm 2026.

**§3. Ba dự đoán hướng đi (6–12 tháng tới)**

**Dự đoán 1** *(loại: mở rộng tính năng)*

- **Dự đoán:** Đến 10/2027, ElevenAgents sẽ bổ sung khả năng quản lý phiên bản và kiểm thử hồi quy gắn trực tiếp với thay đổi SOP/Procedure, giúp đội nghiệp vụ duyệt thay đổi trước khi áp dụng.
- **Lập luận:** M5 đã làm rõ workflow và M7 đưa SOP vào agent; tệp CX ở §2 cần tránh lỗi khi cập nhật nghiệp vụ. Bước tiếp theo hợp lý là quản lý vòng đời thay đổi. Dự đoán nói về mức tích hợp và quản trị sâu hơn, vì [Tests](https://elevenlabs.io/blog/tests-for-elevenlabs-agents) đã tồn tại.

**Dự đoán 2** *(loại: mở rộng segment)*

- **Dự đoán:** Đến 10/2027, ElevenLabs sẽ đóng gói thêm giải pháp voice agent chuyên biệt cho đơn vị tài chính quy mô vừa, có mẫu quy trình và hướng dẫn triển khai cho yêu cầu thanh toán/tài khoản.
- **Lập luận:** M6–M7 xử lý yêu cầu môi trường và SOP; [Revolut](https://elevenlabs.io/blog/revolut) và [Klarna](https://elevenlabs.io/blog/klarna) là bằng chứng có use case ở tài chính. Tệp §2 cần giảm công tích hợp, nên tái sử dụng kinh nghiệm khách hàng lớn cho đơn vị nhỏ hơn là hướng hợp lý; không dự đoán “bắt đầu vào tài chính”, vì đã vào rồi.

**Dự đoán 3** *(loại: mô hình kiếm tiền)*

- **Dự đoán:** Đến 10/2027, ElevenLabs sẽ bổ sung lựa chọn hợp đồng ElevenAgents có phần phí riêng cho triển khai, quản trị và bảo đảm dịch vụ, bên cạnh phí theo lượng sử dụng.
- **Lập luận:** M5–M7 tăng giá trị của vận hành và kiểm soát; tệp doanh nghiệp §2 mua khả năng duy trì dịch vụ. [Trang pricing](https://elevenlabs.io/pricing) đã có Enterprise tùy chỉnh và SLA, nên dự đoán là tách/đóng gói rõ hơn phần dịch vụ của Agents, không phải lần đầu có Enterprise hoặc bỏ hoàn toàn phí sử dụng.

**§4. AI Log**

| Việc | AI làm hay bạn làm? | Bạn kiểm chứng/phán đoán lại thế nào? |
|---|---|---|
| Chọn sản phẩm | Tôi | Tôi chọn ElevenLabs và xác nhận sản phẩm đáp ứng ba tiêu chí: AI là năng lực cốt lõi, có đủ mốc công khai và use case rõ. |
| Tìm và gom nguồn | AI | Tôi yêu cầu ưu tiên nguồn uy tín, sau đó kiểm chứng lại ngày và nội dung tại các link đã liệt kê. Blog và thông báo chính thức là nguồn chính; Product Hunt và Reddit chỉ bổ sung lịch sử launch và phản hồi. |
| Tổng hợp timeline ban đầu | AI | Tôi đối chiếu bản tổng hợp với nguồn gốc, kiểm tra thời điểm và phân biệt công bố, Alpha, early access với phát hành rộng rãi. |
| Chọn 8 mốc và loại mốc | AI gợi ý, tôi chọn và chốt | Tôi xem xét tác động đến công việc, tệp user và điều kiện triển khai; chốt 8 mốc, loại mốc trùng ý và mốc gọi vốn không thể hiện quyết định sản phẩm. |
| Revert nguyên lý | Tôi làm trước, AI góp ý để làm rõ thêm | Tôi tự đối chiếu từng mốc với các nguyên lý đã học và viết phần diễn giải, sau đó nhờ AI góp ý để làm rõ lập luận. Tôi xem xét các góp ý và chốt cách diễn giải; phân biệt x10 như định hướng cải thiện với số đo đã được chứng minh. |
| Phân tích tệp user và JTBD | AI tổng hợp, tôi chọn tệp và chốt JTBD | Tôi đối chiếu bài ra mắt với case Revolut/Klarna, chốt hai tệp đại diện và kiểm tra JTBD được viết theo việc cần hoàn thành thay vì tính năng. |
| Phân tích 4 forces | Tôi | Tôi tự phân tích Push, Pull, Habit và Anxiety, xác định chiều chuyển đổi và chọn nỗi lo thay hệ thống đang vận hành là lực giữ mạnh nhất ở tệp doanh nghiệp; đối chiếu phản hồi tiêu cực để xem lực nào có thể kéo user rời đi. |
| Ba dự đoán hướng đi | Tôi đề xuất ba hướng, AI phân tích thử | Tôi đưa ra ba hướng dự đoán ban đầu rồi nhờ AI phân tích thử lập luận và tính hợp lý của từng hướng. Tôi xem xét phần phân tích, đối chiếu với timeline và tệp user, chỉnh những điểm chung chung hoặc đã xảy ra, rồi chốt ba dự đoán trong bài. |
| Soạn và hoàn thiện memo | AI soạn bản nháp, tôi duyệt nội dung cuối | Tôi rà soát nguồn và lập luận, yêu cầu sửa về đúng template, xác nhận nội dung và chốt bản cuối. |
