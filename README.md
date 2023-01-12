# Node Concepts

In this application you can manage TODO's with a CRUD.
You can:

- Create new todos
- List all todos
- Changing todos `title` and `deadline` of todos already created
- Mark as done an specific todos
- Delete an specific todos

## Routes

### POST `/users`
You must send `name` and `username` field in the body request. 
```javascript
{
  name: "Samuel Mesquita",
  username: "sammexkita"
}
```
After send the data you should receive an data object like:
```javascript
{
  id: "UUID V4"
  name: "Samuel Mesquita",
  username: "sammexkita",
  todos: []
}

```

### GET `/todos`
In this route you must send in header request the username created before.
If you use **Insomnia** it would be like this:
![Screenshot 2023-01-11 at 19 29 32](https://user-images.githubusercontent.com/78756748/211931726-ce10b99a-3f5c-4d51-8dac-42ec2eee202f.png)
With this you must receive all user todos.

### POST `/todos`
To create todos you must send in body request `title`, `deadline` and `username`. This last you need to send in header request.
After send you must receive the following object:
```javascript
  {
    id: "uuid",
    title: "todo title",
    done: false,
    deadline: '2021-02-27T00:00:00.000Z', 
	  created_at: '2021-02-22T00:00:00.000Z'
  }
```

### PUT `/todos/:id`
In this route you can change the `title` and `deadline`. You must provide `username` in request header.
Sending you must receive the todo changed

### PATCH `/todos/:id/done`
You can also mark done in your todo, you just need to provide username in header and the todo id in the request params.

### DELETE `/todos/:id`
To delete a todo you must provide `username` and the todo's id