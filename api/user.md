# user

### /user/sign-up

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
  "code": 1,
  "result": {
    "data": {
      "name": "test",
      "user_name": "123",
      "password": "429a0911a2c42e460682d00d13660b71",
      "stu_id": "B14011024",
      "email": "873661157@qq.com",
      "qq": "873661157",
      "tel": "18252031827",
      "id": 33
    },
    "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOjMzLCJleHAiOjE0NzQxNzkzMDE0OTJ9.Gy74dODCI-8vaBq2PtqpLB3jHQYRTpCsplWdp8AxhdA",
    "expires": 1474179301492
  }
}
```

### /user/sign-in

POST

|Key|Type|Required|
|---|---|:---:|
|password|string|Y|
|stu_id|string|Y|

```
{
  "code": 1,
  "result": {
    "data": {
      "id": 27,
      "name": "test",
      "user_name": "123",
      "password": "429a0911a2c42e460682d00d13660b71",
      "stu_id": "B14011031",
      "tel": "18252031827",
      "email": "873661157@qq.com",
      "qq": "873661157"
    },
    "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOjI3LCJleHAiOjE0NzQzMDA0Nzg3ODZ9.PYDEyDM36lY0Y058o3BzW1asSYOhWJ9M_KAu1W5u62E",
    "expires": 1474300478786
  }
}
```

### /user/remove

GET

|Key|Type|Required|
|---|---|:---:|
|id|number|Y|

```
{
  code: 1
}
```

### /user/update

### /user/get

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
