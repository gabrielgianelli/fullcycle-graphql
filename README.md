# FULL CYCLE

## Comunicação entre sistemas

### GraphQL

Código das aulas de GraphQL do módulo de Comunicação entre sistemas do curso Full Cycle

#### Geração dos resolvers

> go run github.com/99designs/gqlgen generate

#### Execução do projeto

> go run cmd/grpcServer/server.go

#### GraphQL Playground

> http://localhost:8080/

#### Exemplos de chamadas

```
mutation createCategory {
  createCategory(input: {name: "Tecnologia", description: "Cursos de Tecnologia"}) {
    id
    name
    description
  }
}

mutation createCourse {
  createCourse(input: {name: "Full Cycle", description: "The best!", categoryId: "bc3e37ee-9c7c-4e16-801a-a22a18b2e46e"}) {
    id
    name
    description
  }
}

query queryCategories {
  categories {
    id
    name
    description
  }
}

query queryCategoriesWithCourses {
  categories {
    id
    name
    description
    courses {
      id
      name
    }
  }
}

query queryCourses {
  courses {
    id
    name
    description
  }
}

query queryCoursesWithCategory {
  courses {
    id
    name
    description
    category{
      id
      name
    }
  }
}
```