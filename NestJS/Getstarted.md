## NestJS

### Get Started

- 빠른 개발 환경 설정

```
$ npm i -g @nestjs/cli
$ nest new project-name
```

- src 폴더 하위 core files
  - app.controller.ts | A basic controller with a single route. 
  - app.controller.spec.ts | The unit tests for the controller. 
  - app.module.ts | The root module of the application.
  - app.service.ts | A basic service with a single method. 
  - main.ts | The entry file of the application which uses the core function NestFactory to create a Nest application instance. 

#### main.ts

딱 보니 서버 생성하는 것 같은데 매우 효율적으로 보인다

```
import { NestFactory } from '@nestjs/core';
import { AppModule } from './app.module';

async function bootstrap() {
  const app = await NestFactory.create(AppModule);
  await app.listen(3000);
}
bootstrap();
```

#### app.service.ts

api 요청에 실행될 서비스를 작성하는 곳

```
import { Injectable } from '@nestjs/common';

@Injectable()
export class AppService {
  getHello(): string {
    return 'Hello Nest!';
  }
}

```

#### app.controller.ts

HTTP Request를 Routing 해주는 역할

```
import { Controller, Get } from '@nestjs/common';
import { AppService } from './app.service';

@Controller()
export class AppController {
  constructor(private readonly appService: AppService) {}

  @Get()
  getHello(): string {
    return this.appService.getHello();
  }
}
```

'/' path 요청을 appservice의 getHello()로 라우팅 해주는 것

#### app.module.ts

관련있는 Controller와 Service를 묶어주는 역할
OOP의 SOLID 원칙을 manage 할 수 있게 해줌

```
import { Module } from '@nestjs/common';
import { AppController } from './app.controller';
import { AppService } from './app.service';

@Module({
  imports: [],
  controllers: [AppController],
  providers: [AppService],
})
export class AppModule {}
```
