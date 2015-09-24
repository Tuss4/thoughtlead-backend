# thoughtlead-backend
Vokal Hack DayZZZZZZ

# Contents
+ [Thoughts](#thoughts)
+ [Thought Details](#thought-details)
+ [AfterThoughts](#afterthoughts)
+ [AfterThought Details](#afterthought-details)

**URL ROOT:** `/v1`

# Thoughts
**GET:** `/thoughts/`

**Note(s):**
+ Returns list of users thoughts
+ ThoughtLeader must be authenticated

**Response:**

```json
{
  "results": [
    {
      "id": 1,
      "link": "http://reallydopeinformativelink.com/article.html",
      "teams": [1, 5],
      "thoughtleader": 43,
      "description": "I thought this article was really dope and could help the teams.",
      "creation_date": "2015-09-24"
    },
    ...
  ]
}
```

**Status Codes:**
+ `200` if successful
+ `401` if unauthorized

**POST:** `/thoughts/`

**Note(s):**
+ Create a new thought
+ ThoughtLeader must be authenticated

**Request:**
```json
{
  "link": "http://evenmoredopestuff.com/article.html",
  "teams": [1, 5],
  "description": "This was even better, yo."
}
```

**Response:**
```json
{
  "id": 2,
  "link": "http://evenmoredopestuff.com/article.html",
  "teams": [1, 5],
  "thoughtleader": 43,
  "description": "This was even better, yo.",
  "creation_date": "2015-09-24"
}
```
**Status Codes:**
+ `201` if successful
+ `400` if bad request
+ `401` if unauthorized

# Thought Details
**GET:** `/thoughts/:thought_id/`

**Note(s):**
+ Retrieve a thought
+ ThoughtLeader must be authenticated

**Response:**
```json
{
  "id": 2,
  "link": "http://evenmoredopestuff.com/article.html",
  "teams": [1, 5],
  "thoughtleader": 43,
  "description": "This was even better, yo.",
  "creation_date": "2015-09-24"
}
```

**Status Codes:**
+ `200` if successful
+ `401` if unauthorized
+ `404` if not found

**PATCH:** `/thoughts/:thought_id/`

**Note(s):**
+ Update a thought
+ ThoughtLeader must be authenticated

**Request:**
```json
{
  "description": "This was even better, yo. There's some stuff and things in here."
}
```

**Response:**
```json
{
  "id": 2,
  "link": "http://evenmoredopestuff.com/article.html",
  "teams": [1, 5],
  "thoughtleader": 43,
  "description": "This was even better, yo. There's some stuff and things in here.",
  "creation_date": "2015-09-24"
}
```

**Status Codes:**
+ `200` if successful
+ `400` if bad request
+ `401` if unauthorized

**DELETE:** `/thoughts/:thought_id/`

**Note(s):**
+ Delete a thought
+ ThoughtLeader must be authenticated

**Status Codes:**
+ `204` if successful
+ `401` if unauthorized

# AfterThoughts
**GET:** `thoughts/:thought_id/afterthoughts/`

**Note(s):**
+ Retrieve list of AfterThoughts (comments) on a Thought
+ ThoughtLeader must be authenticated

**Response:**
```json
{
  "results": [
    {
      "id": 1,
      "thought": 2,
      "thoughtleader": 78,
      "creation_date": "2015-9-24",
      "comment": "This was an enriching article. I feel smarter."
    },
    ...
  ]
}
```

**Status Codes:**
+ `200` if successful
+ `401` if unauthorized

**POST:** `thoughts/:thought_id/afterthoughts/`

**Note(s):**
+ Create a new afterthought
+ ThoughtLeader must be authenticated

**Request:**
```json
{
  "comment": "This was an enriching article I feel smarter."
}
```

**Response:**
```json
{
  "id": 1,
  "thought": 2,
  "thoughtleader": 78,
  "creation_date": "2015-9-24",
  "comment": "This was an enriching article. I feel smarter."
}
```

**Status Codes:**
+ `201` if successful
+ `400` if bad request
+ `401` if unauthorized

# AfterThought Details

**PATCH:** `/thoughts/:thought_id/afterthoughts/:afterthought_id/`

**Note(s):**
+ Update an afterthought
+ ThoughtLeader must be authenticated

**Request:**
```json
{
  "comment": "I didn't actually feel that smart. Actually I felt stupider."
}
```

**Response:**
```json
{
  "id": 1,
  "thought": 2,
  "thoughtleader": 78,
  "creation_date": "2015-9-24",
  "comment": "I didn't actually feel that smart. Actually I felt stupider."
}
```

**Status Codes:**
+ `200` if successful
+ `400` if bad request
+ `401` if unauthorized

**DELETE:** `thoughts/:thought_id/afterthoughts/:afterthought_id/`

**Note(s):**
+ Delete an afterthought
+ ThoughtLeader must be authenticated

**Status Codes:**
+ `204` if successful
+ `400` if bad request
+ `401` if unauthorized
