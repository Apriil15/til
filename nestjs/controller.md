# Controller

- controller 裡的方法如果有用到 Request 物件，`要 import 對的 Request`

```tsx
import { Controller, Get, Req } from "@nestjs/common";
import { Request } from "express"; // 要 import 對！
import { AppService } from "src/app.service";

@Controller("user")
export class UserController {
  constructor(private app: AppService) {}

  @Get("info")
  findUserInfo(@Req() request: Request): string {
    return "find user info";
  }
}
```

- 參數可以直接用 body 的 decorator

```tsx
@Body() body: Body
```

- route 通配字元 `*`

```tsx
// 加上 *
@Get('in*fo')
```
