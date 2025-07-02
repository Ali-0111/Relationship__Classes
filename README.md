# Relationship__Classes

# has-a in three face

# 1: Association
```
class User:
    def __init__(self, name):
        self.name = name

class Todo:
    def __init__(self, title):
        self.title = title

# Create users
user1 = User("Ali")
user2 = User("Sara")

# Create todos
todo1 = Todo("Buy milk")
todo2 = Todo("Call mom")
todo3 = Todo("Read Quran")

# Manual association
user_todo_map = {
    user1: [todo1, todo3],
    user2: [todo2]
}

# Display associations
for user, todos in user_todo_map.items():
    print(f"{user.name} has the following todos:")
    for todo in todos:
        print(f" - {todo.title}")

```


# 2: Aggregate
```
class Todo:
    def __init__(self, title):
        self.title = title

class User:
    def __init__(self, name, todos):
        self.name = name
        self.todos = todos  # Aggregation

todo1 = Todo("Buy milk")
todo2 = Todo("Call mom")
user = User("Ali", [todo1, todo2])

```

# 3: Composition
```
class Todo:
    def __init__(self, title):
        self.title = title

class User:
    def __init__(self, name):
        self.name = name
        self.todos = []  # Composition

    def add_todo(self, title):
        self.todos.append(Todo(title))

user = User("Ali")
user.add_todo("Buy milk")
user.add_todo("Read book")

```
