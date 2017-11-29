# Algorithms - Breaking the Caesar Cipher

Any substitution cipher \(where letters are substituted for other letters - e.g. Caesar Cipher\) can be broken, given enough information. The reason for this is that certain letters in the English language appear more frequently than others. The following graph describes the relative frequencies of each letter in English usage

|  | ![](/assets/480px-EnglishLanguageFrequency-slf.png) |  |
| :--- | :---: | :--- |


A simple method to attempt to break/decipher the Caesar Cipher is to find the most common letter in the encrypted text. Ideally that letter will represent the letter 'E', so that letter's position in the alphabet relative to the letter 'E' should be the shift of the original Caesar Cipher.  The first step in breaking the cipher is to be able to count how many of each letter occurs in a string.

## Counting How Many of Each Letter Occurs in a String

Suppose we have stored the first few paragraphs of Charles Dickens' story "A Christmas Carol" in a string called **text**.

```
text = """Marley was dead, to begin with. There is no doubt whatever about that.
The register of his burial was signed by the clergyman, the clerk, the
undertaker, and the chief mourner. Scrooge signed it. And Scrooge's name
was good upon 'Change for anything he chose to put his hand to. Old
Marley was as dead as a door-nail.

Mind! I don't mean to say that I know, of my own knowledge, what there
is particularly dead about a door-nail. I might have been inclined,
myself, to regard a coffin-nail as the deadest piece of ironmongery in
the trade. But the wisdom of our ancestors is in the simile; and my
unhallowed hands shall not disturb it, or the Country's done for. You
will, therefore, permit me to repeat, emphatically, that Marley was as
dead as a door-nail.

Scrooge knew he was dead? Of course he did. How could it be otherwise?
Scrooge and he were partners for I don't know how many years. Scrooge
was his sole executor, his sole administrator, his sole assign, his
sole residuary legatee, his sole friend, and sole mourner. And even
Scrooge was not so dreadfully cut up by the sad event, but that he was
an excellent man of business on the very day of the funeral, and
solemnised it with an undoubted bargain.

The mention of Marley's funeral brings me back to the point I started
from. There is no doubt that Marley was dead. This must be distinctly
understood, or nothing wonderful can come of the story I am going to
relate. If we were not perfectly convinced that Hamlet's Father died
before the play began, there would be nothing more remarkable in his
taking a stroll at night, in an easterly wind, upon his own ramparts,
than there would be in any other middle-aged gentleman rashly turning
out after dark in a breezy spot--say St. Paul's Church-yard, for
instance--literally to astonish his son's weak mind.

Scrooge never painted out Old Marley's name. There it stood, years
afterwards, above the warehouse door: Scrooge and Marley. The firm was
known as Scrooge and Marley. Sometimes people new to the business called
Scrooge Scrooge, and sometimes Marley, but he answered to both names. It
was all the same to him.

Oh! but he was a tight-fisted hand at the grindstone, Scrooge! a
squeezing, wrenching, grasping, scraping, clutching, covetous, old
sinner! Hard and sharp as flint, from which no steel had ever struck out
generous fire; secret, and self-contained, and solitary as an oyster.
The cold within him froze his old features, nipped his pointed nose,
shrivelled his cheek, stiffened his gait; made his eyes red, his thin
lips blue; and spoke out shrewdly in his grating voice. A frosty rime
was on his head, and on his eyebrows, and his wiry chin. He carried his
own low temperature always about with him; he iced his office in the
dog-days; and didn't thaw it one degree at Christmas.

External heat and cold had little influence on Scrooge. No warmth could
warm, no wintry weather chill him. No wind that blew was bitterer than
he, no falling snow was more intent upon its purpose, no pelting rain
less open to entreaty. Foul weather didn't know where to have him. The
heaviest rain, and snow, and hail, and sleet could boast of the
advantage over him in only one respect. They often "came down"
handsomely and Scrooge never did.

Nobody ever stopped him in the street to say, with gladsome looks, "My
dear Scrooge, how are you? When will you come to see me?" No beggars
implored him to bestow a trifle, no children asked him what it was
o'clock, no man or woman ever once in all his life inquired the way to
such and such a place, of Scrooge. Even the blind men's dogs appeared to
know him; and, when they saw him coming on, would tug their owners into
doorways and up courts; and then would wag their tails as though they
said, "No eye at all is better than an evil eye, dark master!"

But what did Scrooge care? It was the very thing he liked. To edge his
way along the crowded paths of life, warning all human sympathy to keep
its distance, was what the knowing ones call "nuts" to Scrooge.

Once upon a time--of all the good days in the year, on Christmas
Eve--old Scrooge sat busy in his counting-house. It was cold, bleak,
biting weather: foggy withal: and he could hear the people in the court
outside go wheezing up and down, beating their hands upon their breasts,
and stamping their feet upon the pavement stones to warm them. The City
clocks had only just gone three, but it was quite dark already--it had
not been light all day--and candles were flaring in the windows of the
neighbouring offices, like ruddy smears upon the palpable brown air. The
fog came pouring in at every chink and keyhole, and was so dense
without, that, although the court was of the narrowest, the houses
opposite were mere phantoms. To see the dingy cloud come drooping down,
obscuring everything, one might have thought that nature lived hard by
and was brewing on a large scale.

The door of Scrooge's counting-house was open, that he might keep his
eye upon his clerk, who in a dismal little cell beyond, a sort of tank,
was copying letters. Scrooge had a very small fire, but the clerk's fire
was so very much smaller that it looked like one coal. But he couldn't
replenish it, for Scrooge kept the coal-box in his own room; and so
surely as the clerk came in with the shovel, the master predicted that
it would be necessary for them to part. Wherefore the clerk put on his
white comforter, and tried to warm himself at the candle; in which
effort, not being a man of strong imagination, he failed.

"A merry Christmas, uncle! God save you!" cried a cheerful voice. It was
the voice of Scrooge's nephew, who came upon him so quickly that this
was the first intimation he had of his approach.

"Bah!" said Scrooge. "Humbug!"

He had so heated himself with rapid walking in the fog and frost, this
nephew of Scrooge's, that he was all in a glow; his face was ruddy and
handsome; his eyes sparkled, and his breath smoked again."""
```

Notice the use of the **triple quotes** to store a **multi-line string** in Python.  We can utilize the string method** count\(\)** to count each letter as we **loop **through a string representing the alphabet.  The following code

```
upperCaseText = text.upper()
for letter in "ABCDEFGHIJKLMNOPQRSTUVWXYZ":
	n = upperCaseText.count(letter)
	freq = n / len(text) * 100
	print("Letter: {} Frequency: {:3.2f} %".format(letter, freq) )
```

will produce the output

```
Letter: A Frequency: 6.34 %
Letter: B Frequency: 1.08 %
Letter: C Frequency: 2.29 %
Letter: D Frequency: 3.68 %
Letter: E Frequency: 9.32 %
Letter: F Frequency: 1.41 %
Letter: G Frequency: 1.99 %
Letter: H Frequency: 4.85 %
Letter: I Frequency: 5.10 %
Letter: J Frequency: 0.02 %
Letter: K Frequency: 0.72 %
Letter: L Frequency: 3.21 %
Letter: M Frequency: 1.99 %
Letter: N Frequency: 5.48 %
Letter: O Frequency: 6.48 %
Letter: P Frequency: 1.28 %
Letter: Q Frequency: 0.07 %
Letter: R Frequency: 4.63 %
Letter: S Frequency: 5.20 %
Letter: T Frequency: 6.36 %
Letter: U Frequency: 2.00 %
Letter: V Frequency: 0.57 %
Letter: W Frequency: 2.24 %
Letter: X Frequency: 0.07 %
Letter: Y Frequency: 1.60 %
Letter: Z Frequency: 0.07 %
```

that indicates the frequency of each letter in the **text **string. Notice a couple features of the program.  The code

```
upperCaseText = text.upper()
```

converts the **text **string to all _**uppercase **_letters and stores the new string in the variable **upperCaseText**.  This is done because the alphabet we are looping through consists only of uppercase letters.

