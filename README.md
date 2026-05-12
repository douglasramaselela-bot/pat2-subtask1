# pat2-subtask1
#include <iostream>
#include <string>
#include <cctype>

using namespace std;

int main() {
    
    // Morse code array for A-Z
    string morse[26] = {
        ".-", "-...", "-.-.", "-..", ".", "..-.", "--.", "....",
        "..", ".---", "-.-", ".-..", "--", "-.", "---", ".--.",
        "--.-", ".-.", "...", "-", "..-", "...-", ".--", "-..-",
        "-.--", "--.."
    };

    string message;
    string fullMessage = "";

    cout << "Enter a message in English (A-Z characters only): ";
    getline(cin, message);

    cout << "\nOutput Morse code:\n";

    for (int i = 0; i < message.length(); i++) {
        
        char ch = toupper(message[i]);

        // Ignore spaces
        if (ch == ' ') {
            fullMessage += "   ";
            continue;
        }

        // Check if character is A-Z
        if (ch >= 'A' && ch <= 'Z') {

            string code = morse[ch - 'A'];

            // Display each letter and its Morse code
            cout << ch << ": " << code << endl;

            // Add to full Morse message
            fullMessage += code + "   ";
        }
    }

    // Display full Morse code message
    cout << "\nFull Morse code with spaces:\n";
    cout << fullMessage << endl;

    return 0;
}
