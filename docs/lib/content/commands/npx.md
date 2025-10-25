#include <iostream>
#include <string>
#include <ctime>
#include <cstdlib>

using namespace std;

// Функция для получения текущего времени
string getTime() {
    time_t now = time(0);
    tm *ltm = localtime(&now);
    char buffer[80];
    strftime(buffer, sizeof(buffer), "%H:%M:%S", ltm);
    return string(buffer);
}

// Функция для получения даты
string getDate() {
    time_t now = time(0);
    tm *ltm = localtime(&now);
    char buffer[80];
    strftime(buffer, sizeof(buffer), "%d.%m.%Y", ltm);
    return string(buffer);
}

int main() {
    string command;

    cout << "==============================\n";
    cout << " 🤖  Zafar Assistant v1.0\n";
    cout << "==============================\n";
    cout << "Type 'help' to see available commands.\n\n";

    while (true) {
        cout << "You: ";
        getline(cin, command);

        if (command == "exit" || command == "quit") {
            cout << "Assistant: Goodbye, Zafar! 👋\n";
            break;
        } 
        else if (command == "hello") {
            cout << "Assistant: Hello, Zafar! How are you today?\n";
        } 
        else if (command == "time") {
            cout << "Assistant: The current time is " << getTime() << endl;
        } 
        else if (command == "date") {
            cout << "Assistant: Today’s date is " << getDate() << endl;
        } 
        else if (command == "creator") {
            cout << "Assistant: I was created by Zafar using C++! 🔥\n";
        }
        else if (command == "help") {
            cout << "Assistant: Available commands:\n";
            cout << "  hello   - Greet the assistant\n";
            cout << "  time    - Show current time\n";
            cout << "  date    - Show today’s date\n";
            cout << "  creator - Show information about the creator\n";
            cout << "  exit    - Quit the assistant\n";
        }
        else {
            cout << "Assistant: Sorry, I don’t understand that command. Type 'help' for options.\n";
        }
    }

    return 0;
}
