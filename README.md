#include <iostream>
#include <map>
#include <string>
#include <cctype>

using namespace std;

int main() {
    // Define Morse code mappings
    map<char, string> morseCode = {
        {'A', ".-"},   {'B', "-..."}, {'C', "-.-."}, {'D', "-.."},
        {'E', "."},    {'F', "..-."}, {'G', "--."},  {'H', "...."},
        {'I', ".."},   {'J', ".---"}, {'K', "-.-"},  {'L', ".-.."},
        {'M', "--"},   {'N', "-."},   {'O', "---"},  {'P', ".--."},
        {'Q', "--.-"}, {'R', ".-."},  {'S', "..."},  {'T', "-"},
        {'U', "..-"},  {'V', "...-"}, {'W', ".--"},  {'X', "-..-"},
        {'Y', "-.--"}, {'Z', "--.."},
        {'0', "-----"},{'1', ".----"},{'2', "..---"},{'3', "...--"},
        {'4', "....-"},{'5', "....."},{'6', "-...."},{'7', "--..."},
        {'8', "---.."},{'9', "----."}
    };

    string input;

    cout << "Enter your message (letters and numbers only): ";
    getline(cin, input);

    cout << "Morse Code: ";

    for (char c : input) {
        if (c == ' ') {
            cout << " / "; // Slash to separate words
        } else {
            c = toupper(c); // Convert to uppercase
            if (morseCode.count(c)) {
                cout << morseCode[c] << " ";
            } else {
                cout << "? "; // Unknown character
            }
        }
    }

    cout << endl;
    return 0;
}
