# Java named recognition 
About name recognition 
import java.util.*;

public class NameRecognition {

    
    private static final Set<String> knownNames = new HashSet<>(Arrays.asList(
        "Ahmed", "Mohammed", "Sara", "Mona", "Ali", "Fatima", "Omar", "Huda"
    ));

    public static List<String> recognizeNames(String text) {
        List<String> foundNames = new ArrayList<>();
        String[] words = text.split("\\s+");

        for (String word : words) {
           
            word = word.replaceAll("[^a-zA-Z]", "");

            
            if (knownNames.contains(word)) {
                foundNames.add(word);
            }
        }

        return foundNames;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println(" :");
        String input = scanner.nextLine();

        List<String> names = recognizeNames(input);

        if (names.isEmpty()) {
            System.out.println("");
        } else {
            System.out.println(" :");
            for (String name : names) {
                System.out.println("- " + name);
            }
        }
    }
}