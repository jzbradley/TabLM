# TabLM
Pronounced "Tablem," a melodic shorthand intended for communicating musical ideas with large language models.

For example, ascending and descending the C major scale in 4/4 time:

```tablm
4/4 C 0e 2e 4e 5e 7e 9e 11e 12e | 12e 11e 9e 7e 5e 4e 2e 0e
```

## Staff Heading
First write the time and root note. If you are familiar with guitar tab, the root would be the open string note.
For example:
```tablm
4/4 E
```
would indicate that the root note is E, without specifying a particular key.

Alternatively, the key signature and mode may be glossed here, as in 3/4 time C Major (ionian):
```tablm
3/4 C Maj
```
Working within music theory may be more efficient and accurate for LLMs - particularly where melodies interact with chord progressions.

For sharp and flat use either # and b respectively or the appropriate the unicode symbols, ♯ and ♭, in order to prevent confusion between the note letter B and the flat symbol.


## Pitch and duration
Each note is formed by specifying a semitone number or hyphen for a rest, followed by a duration letter.

Durations:
w = whole
h = half
q = quarter
e = eighth
s = sixteenth

Ties and slurs shall be surrounded with parenthesis. The following would indicate
1. a note held for a quarter and an eighth
2. an eighth rest
3. a quarter note sliding up to an eighth one semitone higher
4. an eighth rest
```tablm
(2q 2e) -e (2q 3e) -e
```
Alternatively, the "d" modifier can be used to indicate a dotted note. The following would be played the same way:
```tablm
2dq -e (2q 3e) -e
```

To indicate a triplet, start the tie with the "t" modifier and division of each note in the triplet.
So, this phrase
```tablm
ts(1 2 3)
```
would indicate an ascending triplet played in one eighth time.

## Measures
The | symbol indicates that another measure will follow. The ||: and :|| symbols indicate that the surrounded passage should repeat.
As an example, here is a cut time stepwise ascent from the root, played twice
```tablm
2/4 A ||: 0h | 1h | 2h | 3h :||
```

## Glossing

### Chords
Accompanying chords can be indicated in line using square brackets.

Here is an example passage from Nine Inch Nails "La Mer"

```tablm
3/4 C
[C7/B♭] -dq 14e 26e 14e | [C] 24dq 17e 17e 19e |
[E♭6] 19e 12e 12q -e 10e | [Fmaj7/C] 19e 10dq -q |
[E♭6] 9q 10q 12q | [Fmaj7/C] 9h (5q | [A♭] 5h) (0q | [B♭] 0h) -q
```

Alternatively, if the key signature is indicated then we can provide the scale degree for progressions instead:

```tablm
3/4 C Maj
[V4/2/IV] -dq 14e 26e 14e | [I] 24dq 17e 17e 19e |
[min i6/5] 19e 12e 12q -e 10e | [IV4/3] 19e 10dq -q |
[min i6/5] 9q 10q 12q | [IV4/3] 9h (5q | [min ♭VI] 5h) (0q | [min ♭VII] 0h) -q
```
Note the description of chords borrowed from minor scale.

Note that a chord change can accompany a rest, and also need not necessarily appear at the beginning of a measure.

There may be some awkwardness if a change needs to be specified in the middle of a melodic note, in which case a tie could be used.

Here, a measure starts with a C major chord under melodic C, which continues over a change to an E major chord:
```tablm
4/4 C
[C] (0h [E] 0h)
```
