# mredis

mredis is a package that provides a Redis client implementation for Go.

## Documentation

[![Go Reference](https://pkg.go.dev/badge/github.com/mixarchitecture/mredis.svg)](https://pkg.go.dev/github.com/mixarchitecture/mredis)

## Installation

You can install the package using the following command:

```shell
go get github.com/mixarchitecture/mredis
```

## Usage

To use the mredis package, import it in your Go code:

```go
import "github.com/mixarchitecture/mredis"
```

## Creating a Redis Client

To create a new Redis client, you need to provide a configuration object (`mredis.Config`) with the necessary connection details:

```go
config := &mredis.Config{
    Host:     "localhost", // Redis server host
    Port:     "6379",      // Redis server port
    Password: "",          // Redis server password (optional)
    DB:       0,           // Redis database number
}

client := mredis.New(config)
```

## Using Redis Service Methods

The `mredis.Service` interface defines various methods to interact with Redis. Here are some examples:

- `Set`: Set the value of a key in Redis.
- `HSet`: Set the values of multiple fields in a Redis hash.
- `Get`: Get the value of a key in Redis.
- `HGet`: Get the value associated with a field in a Redis hash.
- `HGetAll`: Get all fields and values of a Redis hash.
- `SetEx`: Set the value of a key in Redis with an expiration duration.
- `Del`: Delete one or more keys in Redis.
- `Exist`: Check if a key exists in Redis.

```go
// Example usage
value := "Hello, Redis!"
err := client.Set(context.Background(), "mykey", value)
if err != nil {
    // Handle error
}

retrievedValue, err := client.Get(context.Background(), "mykey")
if err != nil {
    // Handle error
}
fmt.Println(retrievedValue) // Output: "Hello, Redis!"
```

Please refer to the GoDoc documentation of the `mredis` package for detailed information about each method and its parameters.

## Contributing

Contributions are welcome! If you find a bug or want to add a new feature, please open an issue or submit a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
