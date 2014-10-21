Relating Messages
=================

Problem
-------

Imagine you're listing your friends and friends of another side-by-side. That would required 2 requests and 2 messages back of the same type. How would you know which message is responding to which request?

| Requesting Message            | Responding Message        |
| ----------------------------- | ------------------------- |
| 'list friends' `{user_id: 1}` | 'list of friends' `[...]` |
| 'list friends' `{user_id: 2}` | 'list of friends' `[...]` |

Solution
--------

Every message can pass an ID to help relate it to other messages.

| Requesting Message                     | Responding Message                      |
| -------------------------------------- | --------------------------------------- |
| 'list friends' `{user_id: 1, _id_: 1}` | 'list of friends' `{_id_: 1, data: []}` |
| 'list friends' `{user_id: 2, _id_: 2}` | 'list of friends' `{_id_: 2, data: []}` |

