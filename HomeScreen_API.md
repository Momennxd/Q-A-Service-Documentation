
# Home Screen
Home screen APIs

## Collections
public collections APIs that will apear on Home Screen

#### Get Top 20 Collections 

```http
GET /api/HomeScreen/Top20Collections
```
Request body
- **Parameters**: None

Response body
| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| SendCollectionDTO | SendCollectionDTO[ ] | List of collections




### Example Response Body
```json
[
  {
    "collectionName": "string",
    "description": "string",
    "isPublic": true,
    "collectionID": 0,
    "addedTime": "2024-10-28T09:29:16.499Z",
    "categories": [
      "string"
    ]
  }
]

```
