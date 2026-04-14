# Rental App Custom Utility Library

A custom Java utility library developed for the AccommodateMe property rental platform.

## Features

- **AESEncryptor** - AES-256-GCM authenticated encryption/decryption with random IV
- **EncryptedFieldConverter** - JPA AttributeConverter for transparent field-level encryption
- **ImageThumbnailUtil** - Aspect-ratio-preserving JPEG thumbnail generation using Java2D
- **InputSanitizer** - Input validation and sanitization to prevent XSS and injection attacks

## Installation

Add to your `pom.xml`:

```xml
<repositories>
    <repository>
        <id>github</id>
        <name>GitHub Packages</name>
        <url>https://maven.pkg.github.com/YOUR_GITHUB_USERNAME/rental-app-custom-util-library</url>
    </repository>
</repositories>

<dependencies>
    <dependency>
        <groupId>com.example</groupId>
        <artifactId>rental-app-custom-util-library</artifactId>
        <version>1.0.0</version>
    </dependency>
</dependencies>
```

## Usage

```java
// AES Encryption
AESEncryptor encryptor = new AESEncryptor(base64Key);
String encrypted = encryptor.encrypt("sensitive data");
String decrypted = encryptor.decrypt(encrypted);

// Input Sanitization
String safe = InputSanitizer.sanitizeShort(userInput, "fieldName");
String email = InputSanitizer.sanitizeEmail(emailInput);

// Thumbnail Generation
byte[] thumbnail = ImageThumbnailUtil.generateThumbnail(imageBytes);
```

## Publishing

```bash
mvn clean deploy
```

## Author

Amjith Krishnan UJ (x25139088)
