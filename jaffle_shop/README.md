Welcome to your new dbt project!

### Using the starter project

Try running the following commands:

- dbt run
- dbt test

### Resources:

- Learn more about dbt [in the docs](https://docs.getdbt.com/docs/introduction)
- Check out [Discourse](https://discourse.getdbt.com/) for commonly asked
  questions and answers
- Join the [chat](https://community.getdbt.com/) on Slack for live discussions
  and support
- Find [dbt events](https://events.getdbt.com) near you
- Check out [the blog](https://blog.getdbt.com/) for the latest news on dbt's
  development and best practices

### Development

I set this up with a PostgreSQL conatiner and a persisted volume so I can forget
about it once I'm done with the tutorial.

I did the following:

```sh
docker pull postgres
docker volume create dbt-tutorial
docker run --name dbt-tutorial \
    -e POSTGRES_PASSWORD=mysecretpassword \
    -p 5432:5432 \
    -v dbt-tutorial:/var/lib/postgresql/data \
    -d postgres
```

It would wise to store the crendentials in a `~/.pgpass` file so I don't have to
type them again when connecting through `psql`.

Before connecting with dbt don't forget to add the connection settings to your
`~/.dbt/profiles.yml`.
