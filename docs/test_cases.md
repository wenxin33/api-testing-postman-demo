# API Test Cases

## TC001 - Get Posts List

* Test case ID: TC001
* Request name: GET posts list
* Method: GET
* Endpoint: `/posts`
* Objective: Verify that the posts list can be retrieved successfully.
* Preconditions:

  * The API service is available.
  * The `base_url` environment variable is configured.
* Test steps:

  1. Send GET request to `/posts`.
  2. Check response status code.
  3. Check response body type.
  4. Check required fields in the first post.
* Expected result:

  * Status code is 200.
  * Response time is less than 3000 ms.
  * Response body is an array.
  * The first item contains `userId`, `id`, `title`, and `body`.

## TC002 - Get Post Detail

* Test case ID: TC002
* Request name: GET post detail
* Method: GET
* Endpoint: `/posts/1`
* Objective: Verify that a specific post can be retrieved successfully.
* Test steps:

  1. Send GET request to `/posts/1`.
  2. Check response status code.
  3. Check whether returned post id equals 1.
  4. Check required fields.
* Expected result:

  * Status code is 200.
  * Response body contains `userId`, `id`, `title`, and `body`.
  * `id` equals 1.

## TC003 - Get Non-existing Post

* Test case ID: TC003
* Request name: GET non-existing post
* Method: GET
* Endpoint: `/posts/999999`
* Objective: Verify API behavior when requesting a non-existing resource.
* Test steps:

  1. Send GET request to `/posts/999999`.
  2. Check response status code.
  3. Check response body.
* Expected result:

  * Status code is 404.
  * Response body is an empty object.

## TC004 - Create Post

* Test case ID: TC004
* Request name: POST create post
* Method: POST
* Endpoint: `/posts`
* Objective: Verify that a post can be created through the API.
* Request body:

```json
{
  "title": "uav path planning test",
  "body": "This is an API testing demo for software testing portfolio.",
  "userId": 1
}
```

* Test steps:

  1. Send POST request to `/posts`.
  2. Check response status code.
  3. Check whether the response contains `id`.
  4. Check whether returned `title`, `body`, and `userId` match the request body.
* Expected result:

  * Status code is 201.
  * Response body contains `id`.
  * Returned data matches the request body.

## TC005 - Update Post

* Test case ID: TC005
* Request name: PUT update post
* Method: PUT
* Endpoint: `/posts/1`
* Objective: Verify that a post can be updated through the API.
* Request body:

```json
{
  "id": 1,
  "title": "updated title",
  "body": "updated body content",
  "userId": 1
}
```

* Test steps:

  1. Send PUT request to `/posts/1`.
  2. Check response status code.
  3. Check whether the returned fields match the request body.
* Expected result:

  * Status code is 200.
  * `id` equals 1.
  * `title` equals `updated title`.
  * `body` equals `updated body content`.
  * `userId` equals 1.

## TC006 - Delete Post

* Test case ID: TC006
* Request name: DELETE post
* Method: DELETE
* Endpoint: `/posts/1`
* Objective: Verify that a post can be deleted through the API.
* Test steps:

  1. Send DELETE request to `/posts/1`.
  2. Check response status code.
  3. Check response body type.
* Expected result:

  * Status code is 200.
  * Response body is an object.
