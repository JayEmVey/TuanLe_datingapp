# All about MongoDB you'd need to know

## CREATE USER

### Username/password authentication

Ex:

    use reporting
    db.createUser(
      {
        user: "reportsUser",
        pwd: "12345678",
        roles: [
           { role: "read", db: "reporting" },
           { role: "read", db: "products" },
           { role: "read", db: "sales" },
           { role: "readWrite", db: "accounts" }
        ]
      }
    )

Ref: https://docs.mongodb.com/manual/tutorial/create-users/

## UPDATE USER

Ex:
    use cms
    db.updateUser(
    {
      updateUser: "reportsUser",
      pwd: "ABC123",
      roles: [
           { role: "readWrite", db: "reporting" },
           { role: "read", db: "products" },
           { role: "read", db: "sales" },
           { role: "readWrite", db: "accounts" }
        ]
    }

## Change user password
Syntax:
  db.changeUserPassword(username, password)

Ex:
  use products
  db.changeUserPassword("accountUser", "SOh3TbYhx8ypJPxmt1oOfL")

> Ref: https://docs.mongodb.com/manual/reference/method/db.changeUserPassword/index.html

## ROLE
### Built-in role:
- dbAdmin
Provides the ability to perform administrative tasks such as schema-related tasks, indexing, and gathering statistics. This role does not grant privileges for user and role management.
- dbOwner
The database owner can perform any administrative action on the database. This role combines the privileges granted by the readWrite, dbAdmin and userAdmin roles.
- userAdmin
Provides the ability to create and modify roles and users on the current database. Since the userAdmin role allows users to grant any privilege to any user, including themselves, the role also indirectly provides superuser access to either the database or, if scoped to the admin database, the cluster.

>Ref: https://docs.mongodb.com/manual/reference/built-in-roles/#database-administration-roles

### User-defined role:
>Ref: https://docs.mongodb.com/manual/core/security-user-defined-roles/#user-defined-roles

## Backup/restore
### Import/export

- JSON
-- Import collection
  mongoimport -h ds239936.mlab.com:39936 -d heroku_05gt1tps -c <collection> -u <user> -p <password> --file <input file>
-- Export collection
mongoexport -h ds239936.mlab.com:39936 -d heroku_05gt1tps -c <collection> -u <user> -p <password> -o <output file>
- CSV
-- Import collection
  mongoimport -h ds239936.mlab.com:39936 -d heroku_05gt1tps -c <collection> -u <user> -p <password> --file <input .csv file> --type csv --headerline
-- Export collection
  mongoexport -h ds239936.mlab.com:39936 -d heroku_05gt1tps -c <collection> -u <user> -p <password> -o <output .csv file> --csv -f <comma-separated list of field names>
