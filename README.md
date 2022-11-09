# rust-fullstack-demo
A fullstack Rust application demo

## Database Setup
This app requires a Postgres database.
Once you have a Postgres server up and running, create a database and make sure your database user as read and write privileges.

Example:

```bash
sudo -u postgres psql
create database rustfullstack;
create user rustuser with encrypted password 'password';
grant all privileges on database rustfullstack to rustuser;
exit
```

Next create a .env file in the root of this project and put the connection url inside.
It should look like this:

```
DATABASE_URL=postgres://{postgres_user}:{postgres_password}@localhost:5432/{database_name}
```

If you used the exact settings from above then it should look like this:

```
DATABASE_URL=postgres://rustuser:password@localhost:5432/rustfullstack
```

Next we need to run the migrations to populate the database with tables and sample data.

From the root directory run the following:

```bash
cargo run --manifest-path ./database/migration/Cargo.toml
```

## Running the App
