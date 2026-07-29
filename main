
import art
print(art.logo)

alphabet = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm',
            'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z']

def translate(lan):
    """Returns the prompt strings based on the selected language ('e' or 'd')."""
    if lan == "e":
        return {
            "direction": "Type 'encode' to encrypt, type 'decode' to decrypt:\n",
            "text": "Type your message:\n",
            "shift": "Type the shift number:\n",
            "restart": 'Type "y" to continue or "n" to exit:\n',
            "result": "Here is the result:",
            "invalid_dir": "Invalid direction!",
            "invalid_shift": "Invalid shift!",
            "empty_text": "Message cannot be empty.",
            "invalid_restart": "Invalid!"
        }
    elif lan == "d":
        return {
            "direction": "Tippe 'encode' zur Verschlüsselung oder 'decode' zur Entschlüsselung:\n",
            "text": "Tippe deine Nachricht:\n",
            "shift": "Tippe die Verschiebungsnummer:\n",
            "restart": 'Tippe "y" zum Weitermachen oder "n" zum Abbrechen:\n',
            "result": "Hier ist das Ergebnis:",
            "invalid_dir": "Ungültige Richtung!",
            "invalid_shift": "Ungültige Verschiebung!",
            "empty_text": "Die Nachricht darf nicht leer sein.",
            "invalid_restart": "Ungültig!!"
        }
    return None

def caesar(original_text, shift_amount, encode_or_decode):
    """Encrypts or decrypts text using the Caesar Cipher algorithm."""
    output_text = ""
    if encode_or_decode == "decode":
        shift_amount *= -1

    for letter in original_text:
        if letter not in alphabet:
            output_text += letter
        else:
            shifted_position = alphabet.index(letter) + shift_amount
            shifted_position %= len(alphabet)
            output_text += alphabet[shifted_position]

    return output_text

# --- Main Game Loop ---
should_continue = True

while should_continue:
    # 1. Language Selection Loop
    lan = input("Please select your language (E for English or D for Deutsch):\n").lower()
    prompts = translate(lan)
    
    if prompts is None:
        print("Invalid language! / Ungültige Sprache!")
        continue

    # 2. Direction Validation Loop
    while True:
        direction = input(prompts["direction"]).lower()
        if direction in ["encode", "decode"]:
           break
        print(prompts["invalid_dir"])

    # 3. Text Validation Loop
    while True:
        text = input(prompts["text"]).lower()
        if len(text) != 0:
           break
        print(prompts["empty_text"])

    # 4. Shift Validation Loop
    while True:
        shift_input = input(prompts["shift"])

        if shift_input.isdigit():
            shift = int(shift_input)
            break

        print(prompts["invalid_shift"])

    # 5. Process and Display Result
    result = caesar(original_text=text, shift_amount=shift, encode_or_decode=direction)
    print(f"\n{prompts['result']} {result}\n")

    # 6. Restart Condition
    while True:
        restart = input(prompts["restart"]).lower()
        if restart in ["n", "no"]:
            should_continue = False
            print(art.bye)
            break
        elif restart in ["y", "yes"]:
            break
        else:
            print(prompts["invalid_restart"])





