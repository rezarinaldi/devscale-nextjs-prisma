# 📐 Template Project Next.js, Prisma, and AWS S3

> [!NOTE]
> Template Project Next.js, Prisma, and AWS S3 for Bootcamp devscale.id (Beginner Class) Batch 4.

This is an example template, already set up:

- Example Middleware, go to [middleware.js](./src/middleware.js) file.

```bash
src
└── middleware.js
```

- [daisyUI](https://daisyui.com/)
- [Prisma](https://prisma.io/)
- [AWS S3](https://aws.amazon.com/pm/serv-s3)

## Environment Variables

- DATABASE_URL
- AWSS3_ACCESS_KEY
- AWSS3_SECRET_KEY
- JWT_SECRET

## How to use it:

1. Clone this repo or use as template:

- Clone the repo.

```bash
git clone https://github.com/rezarinaldi/devscale-nextjs-prisma.git
# at current directory/folder
git clone https://github.com/rezarinaldi/devscale-nextjs-prisma.git .

# using ssh
git clone git@github.com:rezarinaldi/devscale-nextjs-prisma.git
# at current directory/folder
git clone git@github.com:rezarinaldi/devscale-nextjs-prisma.git .
```

- Create project with template.

```bash
npx create-next-app@latest -e https://github.com/rezarinaldi/devscale-nextjs-prisma
# at current directory/folder
npx create-next-app@latest -e https://github.com/rezarinaldi/devscale-nextjs-prisma .
```

2. Install dependencies:

```bash
npm install
```

3. Copy the `.env.example` to `.env`:

```bash
cp .env.example .env
```

4. Setting provider database and create database model in the [schema.prisma](./src/prisma/schema.prisma) file.

```bash
src
└── prisma
    └── schema.prisma
```

5. Do prisma migration:

> [!WARNING]
> This step if the database provider used is `SQLite`, otherwise ignore it and skip this step.

```bash
npm run db:migrate
```

6. Use `db push` to push the initial schema to the database:

```bash
npm run db:push
```

7. Run the development server:

```bash
npm run dev
```

8. Open http://localhost:3000 with your browser to see the result.

9. Do prisma studio:

```bash
npm run db:studio
```

10. Open http://localhost:5555 with your browser to see the result.

## Deployment

> [!TIP]
> Don't forget adding `prisma generate` to the existing script build command Vercel.

### Vercel UI's build script field

Another way to configure `prisma generate` to be run on every deployment is to add the command to the build settings via Vercel's UI.

Within your project's dashboard, go to the `Settings` tab and find the `General` section. In that section you will find a box labeled `Build & Development Settings` that contains an input field named `Build Command`:

![build-command-1](public/readme/vercel-ui-build-command.png)

Within that field, prepend `prisma generate` to the existing script:

```bash
prisma generate && next build
```

![build-command-2](public/readme/vercel-ui-build-command-filled.png)

Reference: [Vercel build dependency caching workaround](https://www.prisma.io/docs/orm/more/help-and-troubleshooting/help-articles/vercel-caching-issue)
