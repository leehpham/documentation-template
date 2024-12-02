# Environment Variables

Document required environment variables.

## Required Variables

| Variable Name      | Description                          | Example Value          |
|--------------------|--------------------------------------|------------------------|
| `PORT`            | Application port                     | `3000`                |
| `DB_HOST`         | Database host                        | `localhost`           |
| `DB_USER`         | Database username                    | `user123`             |
| `DB_PASS`         | Database password                    | `securepassword`      |
| `JWT_SECRET`      | Secret key for JWT                   | `your-secret-key`     |

## Using .env

Create a `.env` file in the root directory based on `.env.example`. Example:

```txt
PORT=3000
DB_HOST=localhost
DB_USER=user123
DB_PASS=securepassword
JWT_SECRET=your-secret-key
```
