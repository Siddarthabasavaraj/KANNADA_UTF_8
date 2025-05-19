# kannada_paragraph_utf_linearprint.py

# Python code to replace ottaksharas with linear aksharas
# Kannada paragraph (4 lines)
kannada_text = """ನಮಸ್ಕಾರ ಗೆಳೆಯರೆ!
ನಾನು ಕನ್ನಡ ಭಾಷೆ ಓದುತ್ತೇನೆ.
ಇದು ನನ್ನ ಪ್ರಿಯ ಭಾಷೆ.
ನಮಗೆ ಕನ್ನಡ ತುಂಬಾ ಪ್ರೀತಿಯದ್ದು."""

# Print the paragraph
print("Kannada Paragraph:")
print(kannada_text)
print("\nCharacter-wise Unicode and UTF-8 bytes:\n")
print("Character | Unicode Code Point | UTF-8 Bytes")
print("----------------------------------------------")

# Save the paragraph to a UTF-8 encoded text file
file=open("kannada_linear_ottakshara.txt", "w", encoding="utf-8")

for char in kannada_text:
    if char.strip() == "":  # Skip spaces and newlines
        print(char, end="")  # Preserve it as is
        file.write(char)
    elif (ord(char) >= 3200) and (ord(char) <= 3327):  # Fixed range
        print(char, end="")
        file.write(char)
    else:
        print("\n" + char, end="")
        file.write("\n" + char)

file.close()
print("\n\nFile saved successfully as kannada_linear_ottakshara.txt with UTF-8 encoding.")
