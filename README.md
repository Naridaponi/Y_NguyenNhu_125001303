
# NHẬT KÝ PROMPT ENGINEERING (VIBE CODING LOG)
- **Họ và tên: Nguyễn Như Ý**
- **MSSV: 125001303**
- **Tên đề tài Website: COSMOS - Explore Our Solar System**
- **Công cụ AI đã sử dụng: AntiGravity**
## 1. Yêu cầu ban đầu (System/Initial Prompt)

> *bạn là 1 chuyên gia về thiết kế web và làm animation. Hãy giúp tôi thiết kế 1 web tên là COSMOS. website có 4 chức năng chính:1. solar system: mặt trời và 8 hành tinh quay quanh quỹ đạo,
> 2. planet explore: nhấn vào một hành tinh để xem thông tin chi tiết.
> 3.space fact: hiển thị sự thật về vũ trụ
> 4.interactive controls: cho phép tạm dừng hoặc điều chỉnh tốc độ quay
> phong cách thiết kế:
> nền đen hoặc xanh đen
> các ngôi sao lấp lánh
> hành tinh có màu sắc và kích thước khác nhau
> chuyển động mượt mà
> chỉ sử dụng HTML và CSS. Không sử dụng javascipt
> 1. Chuẩn Semantic HTML5 (Tối thiểu 5 thành phần)
> Website phải sử dụng đúng ngữ nghĩa các thẻ HTML5:
> ● <header> (Chứa logo, navigation menu)
> ● <nav> (Thanh điều hướng)
> ● <main> (Khu vực nội dung chính)
> ● <section> hoặc <article> (Chia các khối nội dung rõ ràng)
> ● <footer> (Chân trang chứa thông tin liên hệ, copyright,...)
> 2. Kỹ thuật CSS & CSS Variables
> ● Sử dụng CSS Variables (:root { --primary-color: ...; }) để quản lý phối màu,

> font chữ và spacing nhất quán cho toàn bộ trang.
> ● Áp dụng Layout hiện đại: CSS Flexbox hoặc CSS Grid để căn chỉnh
> responsive cơ bản.
> 3. Tương tác & Hiệu ứng (Libraries)
> ● Tích hợp Animate.css: Áp dụng hiệu ứng động cho các phần tử chính (Text
> tiêu đề, Hero Section, Button CTA,...).
> ● Tích hợp AOS (Animate On Scroll): Tạo hiệu ứng xuất hiện cuộn trang
> sinh động cho các section nội dung.
> ● Hiệu ứng :hover, :focus tự viết bằng CSS cho nút bấm và các thẻ bài viết
> (cards).*
## 2. Quá trình tinh chỉnh & Giải quyết sự cố (Iteration Iterations)
### Lần 1: Dựng khung Semantic HTML & CSS Variable
- **Prompt đã dùng: ở phần HTML, bạn đang sử dụng quá nhiều <.div> hãy sửa nó thành sửa lại thành <.main> và <.section>**
- **Kết quả AI tạo ra:**
> Tôi đã tối ưu lại toàn bộ cấu trúc trong file index.htmltheo chuẩn Semantic HTML5, loại bỏ phần lớn các thẻ <div> lạm dụng và thay thế bằng <main> cùng <section>:
> Các điểm thay đổi chính:
> Thẻ <main id="main-content">:Bao trọn toàn bộ nội dung chính của trang web: Hero, Hệ Mặt Trời, Khám phá các hành tinh, Space Facts và khu vực cửa sổ chi tiết các hành tinh (Modals). Chuyển đổi thành <section> rõ ràng theo ngữ nghĩa: Hero Section: Chuyển .hero-content và .hero-scroll-indicator thành các <section>.
> Solar System Section: .controls-panel và .speed-controls $\rightarrow$ <section>. .solar-system-container $\rightarrow$ <section>.
>Planet Explore Section: .planet-grid $\rightarrow$ <section>.
>Bên trong mỗi thẻ hành tinh: .planet-card-inner, .planet-card-front, .planet-card-back $\rightarrow$ <section>.
>Space Facts Section: .facts-grid $\rightarrow$ <section>.
> Planet Detail Modals:
> Đưa toàn bộ vào khối <section class="planet-modals-section"> bên trong <main>.
>Mỗi modal $\rightarrow$ <section id="*-detail" class="planet-modal" role="dialog">.
> Lưới thông số .modal-stats-grid và từng mục .modal-stat $\rightarrow$ <section>.
> Footer:
> .footer-content, .footer-brand, .footer-bottom $\rightarrow$ <section>.
> Bảo toàn thiết kế và tính năng: Các class và ID được giữ nguyên vẹn nên giao diện, hiệu ứng tương tác, animation và thư viện AOS vẫn hoạt động hoàn hảo và mượt mà.
- **Nhận xét & Tinh chỉnh của SV: Trong quá trình xem file HTML, phát hiện AI đã sài nhiều thẻ <.div> hơn là <.main> và <.section>. Đã nhắc AI sửa lại một cách hợp lí.**
## Lần 2: Thêm hiệu ứng load trang
- **Prompt đã dùng: Tôi yêu cầu bạn, khi  vừa bấm vào trang web sẽ là hiệu ứng mở màn ví dụ như: một tàu vũ trụ bay ngang, có thanh loading**
- **Kết quả AI tạo ra:**
>1. Hiệu ứng mở màn (Intro Preloader): Tàu vũ trụ bay ngang màn hình: Thiết kế tàu vũ trụ SVG phong cách sci-fi với thân kim loại công nghệ cao, đuôi lửa phản lực plasma (plasma flame) rực cháy và vệt khói ánh sáng gradient (plasma trail) bay lướt từ góc dưới bên trái qua tâm màn hình lên góc trên bên phải. Hiệu ứng sao siêu không gian (Hyperdrive Warp Stars): Các vệt tia sao vụt qua với tốc độ cao tạo cảm giác tàu đang chuyển động trong vũ trụ.
>Bảng điều khiển HUD & Thanh Loading: Huy hiệu phi vụ COSMOS MISSION 2026.
>Tiêu đề phát sáng COSMOS kèm thông báo trạng thái ĐANG KHỞI TẠO TÀU KHÁM PHÁ & HỆ THỐNG VŨ TRỤ....
>Thanh tiến trình (Loading Bar): Tự động chạy mượt mà từ 0% đến 100% trong 2.1s với hào quang neon cyan rực rỡ và nhãn 100% READY.
>Có nút hỗ trợ "Bỏ qua mở đầu ↷" (thuần CSS) cho phép người dùng bấm vào để vào thẳng trang chính ngay lập tức nếu không muốn chờ.
>Chuyển cảnh mượt mà: Sau ~2.4s, toàn bộ màn hình giới thiệu sẽ tự động hòa tan (introFadeOut) và ẩn hoàn toàn (visibility: hidden; pointer-events: none;) để mở ra trang chính.
- **Nhận xét & Tinh chỉnh của SV: AI đã hoàn thành tốt, vượt mong đợi**
  
## 3. Đánh giá cá nhân về quá trình Vibe Coding
- AI đã giúp bạn tiết kiệm thời gian ở phần nào nhất?
> AI giúp tôi tiết kiệm thời gian code từng dòng, có thể giải quyết nhiều tác vụ trong vài phút
- Bài học rút ra khi đặt câu hỏi (Prompt) cho AI trong thiết kế web?
> Lưu ý xem còn bao nhiêu tokens, hết tokens là các dòng code + web bị lỗi khi đang chạy prompt, Đặt prompt đầy đủ nội dung yêu cầu, không chỉnh sửa 1 prompt liên tục
