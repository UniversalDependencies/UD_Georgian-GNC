# Summary

UD_Georgian-GNC is a treebank based on texts from the Georgian National Corpus, [GNC](https://clarino.uib.no/gnc).

# Introduction

UD_Georgian-GNC is a treebank based on texts from the Georgian National Corpus, [GNC](https://clarino.uib.no/gnc), which is a corpus of written texts from a variety of genres. The sentences are taken from original and translated novels and from news websites.

The sentences are analysed using a finite state morphological analyser, and Constraint Grammar rules for disambiguation and dependency parsing. Both disambiguation and dependency analyses are corrected manually in a tool specifically developed for that purpose.

# Annotation principles

The lexicon of the morphological analyser is based on Kita Tschenkéli’s Georgisch-Deutsches Wörterbuch; in this dictionary, verbs are listed according to verbal root and, inside each root article, by Verbal Noun (Masdar). Consequently, the Verbal Noun is chosen as the lemma form of inflected finite verbs, and also of participles.

## Arguments of finite verbs

Georgian argument and case syntax is quite complex.

Finite verbs may have up to four actants, two of which may be cross-referenced by affixes in the verb. Depending on verb class and tense, subject and object dependents are marked by Nominative, Ergative or Dative case.
Specifically, indirect objects of active verbs are cross-referenced by nominals in the Dative in the Present and Aorist tense series, but in the Perfect series, they are demoted to obliques marked by the postposition -თვის. For these oblique dependents, the relation label `obl:iobj` is used.

## Verbal noun and participles

### Verbal nouns (VN)

Verbal nouns are treated as nominals (pos = `NOUN`). In many constructions however, VNs retain their verbal force and and are accompanied by arguments. Those arguments are coded differently from arguments of finite verbs.

Argument marking follows an ergative pattern:

* The subject of a transitive verb (A) is marked with the postposition მიერ
* The subject of an intransitive verb (S) and the object of a transitive verb (O) are in the genitive case
* In addition, indirect objects are (in most cases) marked with the postposition -თვის

Since VNs do not code voice (active/passive), the S and O roles cannot be distinguished in VNs if there is no overt A role. It is in addition often difficult to tell wether an attributive genitive should be seen as an argument of the VN or a possessive. Hence a neutral relation label is chosen: `nmod`, or `det` in the case of a posessive pronoun.

For the A role, the label `nmod:agent` is chosen.

Indirect objects are labeled `nmod:iobj`.

For the class of inverted verbs (often verbs of sensation: _love_, _hate_, but also _hear_, _have_), where the subject is marked by the dative and the (direct) object by the nominative, this marking scheme doesn’t fully apply. (We fully adopt Tschenkéli’s classification; in his system, many verbs are classified as inverted that e.g. Rayfield’s dictionary treats as (non-inverted) intransitive verbs with animate indirect object and inanimate subject.)

Inverted verbs are in some sense weakly transitive, as there are very few subject tests that apply, and translations to other languages can go both ways (მომწონს: _ich mag/mir gefällt_ in German). Their verbal nouns are often irregular and have a much more nominal feel to them than those of the more regular verbs.

Here, both the experiencer and the theme role can be coded with the genitive (not simultaneously, of course), and again the label `nmod` is chosen in both cases to cover this vagueness.

### Participles

If participles occur in a periphrastic tense construction with an auxiliary, they are treated as verbs. Otherwise, they are treated as adjectives.

## Person names

In Georgian compound person names (e.g., first + last name), the last element is clearly marked as the head of the noun phrase, as it alone has full case morphology, whereas the preceding elements behave similarly to attributive adjectives. Therefore, names are not analysed as a flat structure, rather, the elements preceding the last one are treated as dependents of the last element, with the relation label `nmod:name`.

## Compatibility with the GNC

In the Georgian National Corpus, a proprietary annotation scheme for lemma forms and morpho-syntactic features is used. The GNC annotations, from which the UD annotations are derived, are are kept in the UD analyses: the original lemma form can be found in the MISC column as value of the LMSeg attribute; the morpho-syntactic features are available in the XPOS column.

# Acknowledgments

The Georgian treebank and the tools used to create it have been developed by Paul Meurer.

# References

* Paul Meurer. [The Morphosyntactic Analysis of Georgian](https://clarino.uib.no/gnc/doc/Morphosyntactic-analysis-of-Georgian.pdf).

# Changelog

* 2025-11-15 v2.17
  * Added sentences to a total of 1772 sentences
  * Added Mood=Ind, other smaller changes

* 2025-05-15 v2.16
  * Initial release in Universal Dependencies, 1531 sentences


<pre>
=== Machine-readable metadata (DO NOT REMOVE!) ================================
Data available since: UD v2.15
License: CC BY-SA 4.0
Includes text: yes
Genre: fiction news
Lemmas: converted from manual
UPOS: converted from manual
XPOS: manual native
Features: converted from manual
Relations: manual native
Contributors: Meurer, Paul
Contributing: elsewhere
Contact: paul.meurer@uib.no
===============================================================================
</pre>
