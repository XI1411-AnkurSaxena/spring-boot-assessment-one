### Story 1:  Create Spring Boot application

### Story 2: REST API to create an article

`POST /api/articles`

Example request body:

```JSON
{
    "title": "Spring Booot",
    "description": "Ever wonder how?",
    "body": "You have to believe",
    "tags": ["Technical", "java", "Spring Boot"]
}
```

Required fields: `title`, `description`, `body`

Optional fields: `tags` as an array of Strings

Tags should be saved as lowercase.

Response

1. It will return response code 201 if article is created successfully

2. It will return 400 if validation failed

3. It will return 500 if anything else happened

4. It will return created article as shown below.

   ```json
   {
       "id": "a98fd991e69a",
       "slug": "spring-boot",
       "title": "Spring Booot",
       "description": "Ever wonder how?",
       "body": "You have to believe",
       "tags": ["technical", "java", "spring boot"],
       "createdAt": "2023-03-10T03:22:56.637Z",
       "updatedAt": "2023-03-10T03:48:35.824Z"
   }
   ```
   
### Story 3: List articles

`GET /api/articles`

1. It should support pagination. 

2. It should should support sorting on the basis of tags.

   Sending a tag name as a sorting parameter in the request should reflect a list of articles with those articles on the top which contains the given tag
   
   /api/articles?sort-tag=technical
   

   ```json
   [{
       "id": "a98fd991e69a",
       "slug": "spring-boot",
       "title": "Spring Booot",
       "description": "Ever wonder how?",
       "body": "You have to believe",
       "tags": ["technical", "java", "spring boot"],
       "createdAt": "2023-03-10T03:22:56.637Z",
       "updatedAt": "2023-03-10T03:48:35.824Z"
   },
   {
       "id": "b48sd121fa0x",
       "slug": "how-to-cook-pasta",
       "title": "How to cook pasta",
       "description": "Are you hungry?",
       "body": "You need to see this recepie right now!",
       "tags": ["food", "italian", "recepie"],
       "createdAt": "2023-03-11T03:22:56.637Z",
       "updatedAt": "2023-03-11T03:48:35.824Z"
   }]
   ```


