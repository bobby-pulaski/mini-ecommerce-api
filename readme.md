# 🛒 Mini E-commerce API (Symfony 7.2 + JWT Auth)

## 🚀 Project Description
This project is the backend of an e-commerce application built using **Symfony 7.2**. It includes user authentication mechanisms using **JWT** and basic operations on products and orders.

---

## 🛠 Technology Stack
- **PHP 8.2 + Symfony 7.2**
- **PostgreSQL / MySQL**
- **JWT Authentication** (LexikJWTAuthenticationBundle)
- **Doctrine ORM**
- **Docker** (optional)

---

## ⚡ Installation

### 1️⃣ Clone the repository
```bash
git clone https://github.com/bobby-pulaski/mini-ecommerce-api.git
cd mini-ecommerce
```

### 2️⃣ Install dependencies
```bash
composer install
```

### 3️⃣ Configure .env
Update the `.env` file with your database and JWT configuration:

```env
DATABASE_URL="mysql://user:password@127.0.0.1:3306/ecommerce_db"
JWT_SECRET_KEY=%kernel.project_dir%/config/jwt/private.pem
JWT_PUBLIC_KEY=%kernel.project_dir%/config/jwt/public.pem
JWT_PASSPHRASE=your_passphrase_here
```

### 4️⃣ Generate JWT keys
```bash
mkdir -p config/jwt
openssl genpkey -algorithm RSA -out config/jwt/private.pem -pkeyopt rsa_keygen_bits:4096
openssl rsa -pubout -in config/jwt/private.pem -out config/jwt/public.pem
chmod 600 config/jwt/private.pem
chmod 644 config/jwt/public.pem
```

### 5️⃣ Database migration
```bash
php bin/console doctrine:migrations:migrate
```

### 6️⃣ Start the server
```bash
symfony server:start
```

---

## 🔑 Authorization (JWT)

### Register user
- **Endpoint:** `POST /api/register`
- **Description:** Register a new user.

### Login
- **Endpoint:** `POST /api/login`
- **Description:** Login and receive a JWT token.

### Using the JWT token
Include the received JWT token in the request header:
```makefile
Authorization: Bearer <TOKEN>
```

---

## 📦 API Endpoints

| Method | Endpoint        | Description        |
|--------|---------------|--------------------|
| POST   | `/api/register` | User registration |
| POST   | `/api/login`    | Login (JWT)       |
| GET    | `/api/products` | Get product list  |
| POST   | `/api/orders`   | Create order      |

---

## 📌 Additional Information

### Docker
If you are using Docker, start the project with:
```bash
docker-compose up -d
```

### Testing
You can test the API using tools like **Postman** or **cURL**.

---

## ✨ Author
**RobertKuligDev** - [GitHub](https://github.com/bobby-pulaski/mini-ecommerce-api)

