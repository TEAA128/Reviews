## Server API

### Get review info
  * GET `room/:roomid/reviews/`

**Path Parameters:**
  * `roomid`  roomid

**Success Status Code:** `200`

**Returns:** JSON

```json
    {
       "ID": 12132
       "cleanliness": 5,
       "communication": 2,
       "check_in": 3,
       "accuracy": 4,
       "location": 3,
       "value": 3
       "date": "2017-06-15",
       "text": "not bad, not great",
       "userID": 324234,
       "roomID": 232,
       "username": "Jeff",
        "image": "https://s3.amazonaws.com/uifaces/faces/twitter/sreejithexp/128.jpg",
       "roomname": "Adam's place"  
    }
```

### Add review
  * POST `/reviews`

**Success Status Code:** `201`

**Request Body**: Expects JSON with the following keys.

```json
     {
        "scores": {
            "cleanliness": 5,
            "communication": 2,
            "check_in": 3,
            "accuracy": 4,
            "location": 3,
            "value": 3
        },
        "_id": "5f08a6331f4175e8f2440265",
        "_roomId": 23,
        "user_name": "Bettie",
        "user_image": "https://s3.amazonaws.com/uifaces/faces/twitter/sreejithexp/128.jpg",
        "user_url": "https://www.youtube.com/watch?v=dQw4w9WgXcQ",
        "date": "2020-06-02T15:12:04.728Z",
        "text": "We need to reboot the optical FTP sensor!",
        "__v": 0
    }
```


### Update review info
  * PATCH `/api/review/:id`

**Path Parameters:**
  * `id` review id

**Success Status Code:** `204`

**Request Body**: Expects JSON with any of the following keys (include only keys to be updated)

```json
    {
        "scores": {
            "cleanliness": 5,
            "communication": 2,
            "check_in": 3,
            "accuracy": 4,
            "location": 3,
            "value": 3
        },
        "_id": "5f08a6331f4175e8f2440265",
        "_roomId": 23,
        "user_name": "Bettie",
        "user_image": "https://s3.amazonaws.com/uifaces/faces/twitter/sreejithexp/128.jpg",
        "user_url": "https://www.youtube.com/watch?v=dQw4w9WgXcQ",
        "date": "2020-06-02T15:12:04.728Z",
        "text": "We need to reboot the optical FTP sensor!",
        "__v": 0
    }
```

### Delete review
  * DELETE `reviews/:id`

**Path Parameters:**
  * `id` review id

**Success Status Code:** `204`

