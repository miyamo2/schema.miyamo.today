# schema.miyamo.today

[![GitHub](https://img.shields.io/github/license/miyamo2/blogschema)](https://img.shields.io/github/license/miyamo2/blogschema)

GraphQL Schema for simply blog application.

This schema implements [Relay GraphQL cursor connection specification](https://relay.dev/graphql/connections.htm).

## Installation

```sh
git clone https://github.com/miyamo2/schema.miyamo.today
```

as submodule

```sh
git submodule add https://github.com/miyamo2/schema.miyamo.today
```

## Usage

### Building GraphQL server with gqlgen

1. Initialize your repo & go module

```sh
mkdir myblog
cd ./myblog
git init
git submodule add https://github.com/miyamo2/schema.miyamo.today blogschema
go mod init myblog
```

2. Setup gqlgen

```sh
go install github.com/99designs/gqlgen@latest
gqlgen init
go mod tidy
```

3. Edit gqlgen.yml

```diff
schema:
    - - graph/*.graphqls
    + - blogschema/**/*.graphqls
```

4. Generate skelton with blogschema

```.sh
gqlgen generate
```
