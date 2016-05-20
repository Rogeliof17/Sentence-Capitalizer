# Sentence-Capitalizer
accepts a string object as an argument and returns a copy of the string with the first character of each sentence capitalized.


import javax.swing.JOptionPane;

public class SentenceCapitalizer
{
    public static void main(String[] args)
    {
        String input;


        input = JOptionPane.showInputDialog(null,
                "Enter any number of sentences and this program will capitalize" +
                        " the first letter of each sentence");

        JOptionPane.showMessageDialog(null, capitalizer(input));

        System.exit(0);

    }

    /**
     * capitalizer method accepts copy of user input then capitalizes
     * the first word of each sentence entered.
     * @param sentence contains a copy of user input
     * @return send back the user input string modified
     */
    public static String capitalizer(String sentence)
    {
        int i;


        StringBuilder string = new StringBuilder(sentence);

        if(string.length() > 0)
            string.setCharAt(0,Character.toUpperCase(string.charAt(0)));

        i = string.indexOf(". ");

        while(i != -1)
        {
            i++;

            while(i < string.length() && string.charAt(i) == ' ')
                i++;

            string.setCharAt(i, Character.toUpperCase(string.charAt(i)));

            i = string.indexOf(". ", i);
        }

        i = string.indexOf("? ");

        while(i != -1)
        {
            i++;

            while(i < string.length() && string.charAt(i) == ' ')
                i++;

            string.setCharAt(i, Character.toUpperCase(string.charAt(i)));

            i = string.indexOf("? ", i);
        }

        i = string.indexOf("! ");

        while(i != -1)
        {
            i++;

            while(i < string.length() && string.charAt(i) == ' ')
                i++;

            string.setCharAt(i, Character.toUpperCase(string.charAt(i)));

            i = string.indexOf("! ", i);
        }

        return string.toString();
    }
}
