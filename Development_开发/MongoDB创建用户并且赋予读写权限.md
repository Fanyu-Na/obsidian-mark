---
title: MongoDB创建用户并且赋予读写权限
cid: 7
type: post
created: 1741325738
modified: 1741325738
slug: 7
---

```bash
db.createUser({
  user: "myUser",
  pwd: "myPassword",
  roles: [
    { role: "readWrite", db: "mydatabase" },
    { role: "read", db: "anotherdatabase" }  // 只有读权限
  ]
});
```
