# WTM Sport E-commerce Platform

## 📋 Giới thiệu tổng quan

WTM Sport là một nền tảng thương mại điện tử chuyên về các sản phẩm thể thao, bao gồm giày, quần áo và phụ kiện thể thao từ các thương hiệu nổi tiếng như Nike, Adidas, Puma. Hệ thống được xây dựng với kiến trúc monolithic, bao gồm một backend API tập trung và frontend React application.

## 🏗️ Kiến trúc hệ thống

```
wtmsport-nodejs/
├── SportEcommerceServices/    # Backend API Services
├── WebSport/                  # Frontend React Application
└── docker-compose.yml         # Container Orchestration
```

## 🔧 Công nghệ sử dụng

### Backend (SportEcommerceServices)
- **Runtime**: Node.js với Express.js
- **Database**: MongoDB với Mongoose ODM
- **Authentication**: JWT (JSON Web Tokens)
- **Cache**: Redis Cloud
- **File Storage**: Cloudinary
- **Payment**: PayOS Integration
- **Email**: NodeMailer với Gmail
- **AI**: OpenAI API cho chatbot
- **Documentation**: Swagger UI
- **Testing**: Jest với Supertest

### Frontend (WebSport)
- **Framework**: React 19 với Vite
- **UI Library**: Ant Design, Material Tailwind
- **State Management**: Redux
- **Routing**: React Router DOM
- **Styling**: Tailwind CSS, SASS
- **3D Graphics**: Three.js với React Three Fiber
- **Charts**: ApexCharts
- **Authentication**: Firebase
- **Icons**: React Icons, Heroicons

## 📁 Cấu trúc dự án chi tiết

### SportEcommerceServices (Backend)

```
SportEcommerceServices/
├── src/
│   ├── chronos/           # Scheduled Jobs
│   │   └── OrderChecker.js    # Kiểm tra đơn hàng định kỳ
│   ├── config/            # Cấu hình hệ thống
│   │   ├── db.js             # Kết nối MongoDB
│   │   ├── cloudinary.js     # Cấu hình Cloudinary
│   │   ├── Nodemailer.js     # Cấu hình email
│   │   ├── OpenAI.js         # Cấu hình OpenAI
│   │   ├── PayOS.js          # Cấu hình thanh toán
│   │   ├── Redis.js          # Cấu hình Redis
│   │   └── swagger.js        # API Documentation
│   ├── controllers/       # Controllers xử lý business logic
│   │   ├── Auth.controller.js
│   │   ├── Cart.controller.js
│   │   ├── Category.controller.js
│   │   ├── Chatbot.controller.js
│   │   ├── Discount.controller.js
│   │   ├── Favourite.controller.js
│   │   ├── Feedback.controller.js
│   │   ├── Order.controller.js
│   │   ├── Payment.controller.js
│   │   ├── Product.controller.js
│   │   ├── Store.controller.js
│   │   └── User.Controller.js
│   ├── middlewares/       # Middleware functions
│   │   ├── AuthMiddleWare.js     # Xác thực JWT
│   │   ├── ResponseHandler.js    # Chuẩn hóa response
│   │   └── UploadMiddleWare.js   # Upload file
│   ├── models/            # Database Models (MongoDB)
│   │   ├── Cart.model.js
│   │   ├── Category.model.js
│   │   ├── ChatHistory.model.js
│   │   ├── Discount.model.js
│   │   ├── Favourite.model.js
│   │   ├── Feedback.model.js
│   │   ├── LoginHistory.model.js
│   │   ├── Notification.model.js
│   │   ├── Order.model.js
│   │   ├── Product.model.js
│   │   ├── Store.model.js
│   │   └── User.model.js
│   ├── routes/            # API Routes
│   │   ├── Auth.route.js
│   │   ├── Cart.route.js
│   │   ├── Category.route.js
│   │   ├── Chatbot.route.js
│   │   ├── Discount.route.js
│   │   ├── Favourite.route.js
│   │   ├── Feedback.route.js
│   │   ├── Order.route.js
│   │   ├── Payment.route.js
│   │   ├── Product.route.js
│   │   ├── Store.route.js
│   │   ├── User.route.js
│   │   └── index.route.js
│   ├── services/          # Business Logic Services
│   │   ├── Auth.service.js
│   │   ├── Cart.service.js
│   │   ├── Category.service.js
│   │   ├── Chatbot.service.js
│   │   ├── Discount.service.js
│   │   ├── Favourite.service.js
│   │   ├── Feedback.service.js
│   │   ├── Order.service.js
│   │   ├── Payment.service.js
│   │   ├── Product.service.js
│   │   ├── Store.service.js
│   │   └── User.service.js
│   └── utils/             
│       ├── GenerateOTP.js    # Tạo mã OTP
│       └── JwtUtil.js        # JWT utilities
├── test/                  # Unit Tests
├── server.js             # Entry point
├── package.json          # Dependencies
└── Dockerfile           # Container configuration
```

### WebSport (Frontend)

```
WebSport/
├── src/
│   ├── admin/             # Admin Dashboard
│   ├── components/        # Reusable Components
│   ├── pages/            # Page Components
│   ├── Layout/           # Layout Components
│   ├── routes/           # Route Configuration
│   ├── services/         # API Services
│   ├── context/          # React Context (State Management)
│   ├── config/           # Configuration files
│   ├── assets/           # Static assets
│   ├── App.jsx           # Main App Component
│   ├── main.jsx          # Entry point
│   └── index.css         # Global styles
├── public/               # Public static files
├── package.json          # Dependencies
├── vite.config.js        # Vite configuration
├── tailwind.config.js    # Tailwind CSS config
├── postcss.config.js     # PostCSS config
└── dockerfile           # Container configuration
```

## 🚀 Các tính năng chính

### 👥 Quản lý người dùng
- Đăng ký/Đăng nhập với JWT
- Xác thực OTP qua email
- Quản lý profile người dùng
- Lịch sử đăng nhập

### 🛍️ Quản lý sản phẩm
- Danh mục sản phẩm đa cấp
- Tìm kiếm và lọc sản phẩm
- Quản lý kho hàng
- Upload hình ảnh với Cloudinary

### 🛒 Giỏ hàng và Đặt hàng
- Thêm/xóa sản phẩm vào giỏ hàng
- Quản lý đơn hàng
- Theo dõi trạng thái đơn hàng
- Lịch sử mua hàng

### 💳 Thanh toán
- Tích hợp PayOS
- Nhiều phương thức thanh toán
- Xử lý webhook thanh toán

### 🎁 Khuyến mãi
- Mã giảm giá
- Chương trình khuyến mãi
- Áp dụng discount tự động

### 🤖 Chatbot AI
- Tích hợp OpenAI
- Tư vấn sản phẩm thông minh
- Lịch sử chat

### 📊 Dashboard Admin
- Thống kê doanh thu
- Quản lý đơn hàng
- Quản lý người dùng
- Analytics với ApexCharts

### ⭐ Tính năng khác
- Yêu thích sản phẩm
- Đánh giá và feedback
- Thông báo real-time
- Responsive design

## 🔧 Cài đặt và chạy dự án

### Yêu cầu hệ thống
- Node.js 18+
- MongoDB
- Redis
- Docker (optional)

### 1. Clone repository
```bash
git clone <repository-url>
cd wtmsport-nodejs
```

### 2. Cài đặt Backend
```bash
cd SportEcommerceServices
npm install
```

### 3. Cài đặt Frontend
```bash
cd ../WebSport
npm install
```

### 4. Cấu hình môi trường
Tạo file `.env` trong các thư mục tương ứng dựa trên `.env.example`

#### Backend (.env)
```env
PORT=5000
MONGODB_URL=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
REDIS_CLOUD_URL=your_redis_url
GMAIL_USER=your_gmail
GMAIL_PASS=your_gmail_password
CLOUDINARY_CLOUD_NAME=your_cloudinary_name
CLOUDINARY_API_KEY=your_cloudinary_key
CLOUDINARY_API_SECRET=your_cloudinary_secret
PAYOS_CLIENT_ID=your_payos_client_id
PAYOS_API_KEY=your_payos_api_key
PAYOS_CHECKSUM_KEY=your_payos_checksum_key
OPENAI_API_KEY=your_openai_api_key
```

#### Frontend (.env)
```env
VITE_FIREBASE_API_KEY=your_firebase_api_key
VITE_FIREBASE_AUTH_DOMAIN=your_firebase_auth_domain
VITE_FIREBASE_PROJECT_ID=your_firebase_project_id
VITE_API_URL=http://localhost:5000
```

### 5. Chạy ứng dụng

#### Development mode
```bash
# Backend
cd SportEcommerceServices
npm run dev

# Frontend (terminal mới)
cd WebSport
npm run dev
```

#### Docker (Production)
```bash
docker-compose up -d
```

## 📚 API Documentation

Khi chạy backend, API documentation sẽ có sẵn tại:
```
http://localhost:5000/api-docs
```

## 🧪 Testing

### Backend Tests
```bash
cd SportEcommerceServices
npm test
```

## 🚀 Deployment

### Docker Production
```bash
docker-compose up -d
```

### Manual Deployment
1. Build frontend: `npm run build`
2. Deploy backend với PM2 hoặc process manager khác
3. Configure reverse proxy (Nginx)

## 🏪 Stores và Database

### MongoDB Collections
- **Users**: Thông tin người dùng
- **Products**: Sản phẩm
- **Categories**: Danh mục
- **Orders**: Đơn hàng
- **Carts**: Giỏ hàng
- **ChatHistory**: Lịch sử chat
- **Discounts**: Mã giảm giá
- **Favourites**: Yêu thích
- **Feedbacks**: Đánh giá
- **LoginHistory**: Lịch sử đăng nhập
- **Notifications**: Thông báo
- **Stores**: Cửa hàng

## 👥 Phân quyền

### User Roles
- **Customer**: Khách hàng thông thường
- **Admin**: Quản trị viên hệ thống

## 🔐 Bảo mật

- JWT Authentication
- Password hashing với bcrypt
- CORS configuration
- Input validation
- Rate limiting
- Environment variables cho sensitive data
---


