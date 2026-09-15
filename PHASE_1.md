# PHASE 1: Foundation

**Scope**: Repository setup, database schema, authentication, RBAC, project structure.

**Gate Requirement**: All tests pass, schema created, basic auth flow works.

## Tasks

### 1.1 Monorepo Setup
- [ ] Initialize pnpm workspace
- [ ] Create `/apps/api`, `/apps/web`, `/packages/types`, `/packages/shared`
- [ ] Configure TypeScript `tsconfig.base.json`
- [ ] Add linting (ESLint), formatting (Prettier)
- [ ] Create `.env.example` with all required vars
- [ ] Set up `.gitignore` (no secrets, no node_modules)

### 1.2 Backend Project Initialization
- [ ] Create `/apps/api` with Fastify
- [ ] Set up TypeScript strict mode
- [ ] Configure ESM imports
- [ ] Add Helmet for security headers
- [ ] Add CORS configuration
- [ ] Create basic health check endpoint: `GET /health`

### 1.3 Database Setup
- [ ] Initialize PostgreSQL via Docker Compose
- [ ] Install Prisma
- [ ] Create initial schema:
  ```
  User
  Organization
  OrganizationMember
  Project
  Environment
  ```
- [ ] Create migration: `001_initial_schema`
- [ ] Add database connection string to `.env`
- [ ] Create seed script with demo organization, demo user, demo project

### 1.4 Authentication
- [ ] Implement email/password registration
- [ ] Implement email/password login
- [ ] Create JWT token generation
- [ ] Implement JWT verification middleware
- [ ] Add session expiration logic
- [ ] Create logout endpoint
- [ ] Add password hashing (bcrypt)
- [ ] Create password reset flow (email token)

### 1.5 User & Organization Model
- [ ] Implement User creation
- [ ] Implement Organization creation
- [ ] Implement Organization membership (OrganizationMember)
- [ ] Add user profile endpoint: `GET /users/me`
- [ ] Add update user endpoint: `PATCH /users/me`

### 1.6 RBAC System
- [ ] Create roles: OWNER, ADMIN, DEVELOPER, VIEWER
- [ ] Implement role-based middleware
- [ ] Create permission checker function
- [ ] Add role assignment to organization members
- [ ] Create RBAC tests

### 1.7 Project Management
- [ ] Create project creation endpoint: `POST /projects`
- [ ] Create project list endpoint: `GET /projects`
- [ ] Create project fetch endpoint: `GET /projects/:id`
- [ ] Create project update endpoint: `PATCH /projects/:id`
- [ ] Create project delete endpoint: `DELETE /projects/:id`
- [ ] Add authorization checks (RBAC) to all endpoints
- [ ] Add project environment configuration (dev, staging, prod)

### 1.8 API Structure
- [ ] Create error handling with typed errors
- [ ] Create response wrapper (success/error format)
- [ ] Create request validation middleware
- [ ] Add correlation ID to all requests
- [ ] Implement structured logging
- [ ] Create API documentation skeleton

### 1.9 Testing
- [ ] Set up Vitest
- [ ] Create tests for authentication
- [ ] Create tests for RBAC
- [ ] Create tests for project CRUD
- [ ] Add database test fixtures
- [ ] Create test database migration script

### 1.10 Docker Compose
- [ ] Create `docker-compose.yml` with:
  - PostgreSQL
  - Redis
  - API service
- [ ] Test full local stack startup
- [ ] Document startup procedure in README

### 1.11 Documentation
- [ ] Create `README.md` with project overview
- [ ] Create `GETTING_STARTED.md` with local setup steps
- [ ] Document API authentication
- [ ] Document RBAC roles and permissions
- [ ] Create `API.md` with endpoint documentation

## Success Criteria

1. ✅ Monorepo builds without errors
2. ✅ `docker-compose up` starts all services
3. ✅ User can register and login
4. ✅ JWT tokens are generated and validated
5. ✅ Organization and projects can be created
6. ✅ RBAC prevents unauthorized access
7. ✅ All tests pass (`npm test`)
8. ✅ API documentation is complete
9. ✅ Environment variables are documented
10. ✅ Database schema is generated and migrated

## Definition of Done for Phase 1

A developer can:
```
1. Clone the repo
2. Copy .env.example → .env
3. Run docker-compose up
4. Run npm install
5. Run npm run db:migrate
6. Run npm test
7. POST /auth/register
   { "email": "dev@test.com", "password": "test123" }
8. POST /auth/login
   { "email": "dev@test.com", "password": "test123" }
9. Receive JWT token
10. GET /users/me (with token)
    Receive user profile
11. POST /projects
    { "name": "Demo", "description": "..." }
12. Receive project object
13. All tests pass
```

When this flow works end-to-end, **Phase 1 is complete**.

---

**Next**: PHASE_2.md (Chains, Contracts, ABI Import)
