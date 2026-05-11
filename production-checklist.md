# Gacky-X Production Deployment Checklist 🚀

Follow this checklist to ensure a safe and high-performance deployment.

### 1. Infrastructure Setup
- [ ] **Node.js**: Ensure v18 or higher is installed.
- [ ] **PostgreSQL**: Database is accessible and `DATABASE_URL` is set.
- [ ] **Redis**: Redis server is running and `REDIS_URL` is configured for caching.
- [ ] **Process Manager**: Use `PM2` or `Docker` to keep the bot alive.

### 2. Discord Developer Portal
- [ ] **Privileged Intents**: `Guild Members`, `Message Content`, and `Server Members` intents are enabled.
- [ ] **Permissions**: Bot has `Administrator` or at least all required management permissions.
- [ ] **Hierarchy**: The bot's highest role is placed above all roles it needs to manage/protect.

### 3. Application Configuration
- [ ] **Bot Owner IDs**: `BOT_OWNER_IDS` in `.env` is correctly comma-separated.
- [ ] **Default Prefix**: Configured as `-` (or your preferred prefix).
- [ ] **Logs**: Run `-logall` or manual setup to ensure security events are tracked.

### 4. Database Initialization
- [ ] Run `npx prisma generate` to sync the client.
- [ ] Run `npx prisma db push` or `prisma migrate deploy` for production schema.
- [ ] Verify `add_performance_indexes` has been applied to speed up logs and lookups.

### 5. Security Validation
- [ ] **Antinuke**: Test thresholds in a private test server.
- [ ] **Whitelist**: Whitelist your alt account to ensure bypasses work.
- [ ] **Verification**: Confirm MATH/TEXT modal popups work instantly.

### 6. Monitoring & Maintenance
- [ ] Monitor console for `[LoggingService]` or `[ComponentHandler]` errors.
- [ ] Check `DeveloperLog` in database for global owner actions.
- [ ] Regularly backup your PostgreSQL database.

---
*Status: Ready for Deployment.*
