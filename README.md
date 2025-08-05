<h1 align="center">
  <img style="vertical-align:middle" height="200"
  src="./docs/_static/imgs/logo.png">
</h1>
<p align="center">
  <i>Supercharge Your LLM Application Evaluations 🚀</i>
</p>

<p align="center">
    <a href="https://github.com/explodinggradients/ragas/releases">
        <img alt="GitHub release" src="https://img.shields.io/github/release/explodinggradients/ragas.svg">
    </a>
    <a href="https://www.python.org/">
            <img alt="Build" src="https://img.shields.io/badge/Made%20with-Python-1f425f.svg?color=purple">
    </a>
    <a href="https://github.com/explodinggradients/ragas/blob/master/LICENSE">
        <img alt="License" src="https://img.shields.io/github/license/explodinggradients/ragas.svg?color=green">
    </a>
    <a href="https://pypi.org/project/ragas/">
        <img alt="Open In Colab" src="https://img.shields.io/pypi/dm/ragas">
    </a>
    <a href="https://discord.gg/5djav8GGNZ">
        <img alt="discord-invite" src="https://img.shields.io/discord/1119637219561451644">
    </a>
    <a target="_blank" href="https://deepwiki.com/explodinggradients/ragas">
    <img 
      src="https://devin.ai/assets/deepwiki-badge.png" 
      alt="Ask DeepWiki.com" 
      height="20" 
    />
  </a>
</p>

<h4 align="center">
    <p>
        <a href="https://docs.ragas.io/">Documentation</a> |
        <a href="#fire-quickstart">Quick start</a> |
        <a href="https://discord.gg/5djav8GGNZ">Join Discord</a> |
        <a href="https://blog.ragas.io/">Blog</a> |
        <a href="https://newsletter.ragas.io/">NewsLetter</a> |
        <a href="https://www.ragas.io/careers">Careers</a>
    <p>
</h4>

Objective metrics, intelligent test generation, and data-driven insights for LLM apps

Ragas is your ultimate toolkit for evaluating and optimizing Large Language Model (LLM) applications. Say goodbye to time-consuming, subjective assessments and hello to data-driven, efficient evaluation workflows.
Don't have a test dataset ready? We also do production-aligned test set generation.

> [!NOTE]
> Need help setting up Evals for your AI application? We'd love to help! We are conducting Office Hours every week. You can sign up [here](https://cal.com/team/ragas/office-hours).

## Key Features

- 🎯 Objective Metrics: Evaluate your LLM applications with precision using both LLM-based and traditional metrics.
- 🧪 Test Data Generation: Automatically create comprehensive test datasets covering a wide range of scenarios.
- 🔗 Seamless Integrations: Works flawlessly with popular LLM frameworks like LangChain and major observability tools.
- 📊 Build feedback loops: Leverage production data to continually improve your LLM applications.

## :shield: Installation

Pypi: 

```bash
pip install ragas
```

Alternatively, from source:

```bash
pip install git+https://github.com/explodinggradients/ragas
```

## :fire: Quickstart

### Evaluate your LLM App

This is 5 main lines:

```python
from ragas import SingleTurnSample
from ragas.metrics import AspectCritic

test_data = {
    "user_input": "summarise given text\nThe company reported an 8% rise in Q3 2024, driven by strong performance in the Asian market. Sales in this region have significantly contributed to the overall growth. Analysts attribute this success to strategic marketing and product localization. The positive trend in the Asian market is expected to continue into the next quarter.",
    "response": "The company experienced an 8% increase in Q3 2024, largely due to effective marketing strategies and product adaptation, with expectations of continued growth in the coming quarter.",
}
evaluator_llm = LangchainLLMWrapper(ChatOpenAI(model="gpt-4o"))
metric = AspectCritic(name="summary_accuracy",llm=evaluator_llm, definition="Verify if the summary is accurate.")
await metric.single_turn_ascore(SingleTurnSample(**test_data))
```

Find the complete [Quickstart Guide](https://docs.ragas.io/en/latest/getstarted/evals)

## Want help in improving your AI application using evals?

In the past 2 years, we have seen and helped improve many AI applications using evals. 

We are compressing this knowledge into a product to replace vibe checks with eval loops so that you can focus on building great AI applications. 

If you want help with improving and scaling up your AI application using evals.


🔗 Book a [slot](https://bit.ly/3EBYq4J) or drop us a line: [founders@explodinggradients.com](mailto:founders@explodinggradients.com).


![](/docs/_static/ragas_app.gif)



## 🫂 Community

If you want to get more involved with Ragas, check out our [discord server](https://discord.gg/5qGUJ6mh7C). It's a fun community where we geek out about LLM, Retrieval, Production issues, and more.

## Contributors

```yml
+----------------------------------------------------------------------------+
|     +----------------------------------------------------------------+     |
|     | Developers: Those who built with `ragas`.                      |     |
|     | (You have `import ragas` somewhere in your project)            |     |
|     |     +----------------------------------------------------+     |     |
|     |     | Contributors: Those who make `ragas` better.       |     |     |
|     |     | (You make PR to this repo)                         |     |     |
|     |     +----------------------------------------------------+     |     |
|     +----------------------------------------------------------------+     |
+----------------------------------------------------------------------------+
```

We welcome contributions from the community! Whether it's bug fixes, feature additions, or documentation improvements, your input is valuable.

1. Fork the repository
2. Create your feature branch (git checkout -b feature/AmazingFeature)
3. Commit your changes (git commit -m 'Add some AmazingFeature')
4. Push to the branch (git push origin feature/AmazingFeature)
5. Open a Pull Request

## 🔍 Open Analytics
At Ragas, we believe in transparency. We collect minimal, anonymized usage data to improve our product and guide our development efforts.

✅ No personal or company-identifying information

✅ Open-source data collection [code](./ragas/src/ragas/_analytics.py)

✅ Publicly available aggregated [data](https://github.com/explodinggradients/ragas/issues/49)

To opt-out, set the `RAGAS_DO_NOT_TRACK` environment variable to `true`.

### Cite Us
```
@misc{ragas2024,
  author       = {ExplodingGradients},
  title        = {Ragas: Supercharge Your LLM Application Evaluations},
  year         = {2024},
  howpublished = {\url{https://github.com/explodinggradients/ragas}},
}
```


Ragas là gì?
Ragas là một bộ công cụ mã nguồn mở giúp bạn đánh giá và tối ưu các ứng dụng sử dụng mô hình ngôn ngữ lớn (LLM) như ChatGPT, GPT-4, v.v. Thay vì phải tự kiểm tra, đánh giá kết quả bằng tay (dễ chủ quan, tốn thời gian), Ragas cung cấp cách đánh giá khách quan, tự động, và dựa trên dữ liệu.

Mục đích chính
Đánh giá ứng dụng LLM một cách khoa học: Sử dụng các chỉ số (metrics) chuẩn xác, có thể tự động chấm điểm câu trả lời của AI.

Tạo dữ liệu kiểm thử tự động: Nếu bạn chưa có bộ dữ liệu kiểm thử (test set), Ragas có thể tự sinh ra bộ dữ liệu phù hợp với thực tế sản xuất.

Phân tích & cải tiến liên tục: Hỗ trợ kết nối với các framework LLM phổ biến như LangChain, và cho phép xây dựng quy trình phản hồi để ứng dụng của bạn ngày càng thông minh hơn.

Tính năng nổi bật
Đánh giá khách quan: Kết hợp cả chỉ số truyền thống và chỉ số dựa trên LLM.

Tự tạo bộ dữ liệu kiểm thử: Bao phủ đa dạng trường hợp sử dụng thực tế.

Tích hợp dễ dàng: Làm việc tốt với các công cụ LLM phổ biến như LangChain.

Phản hồi từ dữ liệu sản xuất: Cho phép sử dụng dữ liệu thực tế để liên tục cải tiến AI app.

Cài đặt Ragas như thế nào?
Bạn chỉ cần một lệnh duy nhất nếu dùng pip:

bash
Sao chép
Chỉnh sửa
pip install ragas
Hoặc, cài đặt trực tiếp từ mã nguồn GitHub:

bash
Sao chép
Chỉnh sửa
pip install git+https://github.com/explodinggradients/ragas
Cách sử dụng cơ bản (Quickstart)
Ví dụ, bạn muốn đánh giá khả năng tóm tắt văn bản của LLM. Dưới đây là đoạn code mẫu (Python):

python
Sao chép
Chỉnh sửa
from ragas import SingleTurnSample
from ragas.metrics import AspectCritic

test_data = {
    "user_input": "summarise given text\nThe company reported an 8% rise in Q3 2024, driven by strong performance in the Asian market...",
    "response": "The company experienced an 8% increase in Q3 2024, largely due to effective marketing strategies and product adaptation..."
}
evaluator_llm = LangchainLLMWrapper(ChatOpenAI(model="gpt-4o"))
metric = AspectCritic(name="summary_accuracy",llm=evaluator_llm, definition="Verify if the summary is accurate.")
await metric.single_turn_ascore(SingleTurnSample(**test_data))
Ragas sẽ trả về điểm số đánh giá (score) cho câu trả lời của AI, giúp bạn biết mức độ chính xác và chất lượng.

Tham gia cộng đồng & nhận hỗ trợ
Discord: Tham gia cộng đồng Ragas để hỏi đáp, chia sẻ kinh nghiệm về LLM, AI production, v.v.

Tài liệu: Xem tài liệu chi tiết tại đây

Blog & Newsletter: Có blog, bản tin cập nhật về LLM và các best practice.

Đóng góp vào dự án
Nếu muốn đóng góp code, sửa lỗi, bổ sung tài liệu... bạn chỉ cần:

Fork repo

Tạo branch mới cho tính năng/sửa lỗi của bạn

Commit và push lên GitHub

Mở pull request để xin được merge vào dự án chính

Lưu ý về quyền riêng tư
Ragas chỉ thu thập dữ liệu sử dụng ẩn danh để cải thiện sản phẩm, không lấy thông tin cá nhân. Bạn có thể tắt tính năng này bằng cách đặt biến môi trường RAGAS_DO_NOT_TRACK=true.

Tóm lại:
Ragas giúp bạn đánh giá chất lượng các ứng dụng AI (LLM) một cách tự động, khách quan, tiết kiệm thời gian và liên tục cải tiến dựa trên dữ liệu thực tế.

1. Đánh giá chất lượng trả lời của chatbot/AI assistant
Vấn đề:
Khi bạn xây dựng chatbot, trợ lý ảo, hoặc ứng dụng hỏi đáp dựa trên LLM, làm sao biết câu trả lời của AI có đúng ý người dùng, có chính xác, đầy đủ, logic… hay không?

Ứng dụng Ragas:

Tạo ra bộ dữ liệu kiểm thử gồm các câu hỏi và câu trả lời do AI sinh ra.

Ragas tự động chấm điểm các câu trả lời của AI dựa trên nhiều tiêu chí (độ chính xác, sự đầy đủ, độ logic, v.v.).

Nhờ đó, bạn biết được chỗ nào AI làm tốt/chưa tốt để cải thiện.

Ví dụ:

Đánh giá khả năng tóm tắt, dịch thuật, giải thích của AI qua các task mẫu.

Tự động kiểm tra chatbot nội bộ cho doanh nghiệp.

2. So sánh nhiều mô hình LLM hoặc nhiều phiên bản ứng dụng
Vấn đề:
Bạn muốn thử nhiều mô hình khác nhau (ví dụ: GPT-3.5, GPT-4, Claude, v.v.) hoặc nhiều phiên bản ứng dụng để xem cái nào tốt hơn, nhưng việc kiểm tra thủ công rất tốn thời gian và chủ quan.

Ứng dụng Ragas:

Đánh giá các mô hình/phiên bản khác nhau trên cùng một bộ test.

So sánh điểm số, phân tích ưu – nhược điểm dựa trên kết quả thực tế.

Giúp bạn chọn ra mô hình hoặc giải pháp tối ưu nhất.

3. Kiểm thử tự động liên tục (CI/CD cho AI apps)
Vấn đề:
Sau mỗi lần cập nhật code, muốn đảm bảo AI của bạn không “tụt chất lượng” hoặc gặp bug trong phần xử lý ngôn ngữ.

Ứng dụng Ragas:

Tích hợp vào pipeline CI/CD để mỗi lần update code, hệ thống sẽ tự động đánh giá chất lượng LLM (tương tự test tự động của backend/frontend).

Phát hiện sớm lỗi hoặc sự xuống cấp chất lượng, không cần kiểm tra thủ công từng câu trả lời.

4. Tạo bộ dữ liệu kiểm thử nếu chưa có sẵn
Vấn đề:
Nhiều dự án mới chưa có dữ liệu thực tế để kiểm thử, hoặc muốn bổ sung các tình huống đặc biệt/phức tạp.

Ứng dụng Ragas:

Tự động sinh ra bộ dữ liệu test phù hợp với mục đích sử dụng, bám sát thực tế vận hành của sản phẩm.

Giảm công sức tự tạo tay từng câu hỏi.

5. Phân tích, cải thiện chất lượng dịch vụ AI từ dữ liệu thực tế
Vấn đề:
Muốn dùng phản hồi từ người dùng thực tế để cải tiến AI.

Ứng dụng Ragas:

Kết nối với các hệ thống ghi nhận tương tác thật của người dùng (log, feedback) và tự động đánh giá lại, gợi ý điểm cải tiến.

Xây dựng “feedback loop” giúp AI càng dùng càng tốt hơn.

6. Báo cáo, trực quan hóa kết quả đánh giá
Vấn đề:
Cần báo cáo chất lượng AI cho sếp, khách hàng hoặc nội bộ team.

Ứng dụng Ragas:

Tổng hợp số liệu đánh giá, xuất ra báo cáo trực quan, dễ theo dõi.

Giúp minh bạch hóa quá trình phát triển AI.

Tóm lại:
Ragas giúp bạn biến việc kiểm thử và tối ưu hóa ứng dụng LLM/AI thành một quy trình tự động, khách quan, liên tục và dữ liệu hóa.
Nó đặc biệt hữu ích cho các team AI, data scientist, developer làm chatbot, search engine, QA automation, dịch thuật, phân tích dữ liệu, v.v.
