# SHA-512 in Java

An educational Java implementation of SHA-512 that exposes the hashing pipeline through dedicated preprocessing, message-schedule, compression-round, and digest classes.

## Hashing pipeline

```text
Input file → PreProcessor → WordGenerator → Compression rounds → SHA-512 digest
```

| Class | Responsibility |
| --- | --- |
| `PreProcessor` | Prepare the input message for block-based hashing |
| `WordGenerator` | Construct the words used by the compression rounds |
| `Function` | Supporting bitwise and arithmetic operations |
| `Round` | Execute the compression-round calculations |
| `SHA` | Coordinate processing and expose the hash result |
| `MainClass` | Read the configured input file, print the digest, and write its text output |

This decomposition makes the relationship between message preparation and iterative state transformation visible, providing an algorithm-focused complement to library-based hashing.

## Explore and run

Open `SHA512/` as a Java project with a JDK and mark `src/` as the source root. The driver is `mainPackage.MainClass`; its input and output locations are the absolute paths declared in that class. The repository also supplies example files under `SHA512/src/files/`.

Compile the implementation from the repository root:

```bash
javac -d /tmp/sha512-classes SHA512/src/mainPackage/*.java SHA512/src/othersPackage/*.java
```

Run `mainPackage.MainClass` in an environment providing the driver's configured file locations. It prints the hash and writes its 128-character hexadecimal representation.

## Authors

Yasin Sazid (BSSE 1006) and Abdullah-Al-Jahid (BSSE 1030).
