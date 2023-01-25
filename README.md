# ExTypesense

![Hex.pm](https://img.shields.io/hexpm/v/ex_typesense)
[![Hexdocs.pm](https://img.shields.io/badge/hex-docs-lightgreen.svg)](https://hexdocs.pm/ex_typesense/)
![Hex.pm](https://img.shields.io/hexpm/l/ex_typesense)

Typesense client for Elixir with support for importing your Ecto schemas.

## TODO:

- [x] ~import ecto schemas to propagate collections/documents~
- [ ] pre-defined schema and fields
- [ ] creating collection using auto schema detection
- [x] ~implement search~
- [ ] implement multisearch
- [ ] implement geosearch
- [ ] implement curation
- [ ] implement synonyms

## local typesense server

```bash
docker container run --rm -it -d --name typesense -e TYPESENSE_DATA_DIR=/data -e TYPESENSE_API_KEY=xyz -v /tmp/typesense-server-data:/data -p 8108:8108 typesense/typesense:0.23.1
```

## Installation

If [available in Hex](https://hex.pm/docs/publish), the package can be installed
by adding `ex_typesense` to your list of dependencies in `mix.exs`:

```elixir
def deps do
  [
    {:ex_typesense, "~> 0.2.2"}
  ]
end
```

Config for setting up api key, host, etc.

> You can find this in your dashboard if you're using cloud-hosted Typesense

```elixir
config :ex_typesense,
  api_key: "xyz",
  host: "localhost", # "111222333aaabbbcc-9.x9.typesense.net"
  port: 8108, # 443
  scheme: "http" # "https"
  ```

  Then:

  1. create collection (`lib/ex_typesense/collection.ex`)
  2. index a document (`lib/ex_typesense/document.ex`)
  3. try to search (`lib/ex_typesense/document.ex`)

Documentation can be generated with [ExDoc](https://github.com/elixir-lang/ex_doc)
and published on [HexDocs](https://hexdocs.pm). Once published, the docs can
be found at <https://hexdocs.pm/ex_typesense>.