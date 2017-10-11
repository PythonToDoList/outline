# To Do List in Four Ways

**Author**: Nicholas Hunt-Walker

DB: postgres

## API endpoints

| Method | Route | Description |
| ------ | ----- | ----------- |
| `GET` | `/` | home page |
| `GET` | `/api/v1/` | list of existing endpoints |
| `GET` | `/api/v1/tasks` | list of all tasks for a user |
| `POST` | `/api/v1/tasks` | add a new task for this user |
| `GET` | `/api/v1/tasks/<id>` | detail of one individual task that belongs to a user |
| `PUT` | `/api/v1/tasks/<id>` | update a user's task |
| `DELETE` | `/api/v1/tasks/<id>` | delete a user's task |
| `POST` | `/api/v1/profiles` | create a new user |
| `POST` | `/api/v1/login` | log a user in |
| `GET` | `/api/v1/logout` | log a user out |
| `GET` | `/api/v1/profiles/<id>` | detail for one user |
| `PUT` | `/api/v1/profiles/<id>` | update info for one user |
| `DELETE` | `/api/v1/profiles/<id>` | delete one user |

## The Task Model

```python
class Task
    id - int
    name - str
    note - str | optional
    creation_date - datetime | auto
    due_date - datetime | optional
    user_id - int | foreign key
    completed - bool | default False
```

## The Profile Model

```python
class Profile
    id - int
    username - str
    email - str
    password - str
    date_joined - datetime | auto
    tasks - str | related to Task objects
```

## Flask

Built with [sloria](https://github.com/sloria)'s Flask cookiecutter

Sources:
- https://realpython.com/blog/python/flask-by-example-part-1-project-setup/ (and subsequent posts)
- https://www.tutorialspoint.com/flask/flask_url_building.htm
- https://blog.miguelgrinberg.com/post/restful-authentication-with-flask
- https://realpython.com/blog/python/token-based-authentication-with-flask/
- http://blog.luisrei.com/articles/flaskrest.html
- https://flask-migrate.readthedocs.io/en/latest/