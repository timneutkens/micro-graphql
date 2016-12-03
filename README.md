# Micro-graphql
Example usage of GraphQL with Zeit's micro

```javascript
const { buildSchema } = require('graphql')
const graphqlHTTP = require('express-graphql')

const schema = buildSchema(`
  type Query {
    hello: String
  }
`)

const rootValue = {
  hello: () => 'Hello world'
}

module.exports = graphqlHTTP({
  schema,
  rootValue,
  graphiql: true
})
```
