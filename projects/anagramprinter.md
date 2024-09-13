---
layout: project
type: project
image: img/anagram.jpeg
title: "Anagram Printer"
date: 2021-12-10
published: true
labels:
  - Java
summary: "A project that I created for an ICS 111 assignment."
---

The definition of an anagram is as follows:
an·a·gram
/ˈanəˌɡram/
noun
a word, phrase, or name formed by rearranging the letters of another, such as cinema, formed from iceman.

In this program, I call the user to input a word, it takes the word, then outputs all possible anagrams for that word. It is a very simple code.
Here is the code in its entirety, since it's not much:
``
import java.util.Scanner;

/*
 * Represents a PrintAnagrams.
 *
 * @author Joanne Oshiro
 *
 */
public class PrintAnagrams {

    /*
     * A Program That Prints All Anagrams Of A Word.
     * 
     * @param args
     */
    public static void main(String[] args) {
        Scanner Scan = new Scanner(System.in);
        System.out.print("Anagrams For: ");
        String Input = Scan.nextLine();
        Scan.close();

        printAnagrams(Input);
    }

    /*
     *  Print's Anagrams Of A Word.
     * 
     * @param Word The Word To Print Anagrams Of.
     * 
     */
    public static void printAnagrams(String Word) {
        printAnagrams("", Word);
    }

    /*
     *  Print's Anagrams Of A Word.
     * 
     * @param Prefix Set To "" For Correct Usage.
     * @param Word The Word To Print Anagrams Of.
     * 
     */
    private static void printAnagrams(String Prefix, String Word) {
        if (Word.length() == 1) {
            System.out.println(Prefix + Word);
        }
        else {
            for (int i = 0; i < Word.length(); i++) {
                String newPrefix = Prefix + Word.charAt(i);
                String newWord = Word.substring(0, i) + Word.substring(i + 1);
                printAnagrams(newPrefix, newWord);
            }
        }
    }

} 
``
Here is also an example of how the input and the resulting output would look like:
Anagrams For: abcd
abcd
abdc
acbd
acdb
adbc
adcb
bacd
badc
bcad
bcda
bdac
bdca
cabd
cadb
cbad
cbda
cdab
cdba
dabc
dacb
dbac
dbca
dcab
dcba
