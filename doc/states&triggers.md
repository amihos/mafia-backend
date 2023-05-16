# states of the game:

- Introduction state
- Day state
- Night state
- Endgame state

# triggers

- Player actions: Players taking in-game actions such as voting to lynch a player or the Mafia choosing to kill a player can trigger state changes.
- Time events: Time events such as the end of the day phase or the end of the night phase can trigger state changes.
- Win conditions: When a win condition is met, such as the Mafia successfully killing enough town members or the town successfully lynching all the Mafia members, the game will transition to the endgame state.

# actions:
- Vote to lynch: During the day phase, players can vote on who they believe is a Mafia member and should be lynched.
- Choose a player to kill: During the night phase, the Mafia can choose a player to kill.
- Investigate a player: Some roles in the game can investigate other players to determine their alignment (town or Mafia).
- Use special abilities: Some roles in the game have special abilities they can use, such as protecting a player from being killed or framing another player as a member of the Mafia. 



| State        | Vote to Lynch | Choose Player to Kill | Investigate Player | Use Special Ability |
|--------------|---------------|-----------------------|--------------------|---------------------|
| Introduction | No            | No                    | No                 | No                  |
| Day          | Yes           | No                    | No                 | No                  |
| Night        | No            | Yes                   | Yes                | Yes                 |
| Endgame      | No            | No                    | No                 | No                  |

graph TD;
  A[Introduction state] -->|Start game| B[Day state];
  B -->|Vote to Lynch| C[Night state];
  C -->|Choose Player to Kill| B;
  B -->|Vote to Lynch or Win condition| D[Endgame state];
  D -->|Start new game| A;
