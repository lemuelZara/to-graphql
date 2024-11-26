# To GraphQL

A simple application to learn about GraphQL.

<br>

How to run app? Is simple, just:

```bash
go run cmd/server/server.go
```

## Queries

```gql
query getAllCategories {
  categories {
    id
    name
  }
}

query getAllCourses {
  courses {
    id
    name
    description
  }
}

query getAllCategoriesWithCourses {
  categories {
    id
    name
    courses {
      id
      name
    }
  }
}

query getAllCoursesWithCategory {
  courses {
    id
    name
    description
    category {
      id
      name
      description
    }
  }
}
```

## Mutations

```gql
mutation createCategory {
  createCategory(
    input: { name: "Gastronomia", description: "Cursos de Gastronomia" }
  ) {
    id
    name
    description
  }
}

mutation createCourse {
  createCourse(
    input: {
      name: "Cozinha criativa"
      description: "Dominando a cozinha"
      categoryId: "ac3796be-1c50-4c68-946b-7e7dec79146c"
    }
  ) {
    id
    name
  }
}
```
