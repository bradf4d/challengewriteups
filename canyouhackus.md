# Writeup 

## canyouhack.us

This has my hardest challenge for each category.

### SQL 2

The challenge has a SQL database lookup

```
Look up information in our book database (eg. search for '1984' or 'Neuromancer'). The "users" table is protected by military grade security.
```

You can search through the table normally and the users table has extra security so it can't be queried dirctly. The SQL database turns on some standard filters that once turned off, make it trivial to query the user's table:

```
'; builtIn:ignore_filter(TRUE);
```

We can close the statement and send in this to turn off some built-in filters. Then, the users table can be queried with a select or union statement.

The users table has a hidden name, `hidden_user_table_42`, so you can modify this query to work with the existing injection:

```SELECT * FROM hidden_user_table_42;```

Hitchhikers guide reference, classic. Click the flag link to get to the rest of the fish!

## Tokens 2

```
Alice has been entering her password into an application to get a series of tokens.
```

The tokens are hashed. You can use John the Ripper to do a hashing table attack against them. You can use the simplest mode of it. You will need a bigger password test list than basic JtR uses, so consider grabbing rockyou.txt or a dictionary.

```john <password file>```

And we get:

``secrettunnel7``





