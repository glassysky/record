# user

### user/sign-up

POST

|Key|Type|Required|
|---|---|:---:|
|name|string|Y|
|user_name|string|Y|
|password|string|Y|
|stu_id|string|Y|
|qq|string|Y|
|email|string|Y|
|tel|string|Y|

```
{
  code: 1,
  result: "success"
}
```

### user/delete

### user/update

### user/get

GET

|Key|Type|Required|
|---|---|:---:|
|id|number|Y(or stu_id)|
|stu_id|string|Y(or id)|

```
{
  "code": 1,
  "result": [
    {
      "id": 14,
      "name": "test",
      "user_name": "123",
      "password": "4567666",
      "stu_id": "B14011030",
      "tel": "18252031827",
      "email": "873661157@qq.com",
      "qq": "873661157"
    }
  ]
}
```
