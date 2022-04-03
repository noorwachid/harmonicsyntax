# Harmonic Syntax
Text editor with agnostic key mapping

NOTE: It's still an idea
NOTE: Executable file name "hs"

QUICK PREVIEW:
- Agnostic binding 
- Using kakoune like grammar
- Using PCRE dialeg instead of Unix or Vim Regex
- Built in treesitter integration
- Built in language server client and completion integration
- Built in fuzzy finder
- Lua scripting API

FROM VIM:
- Fewest key strokes to do something

FROM KAKOUNE:
- Selection first then action
  - Add toggle to show the selection.

## Agnostic binding

## Modes
  I just like to create new terms for them because It's either somebody use my program or they don't.
  - Manipulation
    The core mode, Its directly call core manipulation functions.
  - Movement
    Calling maniplation through key mapping.
    Navigate the code base.
  - Selection
    The movement basically select the move this is like vim visual mode to perform like column selection.
	- Selection
	  ```
	  Quick brown fox jumps [over the lazy dog.
	  And the chicken] are wondering why.
	  ```
	- Column Selection
	  ```
	  Quick brown fox jumps [ove]r the lazy dog.
	  And the chicken are wo[nde]ring why.
	  ```
	- Row Selection
	  ```
	  [Quick brown fox jumps over the lazy dog.]
	  And the chicken are wondering why.
	  ```
  - Search
    Find pattern in current file or the entire folder and perform replace.
  - Direct
    Editing the file.
  - ShortHand
    It's like key mapping but for manipulation mode like alias in shell script.
	Instead of the editor define the shorthands the user can make anything they like.

## Change Mode
### Key Mapping
Qwerty, dvorak and colemak uses the same key placement instead of the same character.
All keyboard shortcuts using key placement instead of character. 
For me it made more sense to have "hjkl" like in dvorak's home row rather than scatered all over the place.
And most of programmers touch-type rather than looking over the keyboard.

All of the manipulations can be entered through manipulation mode.

More like dvorak all editor manipulations go:
1. Separate the movement and action (vowels and consonants).
   Though you can change them.
2. The most used one are in the home rows. 
3. The second one goes to top rows.
4. And the least used goes to the bottom.

```
[Action Section]                  [Movement Section]
| 0 | 1 | 2 | 3 | 4 | 5 |         | 6 | 7 | 8 | 9 | 10| 11| 12| 13|
| ` | 1 | 2 | 3 | 4 | 5 |         | 6 | 7 | 8 | 9 | 0 | - | = |
    | Q | W | E | R | T |         | Y | U | I | O | P | [ | ] | | |
    | A | S | D | F | G |         | H | J | K | L | ; | ' | 
    | Z | X | C | V | B |         | N | M | , | . | / | 
```

The agnostic keymap for settings will notated row then column

- insert
- delete
- change
- copy
- cut: copy paste
- paste: clipboard.read
- swap (cut+paste)
- grab
- touch (grab+move)

- jump

- peek
  open other file without actually leaving the current file
- select
- find
  in search mode press enter to finish the pattern or 
  press the tab to make to replacement input then hit enter to replace
  - find
  - regex match
- replace
  - replace
  - regex placeholder

# Manipulations
## Action API

- Clipboard
  - Clipboard.read
  - Clipboard.write
  - Clipboard.clear

- View
  ```
  +---+----------------------------------+
  | 1 |                                  |
  | 2 |                                  |
  | 3 |                                  |
  | 4 |                                  |
  | 5 |                                  |
  | 6 |                                  |
  +---+----------------------------------+
  ```

  - FloatView
  Same as view but the position is not dependent to view container but it still bound to the container.

  - ModalView
  Same as FloatView but it is completely dependent. 

  - TabView
    ```
    +------------+--------------+----------+
    | active     | inactive     |      < > |
    +------------+--------------+----------+
    |                                      |
    |                                      |
    |                                      |
    |                                      |
    +--------------------------------------+
    ```
  - VerticalSplitView
    ```
    +-----------------+--------------------+
    | active          | inactive           |
    +-----------------+--------------------+
    |                 |                    |
    |                 |                    |
    |                 |                    |
    |                 |                    |
    +-----------------+--------------------+
    ```
  - HorizontalSplitView
    ```
    +--------------------------------------+
    | active                               |
    +--------------------------------------+
    |                                      |
    |                                      |
    +--------------------------------------+
    | inactive                             |
    +--------------------------------------+
    |                                      |
    |                                      |
    +--------------------------------------+
    ```

- ASCII
  - ASCII.Case.toUpper
  - ASCII.Case.toLower
  - ASCII.Case.toTitle
  - ASCII.Case.toCamel
  - ASCII.Case.toPascal
  - ASCII.Case.toSnake
  - ASCII.Case.toScreamingSnake
  - ASCII.Case.toKebab

- Algorithm
  - Algorithm.sort
  - Algorithm.filter
  - Algorithm.map

- File
  - File.read
  - File.write
  - File.close

- Buffer
  - Buffer.moveCursor


## Movement
- CodePoint
  codepoint
- symbol
- line
- block


quick brown fox jumps over the lazy dog
