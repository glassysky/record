# enroll


### /enroll/add

POST

|Key|Type|Required|
|---|---|:---:|
|first_dep|number|Y|
|second_dep|number|N|
|self_intro|text|N|
|join_reason|text|N|

```
{
  "code": 1,
  "result": "success"
}
```

### /enroll/remove

GET

|Key|Type|Required|
|---|---|:---:|
|enroll_id|number|Y|

```
{
  "code": 1,
  "result": "success"
}
```

### /enroll/update

POST

|Key|Type|Required|
|---|---|:---:|
|first_dep|number|Y|
|second_dep|number|N|
|self_intro|text|N|
|join_reason|text|N|

```
{
  "code": 1,
  "result": "success"
}
```

### /enroll/get

GET

|Key|Type|Required|
|---|---|:---:|
|id|number|Y(or enroll_id)|
|enroll_id|number|Y(or id)|
