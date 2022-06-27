# Duong Thanh Tin - Test Manabie

## Togo Respository

### Features
The repository have a few main features
```
- Login
- Create user
- Add task by user and create date
```

### Diagrams

1. #### Sequence Diagram For Flow Feature
- Feature Login
![Sequence](https://raw.githubusercontent.com/DuongThanhTin/togo/master/document/Flow-Login.svg)

- Feature Create User
![Sequence](https://raw.githubusercontent.com/DuongThanhTin/togo/master/document/Flow-CreateUser.svg)

- Feature Add Task
![Sequence](https://raw.githubusercontent.com/DuongThanhTin/togo/master/document/Flow-AddTask.svg)

2. #### ERD Diagram

![ERD](https://raw.githubusercontent.com/DuongThanhTin/togo/master/document/ERD.svg)

###  Structure Project

```
- cmd --> Main applications for this project.
  |- middlewares --> Middlewares for this project
- constants --> Contain variable common
- db --> Data for migrations
  |- migrations -> You can migration up or down data
- documents --> Contain detail documents for this project
- integrationtest --> Run integration test
- internal
  |- api --> You can create different output commands like Api rest, web, GRPC or any other technology.
    |- handlers --> Contain API
      |- common --> API for common
      |- tasks --> API for task
      |- users --> API for user
    |- routes --> Make create route for API
  |- driver --> Config connection to database
  |- models --> Application models
  |- pkg --> Make create function to use common
    |- id --> Make create uuid
    |- responses --> Make create many response data
    |- repositories --> Repositoryies will action to database (CRUD)
      |- authorization --> Repository for auth
      |- task --> Repository for task
      |- user --> Repository for user
  |- usecases --> Usecases to implement action for application
    |- authorization --> Usecase for auth
    |- task --> Usecase for task
    |- user --> Usecase for user
```

### How to start

#### Start local
1. Clone repository
```bash
git clone https://github.com/DuongThanhTin/togo.git
cd togo
```

2. Create Database postgres with your config

3. Change data variable in file .env with your config on step 2

4. Install package
```bash
go get -v github.com/manabie-com/togo/...
```

5. Migration database with terminal
```bash
make migration-up
```
6. Run main.go
```bash
go run cmd/main.go
```

#### If you want to integration test after run projection
```bash
	go test ./integrationtest
```

#### If you want to unit test test after run projection
```bash
	go test ./internal/api/handlers/...
```

#### If you want to remove table on database
```bash
  make migration-down
```
