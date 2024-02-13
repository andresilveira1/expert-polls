<h1 align="center">Expert Polls</h1>

This app is a real-time voting system developed during [Rocketseat](https://www.rocketseat.com.br/) NLW event.

- Create polls.
- Vote in poll.
- A system to count votes in real-time.
- Update votes in real-time.

## Requisites

- [Docker](https://docs.docker.com/get-docker/)
- [Node.js](https://nodejs.org/en)

## To Execute

Run the following commands.

```bash
  git clone https://github.com/andresilveira1/expert-polls.git

  npm install

  docker compose up -d

  npm run dev
```

## HTTP

## POST`/polls`

Create a new poll.

Request body

```json
{
  "title": "Which is the best Node.js framework?",
  "options": ["Express", "Fastify", "NextJS", "HapiJS"]
}
```

Response body

```json
{
  "pollId": "4f123bfe-4a15-45c5-9c20-71af7c7a8c8c"
}
```

## GET`/polls/:pollId`

Return data from a single poll.

Response body

```json
{
  "poll": {
    "id": "4f123bfe-4a15-45c5-9c20-71af7c7a8c8c",
    "title": "Qual o melhor framework Node.js?",
    "options": [
      {
        "id": "e2a59ac1-b14c-4b9c-9857-e7d0ef1d3456",
        "title": "Express",
        "score": 0
      },
      {
        "id": "a02c4127-3834-4f31-af9b-aa110eec66e1",
        "title": "Fastify",
        "score": 1
      },
      {
        "id": "c5652d5f-ee72-43d0-b2b1-1b67d1e3c43c",
        "title": "NextJS",
        "score": 0
      },
      {
        "id": "c1d15230-7ce8-4653-82a5-127e21dc8bb6",
        "title": "HapiJS",
        "score": 0
      }
    ]
  }
}
```

## POST`/polls/:pollId/votes`

Add a vote to specific poll

Request body

```json
{
  "pollOptionId": "a02c4127-3834-4f31-af9b-aa110eec66e1"
}
```

## WebSockets

ws`/polls/:pollId/results`

```json
{
  "pollOptionId": "a02c4127-3834-4f31-af9b-aa110eec66e1",
  "votes": 1
}
```
