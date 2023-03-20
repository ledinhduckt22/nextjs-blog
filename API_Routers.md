# Creating API Routes

API Routes cho phép tạo 1 API endpoint trong Next.js app. Thực hiện bằng việc tạo hàm trong thư mục pages/api

# Do Not Fetch an API Route from getStaticProps or getStaticPaths
Không nên fetch API từ getStaticProps or getStaticPaths. Thay vào đó, **viết 1 hàm server-side** trực tiếp trong getStaticProps or getStaticPaths (or call a helper function).

### Lý do:
- getStaticProps and getStaticPaths chỉ chạy trên server-side, không chạy trên client-side. Thêm nữa, những hàm này sẽ không được gộp trong JS bundle của trình duyệt.