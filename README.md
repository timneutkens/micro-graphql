# Micro-graphql
Example usage of GraphQL with Zeit's micro

## Installation

`npm install -g micro` or `yarn global add micro`

## Usage

Create an `index.js` file with the following contents:

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

Then run
`micro index.js`

## Boilerplates

[Kennet Postigo](https://github.com/kennetpostigo) made an excellent boilerplate based on the example above:
[hyperfuse/micro-graphql](https://github.com/hyperfuse/micro-graphql)
