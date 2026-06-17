🌍 Dự án Website Giới thiệu và Đặt Tour Du lịch 

Dự án xây dựng một ứng dụng trang đơn (Single Page Application - SPA) hiện đại, hỗ trợ doanh nghiệp lữ hành số hóa quy trình vận hành và cung cấp trải nghiệm đặt tour trực tuyến 24/7 mượt mà cho khách hàng. 

🚀 Giới thiệu dự án

Trong bối cảnh chuyển đổi số ngành du lịch, hệ thống này được phát triển nhằm khắc phục các nhược điểm của phương thức kinh doanh truyền thống và các nền tảng CMS/OTA (phí hoa hồng cao, khó tùy biến, hiệu suất kém). Bằng việc sử dụng framework ReactJS, ứng dụng mang lại tốc độ tải trang nhanh chóng, điều hướng tức thì mà không cần tải lại toàn bộ trang, tối ưu trải nghiệm UI/UX cho du khách. 

✨ Tính năng cốt lõi

🧑 Khách hàng (User / Guest)

•	Xác thực & Tài khoản: Đăng ký tài khoản mới, Đăng nhập hệ thống bảo mật bằng JWT. 

•	Tìm kiếm thông minh: Bộ lọc tour theo địa điểm (City), khoảng cách tối đa (Distance) và số lượng người tham gia tối đa (Max Group Size). 

•	Xem chi tiết Tour: Trình bày trực quan lịch trình, mô tả, hình ảnh chất lượng cao, giá cả và form đặt chỗ trực tiếp. 

•	Đặt tour trực tuyến: Quy trình đặt chỗ tinh gọn qua vài bước điền thông tin (Họ tên, SĐT, Ngày khởi hành, Số khách). 

•	Đánh giá & Phản hồi (Review): Khách hàng sau khi trải nghiệm có thể gửi nhận xét và chấm điểm xếp hạng theo số sao (Rating) để cập nhật real-time lên hệ thống. 

👨💼 Quản trị viên (Admin)

(Lưu ý: Hệ thống backend đã hỗ trợ phân quyền, các chức năng này được quản lý và thực thi thông qua các endpoint API) 

•	Quản lý Tour: Thêm mới, cập nhật thông tin và xóa tour khỏi hệ thống. 

•	Quản lý người dùng: Xem danh sách toàn bộ tài khoản người dùng đã đăng ký. 

•	Quản lý đặt chỗ: Theo dõi tập trung danh sách tất cả các lượt đặt tour từ khách hàng. 

💻 Công nghệ sử dụng

Hệ thống được phát triển dựa trên kiến trúc MERN Stack mạnh mẽ: 

Thành phần	Công nghệ	Vai trò trong dự án

Frontend	ReactJS, React Router, Context API	Xây dựng giao diện ứng dụng trang đơn (SPA), quản lý trạng thái toàn cục (Auth) và kết nối với Backend API. 

Backend	Node.js, Express.js	Xây dựng RESTful API, xử lý logic nghiệp vụ, mã hóa mật khẩu và phân quyền với Middleware. 

Database	MongoDB, Mongoose	Cơ sở dữ liệu NoSQL lưu trữ tài liệu linh hoạt (BSON/JSON) cho các đối tượng Tour, User, Booking, Review. 

📐 Kiến trúc hệ thống

Mô hình dữ liệu (Database Schema)

Hệ thống quản lý 4 đối tượng trừu tượng chính kết nối với nhau: 

1.	User: username, email, password (đã hash), photo, role (user/admin). 

2.	Tour: title, city, address, distance, photo, desc, price, maxGroupSize, reviews (mảng ID liên kết), featured. 

3.	Booking: userId, userEmail, tourName, fullName, guestSize, phone, bookAt, totalAmount. 

4.	Review: productId (ID Tour được đánh giá), username, reviewText, rating. 

📂 Cấu trúc mã nguồn

Dựa trên cấu trúc thư mục thực tế trong kho lưu trữ (hình ảnh image_a2ea05.png), mã nguồn của dự án được tổ chức như sau:

Plaintext

mernstack-tour-management_Do_an_co_so/

├── .vscode/

└── quản lý tour du lịch/          # Thư mục chứa mã nguồn chính của ứng dụng

    ├── backend/
    
    │   ├── config/             # Cấu hình kết nối cơ sở dữ liệu MongoDB
    
    │   ├── controllers/        # Xử lý logic nghiệp vụ (auth, tour, booking, review)
    
    │   ├── models/             # Định nghĩa Schema (User.js, Tour.js, Booking.js, Review.js)
    
    │   ├── routes/             # Định tuyến API các endpoint
    
    │   ├── utils/              # Middleware bảo mật & Xác thực token (verifyToken.js)
    
    │   └── server.js           # File chạy chính của máy chủ Backend
    
    │
    
    └── frontend/
    
        ├── public/
        
        └── src/
        
            ├── assets/         # Hình ảnh, icons và thư viện hình ảnh giao diện
            
            ├── components/     # Các thành phần giao diện tái sử dụng (Header, Footer, TourCard)
            
            ├── context/        # Quản lý trạng thái đăng nhập và quyền truy cập (AuthContext.js)
            
            ├── hooks/          # Custom hook fetch dữ liệu tự động từ API (useFetch.js)
            
            ├── pages/          # Các trang giao diện (Home, Tours, TourDetails, Login, Register, SearchResultList, ThankYou)          
            
            └── shared/         # Các thanh công cụ dùng chung toàn hệ thống (SearchBar.jsx)

🛠️ Hướng dẫn cài đặt và khởi chạy

Yêu cầu tiên quyết

•	Máy tính đã cài đặt Node.js (Khuyến nghị phiên bản 16.x hoặc mới hơn).

•	Máy tính đã cài đặt công cụ Git.

•	Cần chuẩn bị trước một chuỗi kết nối (Connection String) cơ sở dữ liệu MongoDB Atlas trực tuyến.

Các bước triển khai chi tiết

Bước 1: Tải mã nguồn về máy địa phương bằng Git

Mở Terminal / Command Prompt trên máy tính của bạn và chạy lệnh sau:

Bash

# Clone dự án từ repository GitHub

git clone https://github.com/Thangit1/mernstack-tour-management_Do_an_co_so.git

# Di chuyển vào thư mục kho lưu trữ vừa clone thành công

cd mernstack-tour-management_Do_an_co_so

Bước 2: Di chuyển vào thư mục chứa code

Theo cấu trúc lưu trữ hiển thị trên GitHub (hình ảnh image_a2ea05.png), toàn bộ mã nguồn nằm bên trong thư mục quản lý tour du lịch. Bạn cần chuyển hẳn vào 

thư mục này:

Bash

cd "quản lý tour du lịch"

Bước 3: Cài đặt và khởi chạy phía Backend (Máy chủ)

Bash

# Di chuyển vào thư mục backend

cd backend

# Cài đặt toàn bộ các thư viện phụ thuộc (Express, Mongoose, JWT, bcryptjs,...)

npm install

Tạo một file có tên là .env đặt trực tiếp tại thư mục /backend và điền cấu hình môi trường như sau:

Đoạn mã

PORT = 4000

MONGO_URI = <Thay_bằng_chuỗi_kết_nối_MongoDB_Atlas_của_bạn>

JWT_SECRET_KEY = <Điền_mã_bí_mật_tự_chọn_để_mã_hóa_chuỗi_token_JWT>

Khởi chạy server backend:

Bash

npm start

# Nếu có nodemon cài sẵn, bạn có thể chạy chế độ dev: npm run dev

Khi hiển thị thông báo kết nối thành công, Server sẽ hoạt động ổn định tại cổng: http://localhost:4000

Bước 4: Cài đặt và khởi chạy phía Frontend (Giao diện người dùng)

Mở một cửa sổ Terminal mới (song song với cửa sổ Backend đang chạy) và thực hiện:

Bash

# Di chuyển vào thư mục chứa code giao diện

cd "quản lý tour du lịch/frontend"

# Cài đặt các gói thư viện React và UI components

npm install

# Khởi chạy ứng dụng Client

npm start

Hệ thống sẽ tự động mở trình duyệt và chạy giao diện trang web tại địa chỉ: http://localhost:3000. 

🔮 Kế hoạch phát triển tương lai

Nhằm khắc phục hoàn toàn những điểm còn thiếu sót của phiên bản hiện tại, dự án định hướng bổ sung và phát triển các tính năng nâng cao sau: 

•	Hoàn thiện Admin Dashboard: Xây dựng màn hình quản trị trực quan (UI) hoàn chỉnh cho Admin để theo dõi biểu đồ thống kê doanh thu, quản lý danh sách 
đặt tour và cập nhật tour trực tiếp trên web thay vì gọi qua API thuần. 

•	Tích hợp cổng thanh toán trực tuyến: Kết nối với các bên thứ ba như VNPAY, MoMo, hoặc Stripe giúp khách hàng có thể trả phí booking trực tuyến ngay lập 
tức. 

•	Tối ưu hóa hiển thị Responsive: Thiết kế lại giao diện theo chuẩn "Mobile-first" để ứng dụng hiển thị mượt mà, tối ưu nút bấm trên màn hình điện thoại 
di động và máy tính bảng. 

•	Nâng cao tính bảo mật: Triển khai thêm các phương thức xác thực mạnh mẽ hơn như xác thực hai yếu tố (2FA) và bổ sung tính năng "Quên mật khẩu/Đặt lại mật khẩu" qua Email. 

•	Hệ thống theo dõi chuyến đi & Đánh giá cao cấp: Cho phép người dùng lưu lại lịch sử chuyến đi, gửi đánh giá (Review) có kèm hình ảnh/video thực tế và 
kích hoạt hệ thống thông báo email tự động khi trạng thái booking thay đổi.

