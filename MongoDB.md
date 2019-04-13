All about MongoDB you'd need to know

*CREATE USER

Username/password authentication

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

*ROLE
- Built-in role:
-- dbAdmin
Provides the ability to perform administrative tasks such as schema-related tasks, indexing, and gathering statistics. This role does not grant privileges for user and role management.
-- dbOwner
The database owner can perform any administrative action on the database. This role combines the privileges granted by the readWrite, dbAdmin and userAdmin roles.
-- userAdmin
Provides the ability to create and modify roles and users on the current database. Since the userAdmin role allows users to grant any privilege to any user, including themselves, the role also indirectly provides superuser access to either the database or, if scoped to the admin database, the cluster.

Ref: https://docs.mongodb.com/manual/reference/built-in-roles/#database-administration-roles

- User-defined role:
Ref: https://docs.mongodb.com/manual/core/security-user-defined-roles/#user-defined-roles