# Project grok-bot-agent-clone

```
[https://www.npmjs.com/package/create-fastnextjs-app]
[https://www.youtube.com/playlist?list=PLaBeGKL1tOU36nVztmb3vKs9qcpC2LTwD]
```

## 01 - Project Setup

```
[https://www.youtube.com/watch?v=oqUyyB7ROHA&list=PLaBeGKL1tOU36nVztmb3vKs9qcpC2LTwD&index=1&t=1015s&pp=0gcJCWMAwfN6Pr3D]

```

```
npx create-fastnextjs-app
Need to install the following packages:
create-fastnextjs-app@1.0.13
Ok to proceed? (y) y


┌   Next.js Startup Boilerplate Scaffolder 
│
◇  What is your project name?
│  grok-bot-agent-clone
│
◇  Select styling framework / components library:
│  Shadcn UI (Tailwind + Radix Pre-built components)
│
◇  Select Database & ORM Stack:
│  PostgreSQL + Drizzle ORM (Self-hosted or Cloud Postgres with Drizzle ORM)
│
◇  Select Authentication Provider:
│  NextAuth / Auth.js (SignIn & SignUp pages, route protection proxy & session provider)
│
◇  Select Payment Gateway:
│  None
│
◇  Select Email Sender API:
│  None
│
◇  Select Background Scheduler & Jobs Queue:
│  Inngest (Serverless event queues, background jobs & cron scheduler)
│
◇  Which package manager do you want to use?
│  npm
│
◇  Do you want to initialize a git repository?
│  Yes
│
◇  Do you want us to automatically run 'npm install'?
│  Yes
│
◇  Project structure scaffolded successfully!
│
(node:32708) [DEP0190] DeprecationWarning: Passing args to a child process with shell option true can lead to security vulnerabilities, as the arguments are not escaped, only concatenated.
(Use `node --trace-deprecation ...` to show where the warning was created)
◇  Git repository initialized.
│
◇  Dependencies installed successfully!
│
◇  All shadcn components installed successfully!
│
◇  Success ─────────────────────────────────────────────────────────╮
│                                                                   │
│  Your Next.js project grok-bot-agent-clone is ready to build! 🎉  │
│                                                                   │
│  made by Tubeguruji @ 2026                                        │
│                                                                   │
├───────────────────────────────────────────────────────────────────╯
│
◇  Next Steps ──────────────────────────────────────────────────────────╮
│                                                                       │
│  To get started, run the following commands in your terminal:         │
│                                                                       │
│    cd grok-bot-agent-clone                                            │
│    npm run db:push (after filling .env)                               │
│    npm run inngest:dev (in a 2nd terminal for background dev server)  │
│    npm run dev                                                        │
│                                                                       │
├───────────────────────────────────────────────────────────────────────╯
│
└  Happy coding! Speed up your SaaS journey. 🚀
```

```
npm run dev
```

## 02 - How to Review code using AI

```
[https://www.youtube.com/watch?v=oqUyyB7ROHA&list=PLaBeGKL1tOU36nVztmb3vKs9qcpC2LTwD&index=1&t=1820s]
```

```
Coderabbit Setup
```

## 03 - Setup Auth and DB

```
[https://www.youtube.com/watch?v=oqUyyB7ROHA&list=PLaBeGKL1tOU36nVztmb3vKs9qcpC2LTwD&index=1&t=2099s]
```

### 03.01 Database

```
Drop database and user

psql -U postgres
postgres=# DROP DATABASE grok_bot_db; 
postgres=# DROP USER grok_bot_user; 

```

```
Create database and user

psql -U postgres
postgres=# CREATE DATABASE grok_bot_db; 
postgres=# CREATE USER grok_bot_user WITH ENCRYPTED PASSWORD 'WXYZ&6789'; 
postgres=# GRANT ALL PRIVILEGES ON DATABASE grok_bot_db TO grok_bot_user; 
postgres=# \c grok_bot_db postgres;
You are now connected to database "grok_bot_db" as user "postgres"
grok_bot_db=# GRANT ALL ON SCHEMA public TO grok_bot_user; 
grok_bot_db=# ALTER USER grok_bot_user CREATEDB;
```

```
Create DATABASE_URL in .env

DATABASE_URL="postgres://grok_bot_user:WXYZ&6789@localhost:5432/grok_bot_db"
```

```
npm run db:push

> grok-bot-agent-clone@0.1.0 db:push
> drizzle-kit push

No config path provided, using default 'drizzle.config.ts'
Reading config file 'D:\Projects\learning\TG_TubeGuruji\grok-bot-agent-clone\drizzle.config.ts'
Using 'postgres' driver for database querying
[✓] Pulling schema from database...
[✓] Changes applied
```

```
npm run db:studio

> grok-bot-agent-clone@0.1.0 db:studio
> drizzle-kit studio

No config path provided, using default 'drizzle.config.ts'
Reading config file 'D:\Projects\learning\TG_TubeGuruji\grok-bot-agent-clone\drizzle.config.ts'
Using 'postgres' driver for database querying

 Warning  Drizzle Studio is currently in Beta. If you find anything that is not working as expected or should be improved, feel free to create an issue on GitHub: https://github.com/drizzle-team/drizzle-kit-mirror/issues/new or write to us on Discord: https://discord.gg/WcRKz2FFxN
```

### 03.02 Authentication

```
[https://next-auth.js.org/]
```

```
npm i axios
```

Current: 48:12

