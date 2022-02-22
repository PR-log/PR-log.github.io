try exception statement
---
modified(2022/02/22)

```
try:
  4/0
except Exception as ex:    #Exception : 여러가지 오류 포함
  print(f"error = {ex}")
 ```
>division by zero

If an error occurred while perform try block  
-> perform except block

But if there is no error in the try block, except block is not performed
