
// hangman
import java.util.*;

class Hang {
    public static void display() {
        ArrayList<String> list = new ArrayList<>(Arrays.asList(
                "python", "javascript", "kotlin", "ruby", "swift", "algorithm",
                "compiler", "database", "encryption", "firewall", "hardware",
                "internet", "java", "kernel", "malware", "network", "object",
                "protocol", "query", "router", "security", "token", "url",
                "virtual", "wireless", "xml", "yaml", "zip", "abstract", "binary",
                "cache", "developer", "ethernet", "framework", "gateway", "hexadecimal",
                "iteration", "juxtapose", "keystroke", "lambda", "metadata", "node"));

        ArrayList<String> clues = new ArrayList<>(Arrays.asList(
                "A popular programming language for data science",
                "A widely-used scripting language for web development",
                "A statically typed language for JVM",
                "A precious stone, also a programming language",
                "A fast programming language for iOS development",
                "A process or set of rules to be followed in problem-solving operations",
                "A program that translates code from high-level to machine language",
                "An organized collection of data",
                "The process of converting information into code",
                "A network security system",
                "The physical components of a computer",
                "A global network connecting millions of private, public, academic, and government networks",
                "A high-level programming language known for its portability",
                "A core component of an operating system",
                "A type of software designed to harm a computer",
                "A collection of computers connected together",
                "An instance of a class",
                "A set of rules for data transmission",
                "A request for information from a database",
                "A networking device that forwards data packets",
                "Measures taken to protect data",
                "An object representing a sequence of characters",
                "A reference to a web resource",
                "Not physically existing but made by software to appear so",
                "Network communications without wires",
                "A markup language for documents",
                "Yet Another Markup Language",
                "A format for compressing data files",
                "Difficult to understand; requiring much thought",
                "A number system using only 0 and 1",
                "A place where data is stored temporarily",
                "A person who writes computer programs",
                "A network technology for connecting devices",
                "A basic structure on which software or hardware can be built",
                "A node that provides an entry point to another network",
                "A numerical representation of a value using base 16",
                "The repetition of a process",
                "To place side by side for comparison",
                "A key on a keyboard",
                "A type of anonymous function",
                "Data that provides information about other data",
                "A point of intersection in a network"));

        ArrayList<String> hang = new ArrayList<>(Arrays.asList(
                """
                         +---+
                         O   |
                        /|\\  |
                        / \\  |
                              |
                        ===""",
                """
                         +---+
                         O   |
                        /|\\ |
                        /    |
                              |
                        ===""",
                """
                         +---+
                         O   |
                        /|\\ |
                             |
                             |
                        ===""",
                """
                         +---+
                         O   |
                        /|   |
                             |
                             |
                        ===""",
                """
                         +---+
                         O   |
                         |   |
                             |
                              |
                        ===""",
                """
                         +---+
                         O   |
                             |
                             |
                             |
                        ===""",
                """
                         +---+
                             |
                             |
                             |
                              |
                        ==="""));

        Random ran = new Random();
        int ran_value = ran.nextInt(list.size());
        String word = list.get(ran_value);

        System.out.println("Welcome to Hang World");
        System.out.println("Your word is size " + word.length());
        System.out.println("Your clue for the word is " + clues.get(ran_value));

        char arr[] = new char[word.length()];
        for (int i = 0; i < word.length(); i++) {
            arr[i] = '_';
        }
        Scanner sc = new Scanner(System.in);

        int tries = 6;
        System.out.println(word);
        int nt = 0;
        char hi = '_';enum

        while (tries > -1) {

            System.out.println(hang.get(tries));
            System.out.println("you have these many trys left" + tries);
            System.out.println("please  guess the letter");
            for (char i : arr) {
                System.out.print(i + " ");
            }
            System.out.println();

            if (nt == 0) {

                hi = sc.next().charAt(0);
            }
            for (char i : arr) {
                if (hi == i) {
                    tries--;
                    continue;
                }
            }
            boolean hello = true;
            for (int i = 0; i < word.length(); i++) {
                if (hi == word.charAt(i)) {
                    arr[i] = hi;
                    hello = false;
                }

            }
            if (hello) {
                System.out.println("sorry you have enter the worng letter");
                tries--;
            }
            boolean bro = true;

            for (char i : arr) {
                if (i == '_') {
                    bro = false;
                    continue;

                }
            }
            if (bro) {
                nt++;
                if (nt == 1) {
                    continue;
                }
                System.out.println("you have win the game");
                System.exit(0);
            }

        }
        System.out.println("you have lost");

    }

    public static void main(String args[]) {
        display();

    }
}




