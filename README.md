# Node.js Backend Template 

A simple and reusable backend starter built with **Node.js**, **Express**, and **PostgreSQL**.  
Includes authentication, role-based access control (RBAC), file uploads, CRUD operations, error handling, and email templates.

---

##  Project Structure

backend/
├── server.js              # Entry point
├── config/                # Environment + DB config
├── routes/                # API endpoints
├── controllers/           # Request handlers
├── middleware/            # Auth, RBAC, uploads
├── utils/                 # Helpers (JWT, crypto, logger)
├── models/                # DB queries / schemas
├── emails/                # Email templates
├── uploads/               # Uploaded files
├── .env                   # Environment variables
└── package.json           # Dependencies

---

##  Setup

1. **Clone the repo**
   git clone https://github.com/VanathiS06/node-express-template.git
   cd node-express-template

2. **Install dependencies**
   npm install

3. **Configure environment**
   - Copy `.env.example` → `.env`
   - Update DB credentials, JWT secret, email SMTP settings

4. **Run migrations**
   # Example using psql
   psql -U <user> -d <dbname> -f migrations/001_init.sql

5. **Start the server**
   npm run dev
   # Server runs at http://localhost:4000

---

##  Authentication & RBAC

- JWT-based authentication
- Roles: `admin`, `manager`, `user`
- Middleware enforces access:
  - `auth.js` → verifies JWT
  - `rbac.js` → checks role permissions

---

##  File Uploads

- Uses **Multer** for handling multipart form data
- Files stored in `/uploads`
- Metadata saved in PostgreSQL

---

##  Email Templates

- Located in `emails/templates/`
- Examples:
  - `verifyEmail.html`
  - `resetPassword.html`
- Sent via **Nodemailer** with EJS rendering

---

##  Utilities

- `jwt.js` → sign/verify tokens
- `crypto.js` → password hashing
- `logger.js` → simple logging utility

---

##  API Docs

- Swagger UI available at:
  http://localhost:4000/api/docs

---

##  Using as a Template

When starting a new project:
   git clone https://github.com/VanathiS06/node-express-template.git my-new-project
   cd my-new-project
   rm -rf .git   # remove old history
   git init      # start fresh repo

---

## Next Steps

- Add validation (Joi)
- Add rate limiting (express-rate-limit)
- Add testing (Jest + Supertest)
- Deploy with Docker or cloud provider

---