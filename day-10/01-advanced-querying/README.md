# Advanced Querying with Sequelize

## Overview

In this lesson, we will learn how to perform advanced querying with Sequelize. We will cover filtering, sorting, pagination, and performing complex queries using Sequelize's query interface.

## Filtering

To filter records, use the `where` option in your query. You can specify conditions to match records based on attribute values.

### Example: Filtering Records

```javascript
// filter-posts.js
const { Sequelize, DataTypes } = require('sequelize')
const sequelize = new Sequelize('test_db', 'root', 'password', {
  host: 'localhost',
  dialect: 'mysql'
})

const Post = sequelize.define('Post', {
  title: {
    type: DataTypes.STRING,
    allowNull: false
  },
  content: {
    type: DataTypes.TEXT,
    allowNull: false
  }
})

async function filterPosts() {
  await sequelize.sync()

  const posts = await Post.findAll({
    where: {
      title: 'First Post'
    }
  })
  console.log('Filtered posts:', JSON.stringify(posts, null, 2))

  await sequelize.close()
}

filterPosts()
```

## Sorting

To sort records, use the `order` option in your query. You can specify the attributes to sort by and the sorting direction (ASC or DESC).

### Example: Sorting Records

```javascript
// sort-posts.js
const { Sequelize, DataTypes } = require('sequelize')
const sequelize = new Sequelize('test_db', 'root', 'password', {
  host: 'localhost',
  dialect: 'mysql'
})

const Post = sequelize.define('Post', {
  title: {
    type: DataTypes.STRING,
    allowNull: false
  },
  content: {
    type: DataTypes.TEXT,
    allowNull: false
  }
})

async function sortPosts() {
  await sequelize.sync()

  const posts = await Post.findAll({
    order: [
      ['title', 'ASC']
    ]
  })
  console.log('Sorted posts:', JSON.stringify(posts, null, 2))

  await sequelize.close()
}

sortPosts()
```

## Pagination

To paginate records, use the `limit` and `offset` options in your query. The `limit` option specifies the maximum number of records to return, and the `offset` option specifies the number of records to skip.

### Example: Paginating Records

```javascript
// paginate-posts.js
const { Sequelize, DataTypes } = require('sequelize')
const sequelize = new Sequelize('test_db', 'root', 'password', {
  host: 'localhost',
  dialect: 'mysql'
})

const Post = sequelize.define('Post', {
  title: {
    type: DataTypes.STRING,
    allowNull: false
  },
  content: {
    type: DataTypes.TEXT,
    allowNull: false
  }
})

async function paginatePosts() {
  await sequelize.sync()

  const posts = await Post.findAll({
    limit: 2,
    offset: 1
  })
  console.log('Paginated posts:', JSON.stringify(posts, null, 2))

  await sequelize.close()
}

paginatePosts()
```

## Complex Queries

Sequelize allows you to perform complex queries using a combination of filtering, sorting, and pagination. You can also use raw SQL queries if needed.

### Example: Complex Query

```javascript
// complex-query.js
const { Sequelize, DataTypes } = require('sequelize')
const sequelize = new Sequelize('test_db', 'root', 'password', {
  host: 'localhost',
  dialect: 'mysql'
})

const Post = sequelize.define('Post', {
  title: {
    type: DataTypes.STRING,
    allowNull: false
  },
  content: {
    type: DataTypes.TEXT,
    allowNull: false
  }
})

async function complexQuery() {
  await sequelize.sync()

  const posts = await Post.findAll({
    where: {
      title: {
        [Sequelize.Op.like]: '%Post%'
      }
    },
    order: [
      ['title', 'ASC']
    ],
    limit: 2,
    offset: 1
  })
  console.log('Complex query result:', JSON.stringify(posts, null, 2))

  await sequelize.close()
}

complexQuery()
```

## Conclusion

In this lesson, we explored how to perform advanced querying with Sequelize. We covered filtering, sorting, pagination, and performing complex queries. 

## Exercise

[Exercise: Advanced Querying with Sequelize](exercise.md)
