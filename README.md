# Task Manager API Testing

API testing project using **Postman** and **Newman** against a local **JSON Server** API.

## What is tested

| Resource | Operations |
|---|---|
| Users | GET, POST, PUT, PATCH, DELETE + 404 check after delete |
| Tasks | GET, POST, PUT, PATCH, DELETE + link to a user (`assigneeId`) |

- 15 requests and 52 assertions
- Variables to chain requests (`userId`, `taskId`)
- Pre-request script to generate a random email
- Runs from the terminal with Newman and generates an HTML report

## Project structure

```
api-project/
├── postman/        # Postman collection and environment
├── docs/           # Report screenshot
├── db.json         # Working database
├── db.original.json  # Clean copy of the data
└── package.json
```

## How to run

1. Install dependencies: `npm install`
2. Install Newman globally: `npm install -g newman newman-reporter-htmlextra`
3. Start the API: `npm start` (runs on http://localhost:3002)
4. Reset the data when needed: `npm run reset`
5. Run the tests in another terminal: `npm test`
6. Open `reports/report.html`

You can also import the files from the `postman` folder into Postman and run the collection with the Collection Runner.

## Result

![Newman report](docs/newman-report.png)