# Demo: Building a RESTful API with Express

## Objective
Learn how to build a RESTful API using Express, which adheres to best practices in API design and provides a standardized approach for CRUD operations on resources.

## Introduction to RESTful APIs
RESTful APIs (Representational State Transfer) are an architectural style for designing networked applications. They rely on a stateless, client-server, cacheable communications protocol — and in virtually all cases, the HTTP protocol is used.

## Step 1: Set Up Your Express App
Start with a basic Express setup. If you haven't already, create a basic Express server.

## Step 2: Define a Model
For demonstration purposes, let's use a simple in-memory array to simulate a database of books.

```javascript
let books = [
    { id: 1, title: '1984', author: 'George Orwell' },
    { id: 2, title: 'The Great Gatsby', author: 'F. Scott Fitzgerald' }
]
```

## Step 3: Implement CRUD Operations
Create endpoints that allow clients to perform CRUD operations on the \`books\` resource.

### GET All Books
```javascript
app.get('/books', (req, res) => {
    res.status(200).json(books)
})
```

### GET a Single Book by ID
```javascript
app.get('/books/:id', (req, res) => {
    const book = books.find(b => b.id === parseInt(req.params.id))
    if (!book) res.status(404).send('The book was not found')
    res.status(200).json(book)
})
```

### POST a New Book
```javascript
app.post('/books', (req, res) => {
    const { title, author } = req.body
    const book = {
        id: books.length + 1,
        title,
        author
    }
    books.push(book)
    res.status(201).send(book)
})
```

### PUT Update an Existing Book
```javascript
app.put('/books/:id', (req, res) => {
    const book = books.find(b => b.id === parseInt(req.params.id))
    if (!book) res.status(404).send('The book was not found')

    const { title, author } = req.body
    book.title = title
    book.author = author
    res.status(200).send(book)
})
```

### DELETE a Book
```javascript
app.delete('/books/:id', (req, res) => {
    const index = books.findIndex(b => b.id === parseInt(req.params.id))
    if (index === -1) res.status(404).send('The book was not found')

    books.splice(index, 1)
    res.status(204).send()
})
```

## Step 4: Test Your API
Use tools like Postman or curl to test the API endpoints. Ensure that they correctly handle CRUD operations and respond with appropriate HTTP status codes.

## Exercise

[Exercise: Create a RESTful API with Express](exercise.md)