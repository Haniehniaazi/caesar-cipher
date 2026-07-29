# Caesar Cipher (Python)

## Overview

This project is a simple **Caesar Cipher** application written in Python. It allows users to **encrypt** and **decrypt** messages by shifting letters in the alphabet by a specified number of positions.

The program supports **English** and **German** user interfaces and includes input validation to ensure a smooth user experience.

---

## Features

* Encrypt messages using the Caesar Cipher.
* Decrypt encrypted messages.
* English and German language support.
* Validates user input:

  * Language selection
  * Encryption/Decryption mode
  * Empty messages
  * Shift values
  * Restart option
* Preserves spaces, punctuation, and numbers without modification.
* Supports unlimited shift values using modulo arithmetic.

---

## How It Works

The Caesar Cipher shifts each alphabetical character by a specified number of positions.

Example:

* Original: `hello`
* Shift: `3`
* Encrypted: `khoor`

For decryption, the program simply shifts the letters in the opposite direction.

Characters that are **not letters** (spaces, punctuation, numbers, etc.) remain unchanged.

---

## Requirements

* Python 3.x

The project also requires an `art.py` file containing the variables:

* `logo`
* `bye`

These are used to display the welcome and exit banners.

---

## Running the Program

Run the program with:

```bash
python main.py
```

---

## Example

```
Please select your language (E for English or D for Deutsch):
e

Type 'encode' to encrypt, type 'decode' to decrypt:
encode

Type your message:
hello world

Type the shift number:
5

Here is the result:
mjqqt btwqi

Type "y" to continue or "n" to exit:
```

---

## Project Structure

```
project/
│
├── main.py
├── art.py
└── README.md
```

---

## Functions

### `translate(lan)`

Returns all prompts and messages based on the selected language.

Parameters:

* `lan` (`"e"` or `"d"`)

Returns:

* Dictionary containing localized text.

---

### `caesar(original_text, shift_amount, encode_or_decode)`

Encrypts or decrypts a message using the Caesar Cipher algorithm.

Parameters:

* `original_text` – The message to process.
* `shift_amount` – Number of positions to shift.
* `encode_or_decode` – `"encode"` or `"decode"`.

Returns:

* Processed string.

---

## Input Validation

The application checks for:

* Valid language selection.
* Valid operation (`encode` or `decode`).
* Non-empty messages.
* Numeric shift values.
* Valid restart choice (`y` or `n`).

If invalid input is entered, the user is prompted again until a valid value is provided.

---

## License

This project is intended for educational purposes and can be freely modified or extended.
