REST vs RESM
============

A table matching REST requests to RESM messages

| REST              | RESM                                       |
| ------------------|------------------------------------------- |
| GET /users?..     | `{type: 'list users', data: {...}}`        |
| POST /users `{}`  | `{type: 'create user', data: {}}`          |
| GET /users/1      | `{type: 'retrieve user', data: 1}`         |
| PUT /users/1 `{}` | `{type: 'update user', data: {id:1, ...}}` |
| DELETE /users/1   | `{type: 'delete user', data: 1}`           |

Unlike HTTP, web sockets do not respond to a message; the transmission is only one way. To get around this, there is a 2nd message available with the action turned into a noun. This represents the result gathered from the action. This isn't required for all actions.

*To simplify following examples, the message ‘type’ will be displayed in quotes and the message ‘data’ will immediately follow (if any is required).*

| Client Message      | Server Message       |
| ------------------- | -------------------- |
| 'list users' `{}`   | 'list of users' `[]` |
| 'retrieve user' `1` | 'user' `{}`          |

All applications listening to/emitting these messages should act on all the above messages. That way information can be completely shared by all applications. For example there maybe a case when the server would like to know what users the clients have.

When actions take place that all clients need to be aware, the server "[broadcasts](/johngeorgewright/RESM/wiki/messaging-and-broadcasting)" to all listening clients. In the case of deleting the user, the server can simply bounce the message without changing any data. When updating and creating users, however, the server may need want to change the data before rebroadcasting it.

| Client Message            | Server Message       | Server Broadcast          |
| ------------------------- | -------------------- | ------------------------- |
| 'list users' `{}`         | 'list of users' `[]` |                           |
| 'create user' `{}`        |                      | 'create user' `{}`        |
| 'retrieve user' `1`       | 'user' `{}`          |                           |
| 'update user' `{id:1, …}` |                      | 'update user' `{id:1, …}` |
| 'delete user' `1`         |                      | 'delete user' `1`         |

