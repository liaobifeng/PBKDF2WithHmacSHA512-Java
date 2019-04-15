# PBKDF2WithHmacSHA512-Java
PBKDF2 with HmacSHA512 password cryptography in Java.

[PBKDF2](http://en.wikipedia.org/wiki/PBKDF2)
[HMAC](http://en.wikipedia.org/wiki/Hash-based_message_authentication_code)
[SHA512](http://en.wikipedia.org/wiki/SHA-2)

## Getting Started

### Prerequisites
1. Java 7 or higher

### Installing
No setup is required, the .java file can be directly including into your project.

## Examples
```java
// The password to encrypt 
final String password = "password";

// We need to generate a random Salt before we can encrypt the password
final byte[] salt = PBKDF2WithHmacSHA512.salt();

// Now we hash the password
final byte[] hash = PBKDF2WithHmacSHA512.hash(password, salt);

// That's all we need to do to encrypt the password using PBKDF2WithHmacSHA512.

// Authentication:
final String attemptedPassword = "attemptedPassword"; //would fail as password was set to "password"
boolean valid = PBKDF2WithHmacSHA512.authenticate(attemptedPassword, salt, hash);

if (valid) {
  // The password was correct
} else {
  // The password was incorrect
}
```

*When storing the password you only need to store the salt and hash.*

## Contributing
We are happy to have contributions whether it is for small bug fixes or new pieces of major functionality. To contribute changes, you should first fork the upstream repository to your own GitHub account. You can then add a new remove for upstream and rebase any changes to
make keep up to date with upstream.

`git remote add upstream https://github.com/skdev/PBKDF2WithHmacSHA512-Java.git`

The style guides the project uses is based on the [PSR-2: Coding Style Guide](https://www.php-fig.org/psr/psr-2/)

## Authors
**Suraj Kumar**

## License
This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details
