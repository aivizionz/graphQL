# graphQL

## GRAPHQL  
1. https://docs.github.com/en/graphql/overview/explorer 

### 1. GraphQL Using  Query -  Fields, Arguments, Alias, Fragments and Operation Name 

``` shell
query viewerInfo1 {
  viewer {
    login
    bio
    id
    name
    firstfollowers: following(first: 3) {
      nodes {
        ...userInfo
      }
    }
    lastfollowers: following(last: 3) {
      nodes {
        ...userInfo
      }
    }
  }
}

```

``` shell
fragment userInfo on User {
  id
  name
  bio
  bioHTML
  avatarUrl
}
```


### 2. GraphQL Using  Query - Variables

``` shell
query viewerInfo2($isOwner: Boolean!) {
  viewer {
    id
    name
    starredRepositories(ownedByViewer: $isOwner, last: 3) {
      nodes {
        id
        name
      }
    }
  }
}
```

Query Variables for query  viewerInfo2:
``` shell
{
  "isOwner": false
}
```


``` shell
query viewerInfo3 {
  viewer {
    id
    name
    status {
      id
      message
    }
  }
}

```

### 3. Using GraphQL Mutation

``` shell
mutation NewStatus($input: ChangeUserStatusInput!) {
  changeUserStatus (input: $input) {
    clientMutationId
    status {
      message
    }
  }
}

```

Query Variables for mutation NewStatus
``` shell
{
  "input": {
    "clientMutationId": "10101002",
    "message": "Working on Blockchain"
  }
}
```



## GraphQL clients:
1. Apollo:  https://github.com/learnapollo/learnapollo
2. Relay: https://github.com/learnrelay/learnrelay
3. URQL:   https://formidable.com/open-source/urql/docs/ 

## links
1. https://formidable.com/open-source/urql/docs/comparison/
2. https://graphqlconf.org/


## GraphQL  Server:
1. Apollo Server
2. Express GraphQL
3. GraphQL yoga

## Database to GraphQL
1. Prisma https://github.com/prisma

## Tools
1. GraphiQL
2. GraphQL Voyager
3. GraphQL Faker
4. GraphQL  Visual editor

## Resources
1. https://learn.microsoft.com/en-us/shows/graphql/
