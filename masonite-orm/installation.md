# 🔌 Installation

**This ORM is still in development**

First install via pip:

```text
$ pip install masonite-orm
```

## Base Python Projects

### Configuration File

The first thing you will need is a configuration file. This will be home to all your database connection information.

We can simply create a `config/database.py` file and then put a `CONNECTIONS` variable with a dictionary of connection details. This file will look like this:

```python
# config/database.py
DATABASES = {
    'default': 'mysql',
    'mysql': {
        'driver': 'mysql',
        'host': 'localhost',
        'user': 'root',
        'password': '',
        'database': 'orm',
        'port': '3306',
        'prefix': '',
        'options': {
            'charset': 'utf8mb4',
        },
    },
    'postgres': {
        'driver': 'postgres',
        'host': 'localhost',
        'user': 'postgres',
        'password': 'postgres',
        'database': 'orm',
        'port': '5432',
        'prefix': ''
    },
    'sqlite': {
        'driver': 'sqlite',
        'database': 'orm.db',
    }
}
```

### Creating a Model

Now you can create a model. Refer to the model documentation but in simplest form you can create a class which inherits Masonite ORM `Model` class. Assuming you have a `users` table:

```python
# user.py
from masonite.orm import Model

class User(Model):
    pass
```

### Make a database call

To make sure everything is correct let's try making a database call:

```python
# Import your Model wherever it is
from user import User 

print(User.all())
```

You should see a collection class in the terminal.

Congratulations! You just installed Masonite ORM.

