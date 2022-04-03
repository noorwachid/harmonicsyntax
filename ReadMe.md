# Harmonic Syntax
Text editor with agnostic key mapping

NOTE: executable file name "hs"

QUICK PREVIEW:
- Agnostic binding 
- Using kakoune like grammar
- PCRE dialeg instead of Unix or Vim Regex
- Built in treesitter integration
- Built in language server client and completion integration
- Built in fuzzy finder
- Lua scripting API

FROM VIM:
- Fewest key strokes to do something

FROM KAKOUNE:
- Selection first then action

## Agnostic binding

## Modes
  I just like to create new terms for them because It's either somebody uses it or they don't.
  - Change
	- Movement
	- Direct
  - Manipulation
  - ShortHand
    Its basically keymap but for manipulation mode like alias in shell script.
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
2. The most used one are in the home rows. 
3. The second one goes to top rows.
4. And the least used goes to the bottom.

[Action Section]                  [Movement Section]
| 0 | 1 | 2 | 3 | 4 | 5 |         | 6 | 7 | 8 | 9 | 10| 11| 12| 13|
| \`| 1 | 2 | 3 | 4 | 5 |         | 6 | 7 | 8 | 9 | 0 | - | = |
    | Q | W | E | R | T |         | Y | U | I | O | P | [ | ] | | |
    | A | S | D | F | G |         | H | J | K | L | ; | ' | 
    | Z | X | C | V | B |         | N | M | , | . | / | 

The agnostic keymap for settings will notated row then column

# Manipulations
Every manipulation has 4 modes, it dictated by the bit operator.

Imagine the "word" manipulation the default value is "01".
Which means it goes to the end of the word.
If you put make "~word" it'll be "10" and you'll get goes to the begining of the word.

## Action
- Insert
- Delete
- Change (Delete+Insert)
- Copy
- Cut (Copy+Delete)
- Paste
- Swap (Cut+Paste)
- Grab
- Move
- Select
- Touch (Grab+Move)
- Find
  In search mode press enter to finish the pattern or 
  press the tab to make to replacement input then hit enter to replace
  - Find
  - Regex Match
- Replace
  - Replace
  - Regex Placeholder

All maniplation terms is taken from book, and some taken from web terms.

## Movement
- Letter (Character)
- Word (Symbol)
- Sentence (Line)
- Paragraph (Block)
- Page
- Chapter 
- Part
- Book (File)


quick brown fox jumps over the lazy dog
