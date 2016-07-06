**API**

**REST Index** 

GET /resource
**Params**:
> task: (string)
> start: (integer)
> limit: (integer)
> filter1: 
> filter: 2
> filter: 3

**Response**
  > error:
  > - message: (string)
  > - backtrace: []
  > data:
  >  - (object)
  > total: (int)
  > 

-----
** REST show **

GET /resource/:id
**Params**:
task: (string)

** Response **
  > error:
  > - message: (string)
  > - backtrace: []
  > data:
  >  - (object)

----- 

** REST create **

POST /resource
PARAMS:
> data: {}

**RESPONSE**:
> error:
>   message: (string)
>   backtrace: []
> id: (key)   

-------

** REST update**

PUT /resouce/:id
PARAMS:
> data: {}

**RESPONSE**:
> error:
>   message: (string)
>   backtrace: []
> id: (key)   

-------

** REST delete **
DELETE /resource/:id
**RESPONSE**:
> error:
>   message: (string)
>   backtrace: []
> id: (key)   
