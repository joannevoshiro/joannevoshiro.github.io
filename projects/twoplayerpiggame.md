---
layout: project
type: project
image: img/twoplayerpiggame.png
title: "Two Player Pig Game"
date: 2022-04-08
published: true
labels:
  - Java
  - Game
summary: "A game devloped for ICS 212 that allows two players can play the two dice pig game."
---

Pig is a simple dice game first described in print by John Scarne in 1945.[1] Players take turns to roll a single dice as many times as they wish, adding all roll results to a running total, but losing their gained score for the turn if they roll a 1. This project creates this game but with two die instead of a singular one. Here is an overview of the rules of the game:

Each turn, a player repeatedly rolls a die until the chosen number is rolled or the player decides to "hold":

If the player rolls the number chosen at the beginning of the game, they score nothing and it becomes the next player's turn.
If the player rolls any other number, it is added to their turn total and the player's turn continues.
If a player chooses to "hold", their turn total is added to their score, and it becomes the next player's turn.
The first player to score 100 or more points wins.

Here is an excerpt from the code:
```
 /**
   * ActionListener for handling the Roll and Hold buttons.
   */
  private class ButtonListener implements ActionListener {
    /*
     * (non-Javadoc)
     * 
     * @see java.awt.event.ActionListener#actionPerformed(java.awt.event.ActionEvent)
     */
    @Override
    
    // set action for buttons when clicked.
    public void actionPerformed(ActionEvent e) {
      if (e.getActionCommand().equalsIgnoreCase("roll")) {
        dice.roll();
        doRules();
      } else if (e.getActionCommand().equalsIgnoreCase("hold")) {
        currentPlayer.setScore(currentPlayer.getScore() + turnScore);
        turnScore = 0;
        if (currentPlayer.getScore() > userWinningTotal) {
          int choice = JOptionPane.showConfirmDialog(currentPlayer.getParent(),
              currentPlayer.getName() + " is the winner.\n Do you want to play again?", "Winner",
              JOptionPane.YES_NO_OPTION);
          if (choice == JOptionPane.NO_OPTION) {
            System.exit(0);
          } else {
            playGame();
          }
        }
        swapPlayers();

      }

    }

  }
```
