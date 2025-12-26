# course-management-api

## Base URL
```
/courses
```

---

## Course Level Endpoints

### 1. List All Courses
**GET** `/courses`

Returns a list of all courses.

**Response:**
```json
[
  {
    "id": "507f1f77bcf86cd799439011",
    "title": "Python Programming",
    "description": "Learn Python from scratch",
    "modules": [...]
  }
]
```

### 2. Get Course by ID
**GET** `/courses/{course_id}`

Get a specific course by its MongoDB ObjectId.

**Parameters:**
- `course_id` (path): MongoDB ObjectId of the course

**Response:**
```json
{
  "id": "507f1f77bcf86cd799439011",
  "title": "Python Programming",
  "description": "Learn Python from scratch",
  "modules": [...]
}
```

### 3. Create Course
**POST** `/courses`

Create a new course.

**Request Body:**
```json
{
  "id": "course-logical-id",
  "title": "Python Programming",
  "description": "Learn Python from scratch",
  "modules": []
}
```

**Response:** 201 Created
```json
{
  "id": "507f1f77bcf86cd799439011",
  "title": "Python Programming",
  "description": "Learn Python from scratch",
  "modules": []
}
```

### 4. Update Course
**PUT** `/courses/{course_id}`

Update an existing course.

**Parameters:**
- `course_id` (path): MongoDB ObjectId of the course

**Request Body:** Same as Create Course

**Response:**
```json
{
  "id": "507f1f77bcf86cd799439011",
  "title": "Updated Title",
  "description": "Updated description",
  "modules": [...]
}
```

### 5. Delete Course
**DELETE** `/courses/{course_id}`

Delete a course.

**Parameters:**
- `course_id` (path): MongoDB ObjectId of the course

**Response:** 200 OK
```json
{
  "ok": true,
  "message": "Course deleted successfully"
}
```

---

## Module Level Endpoints

### 6. Add Module to Course
**POST** `/courses/{course_id}/modules`

Add a new module to a course.

**Parameters:**
- `course_id` (path): MongoDB ObjectId of the course

**Request Body:**
```json
{
  "id": "module-id",
  "title": "Module 1: Introduction",
  "topics": []
}
```

**Response:** 201 Created
```json
{
  "id": "module-id",
  "title": "Module 1: Introduction",
  "topics": []
}
```

### 7. Get Module
**GET** `/courses/{course_id}/modules/{module_id}`

Get a specific module from a course.

**Parameters:**
- `course_id` (path): MongoDB ObjectId of the course
- `module_id` (path): Logical ID of the module

**Response:**
```json
{
  "id": "module-id",
  "title": "Module 1: Introduction",
  "topics": [...]
}
```

### 8. Update Module
**PUT** `/courses/{course_id}/modules/{module_id}`

Update a module in a course.

**Parameters:**
- `course_id` (path): MongoDB ObjectId of the course
- `module_id` (path): Logical ID of the module

**Request Body:** Same as Add Module

**Response:**
```json
{
  "id": "module-id",
  "title": "Updated Module Title",
  "topics": [...]
}
```

### 9. Delete Module
**DELETE** `/courses/{course_id}/modules/{module_id}`

Delete a module from a course.

**Parameters:**
- `course_id` (path): MongoDB ObjectId of the course
- `module_id` (path): Logical ID of the module

**Response:** 200 OK
```json
{
  "ok": true,
  "message": "Module deleted successfully"
}
```

---

## Topic Level Endpoints

### 10. Add Topic to Module
**POST** `/courses/{course_id}/modules/{module_id}/topics`

Add a new topic to a module.

**Parameters:**
- `course_id` (path): MongoDB ObjectId of the course
- `module_id` (path): Logical ID of the module

**Request Body:**
```json
{
  "id": "topic-id",
  "title": "Topic 1: Variables",
  "sub_topics": []
}
```

**Response:** 201 Created
```json
{
  "id": "topic-id",
  "title": "Topic 1: Variables",
  "sub_topics": []
}
```

### 11. Get Topic
**GET** `/courses/{course_id}/modules/{module_id}/topics/{topic_id}`

Get a specific topic from a module.

**Parameters:**
- `course_id` (path): MongoDB ObjectId of the course
- `module_id` (path): Logical ID of the module
- `topic_id` (path): Logical ID of the topic

**Response:**
```json
{
  "id": "topic-id",
  "title": "Topic 1: Variables",
  "sub_topics": [...]
}
```

### 12. Update Topic
**PUT** `/courses/{course_id}/modules/{module_id}/topics/{topic_id}`

Update a topic in a module.

**Parameters:**
- `course_id` (path): MongoDB ObjectId of the course
- `module_id` (path): Logical ID of the module
- `topic_id` (path): Logical ID of the topic

**Request Body:** Same as Add Topic

**Response:**
```json
{
  "id": "topic-id",
  "title": "Updated Topic Title",
  "sub_topics": [...]
}
```

### 13. Delete Topic
**DELETE** `/courses/{course_id}/modules/{module_id}/topics/{topic_id}`

Delete a topic from a module.

**Parameters:**
- `course_id` (path): MongoDB ObjectId of the course
- `module_id` (path): Logical ID of the module
- `topic_id` (path): Logical ID of the topic

**Response:** 200 OK
```json
{
  "ok": true,
  "message": "Topic deleted successfully"
}
```

---

## Sub-Topic Level Endpoints

### 14. Add Sub-Topic to Topic
**POST** `/courses/{course_id}/modules/{module_id}/topics/{topic_id}/sub-topics`

Add a new sub-topic to a topic.

**Parameters:**
- `course_id` (path): MongoDB ObjectId of the course
- `module_id` (path): Logical ID of the module
- `topic_id` (path): Logical ID of the topic

**Request Body:**
```json
{
  "id": "subtopic-id",
  "title": "Understanding Variables",
  "content": []
}
```

**Response:** 201 Created
```json
{
  "id": "subtopic-id",
  "title": "Understanding Variables",
  "content": []
}
```

### 15. Get Sub-Topic
**GET** `/courses/{course_id}/modules/{module_id}/topics/{topic_id}/sub-topics/{subtopic_id}`

Get a specific sub-topic from a topic.

**Parameters:**
- `course_id` (path): MongoDB ObjectId of the course
- `module_id` (path): Logical ID of the module
- `topic_id` (path): Logical ID of the topic
- `subtopic_id` (path): Logical ID of the sub-topic

**Response:**
```json
{
  "id": "subtopic-id",
  "title": "Understanding Variables",
  "content": [...]
}
```

### 16. Update Sub-Topic
**PUT** `/courses/{course_id}/modules/{module_id}/topics/{topic_id}/sub-topics/{subtopic_id}`

Update a sub-topic in a topic.

**Parameters:**
- `course_id` (path): MongoDB ObjectId of the course
- `module_id` (path): Logical ID of the module
- `topic_id` (path): Logical ID of the topic
- `subtopic_id` (path): Logical ID of the sub-topic

**Request Body:** Same as Add Sub-Topic

**Response:**
```json
{
  "id": "subtopic-id",
  "title": "Updated Sub-Topic Title",
  "content": [...]
}
```

### 17. Delete Sub-Topic
**DELETE** `/courses/{course_id}/modules/{module_id}/topics/{topic_id}/sub-topics/{subtopic_id}`

Delete a sub-topic from a topic.

**Parameters:**
- `course_id` (path): MongoDB ObjectId of the course
- `module_id` (path): Logical ID of the module
- `topic_id` (path): Logical ID of the topic
- `subtopic_id` (path): Logical ID of the sub-topic

**Response:** 200 OK
```json
{
  "ok": true,
  "message": "Sub-topic deleted successfully"
}
```

---

## Content Block Level Endpoints

### 18. Add Content Block to Sub-Topic
**POST** `/courses/{course_id}/modules/{module_id}/topics/{topic_id}/sub-topics/{subtopic_id}/content`

Add a new content block to a sub-topic.

**Parameters:**
- `course_id` (path): MongoDB ObjectId of the course
- `module_id` (path): Logical ID of the module
- `topic_id` (path): Logical ID of the topic
- `subtopic_id` (path): Logical ID of the sub-topic

**Request Body:**
```json
{
  "type": "text",
  "value": "This is a text content block",
  "language": null
}
```

Or for code:
```json
{
  "type": "code",
  "value": "print('Hello, World!')",
  "language": "python"
}
```

Or for image:
```json
{
  "type": "image",
  "value": "https://example.com/image.png",
  "language": null
}
```

**Response:** 201 Created
```json
{
  "type": "text",
  "value": "This is a text content block",
  "language": null
}
```

### 19. Update Content Block
**PUT** `/courses/{course_id}/modules/{module_id}/topics/{topic_id}/sub-topics/{subtopic_id}/content/{content_index}`

Update a content block in a sub-topic by its index.

**Parameters:**
- `course_id` (path): MongoDB ObjectId of the course
- `module_id` (path): Logical ID of the module
- `topic_id` (path): Logical ID of the topic
- `subtopic_id` (path): Logical ID of the sub-topic
- `content_index` (path): Zero-based index of the content block

**Request Body:** Same as Add Content Block

**Response:**
```json
{
  "type": "text",
  "value": "Updated content",
  "language": null
}
```

### 20. Delete Content Block
**DELETE** `/courses/{course_id}/modules/{module_id}/topics/{topic_id}/sub-topics/{subtopic_id}/content/{content_index}`

Delete a content block from a sub-topic by its index.

**Parameters:**
- `course_id` (path): MongoDB ObjectId of the course
- `module_id` (path): Logical ID of the module
- `topic_id` (path): Logical ID of the topic
- `subtopic_id` (path): Logical ID of the sub-topic
- `content_index` (path): Zero-based index of the content block

**Response:** 200 OK
```json
{
  "ok": true,
  "message": "Content block deleted successfully"
}
```

---

## Legacy Endpoint

### Get Topic by Logical ID (across all courses)
**GET** `/courses/topics/{topic_id}`

Get a topic by its logical ID, searching across all courses.

**Parameters:**
- `topic_id` (path): Logical ID of the topic

**Response:**
```json
{
  "id": "topic-id",
  "title": "Topic Title",
  "sub_topics": [...]
}
```

---

## Error Responses

All endpoints return standard HTTP status codes:

- **200 OK**: Successful GET, PUT, DELETE operations
- **201 Created**: Successful POST operations
- **400 Bad Request**: Invalid request (e.g., duplicate ID)
- **404 Not Found**: Resource not found

**Error Response Format:**
```json
{
  "detail": "Error message describing what went wrong"
}
```

---

## Example Usage

### Create a complete course structure:

1. **Create Course:**
```bash
POST /courses
{
  "id": "python-course",
  "title": "Python Programming",
  "description": "Learn Python",
  "modules": []
}
```

2. **Add Module:**
```bash
POST /courses/{course_id}/modules
{
  "id": "module1",
  "title": "Basics",
  "topics": []
}
```

3. **Add Topic:**
```bash
POST /courses/{course_id}/modules/module1/topics
{
  "id": "topic1",
  "title": "Variables",
  "sub_topics": []
}
```

4. **Add Sub-Topic:**
```bash
POST /courses/{course_id}/modules/module1/topics/topic1/sub-topics
{
  "id": "subtopic1",
  "title": "Understanding Variables",
  "content": []
}
```

5. **Add Content Block:**
```bash
POST /courses/{course_id}/modules/module1/topics/topic1/sub-topics/subtopic1/content
{
  "type": "text",
  "value": "Variables store data values.",
  "language": null
}
```

---

## Notes

- All IDs at the module/topic/sub-topic level are logical IDs (strings), not MongoDB ObjectIds
- Course IDs use MongoDB ObjectIds
- Content blocks are accessed by zero-based index
- All endpoints validate that parent resources exist before allowing operations
- Duplicate IDs are not allowed at the same level (e.g., two modules with the same ID in one course)


