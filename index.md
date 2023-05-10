# **Lab Report 3 **
## By Marvin Peralta, A17271264

## The GREP command

### Variation 1: `grep -i <pattern> <file path>`

```
grep -i may technical/plos/journal.pbio.0020001.txt

output between the developing and already developed countries (Gibbs 1995; May 1997;
the world (Gibbs 1995; May 1997; Alonso and Fernández-Juricic 2001; Vohora and Vohora
assessing scientific productivity or technical advances (May 1997). More relevant
and development (May 1997). The proportional change in the number of publications, using
may also have increased the relative number of publications in Latin America. In contrast,
target the journals that have the greatest impact. Although there may still be a long road
```
```
grep -i recommendations technical/government/Alcohol_Problems/DraftRecom-PDF.txt

Draft Recommendations
recommendations from conference deliberations. Before the
conference, he and Daniel Pollock drafted recommendations for the
committee modified those recommendations, and they were distributed
achieve unanimity regarding the recommendations, but to have
be to discuss the recommendations one by one, identifying any gaps
sequence of the recommendations did not imply a priority order.
Because the published recommendations will include supporting text,
Gordon Smith suggested that the recommendations should address
recommendations.
to patients. Perhaps the recommendations should address alcohol
Edward Bernstein pointed out that the recommendations would
research recommendations with a recommendation that included
Daniel Pollock added that the message of the recommendations
clinicians understand the recommendations better. If we do not, a
Catherine Gordon proposed that the recommendations address the
recommendations to the high-risk environment in which these people
explicit somewhere in the recommendations.
Ries thought that the recommendations should encourage studying
Pat Lenaghan suggested that clinicians need recommendations
General comments about the recommendations
proposed recommendations, Hungerford asked if they had general
comments about the recommendations overall.
```

The -i add-on ignores whether the string provided has uppercase or lowercase letters - all lines in the file containing the string will be printed out. It can be helpful when you are looking for words that should be capitalized, lowercase, or just trying to find the lines that the word pops up in a text file.

### Variation 2: `grep -w <pattern> <file path>`

```
grep -w a technical/biomed/1468-6708-3-3.txt

is an important issue as the risk of a recurrent adverse
63 hours) of admission for unstable angina or a non-Q-wave
discharge. The primary efficacy endpoint was a composite of
was 124 mg/dL. Atorvastatin treatment was associated with a
for a number of reasons. Although lipid-lowering therapy
was associated with a significantly lower mortality when
identify a short-term (ie, within 16 weeks) clinical
remove a major obstacle to the inpatient initiation of
a number of inherent study limitations worth noting. First
and foremost, the possibility of a null treatment effect
troubling. While it is impressive that a clinical benefit
There were also a number of limitations that may have
Nevertheless, a number of trials have established the
revascularization [ 9 10 11 ] . Furthermore, a number of
Q-waves represent a substantial proportion of all patients
with a non-Q-wave myocardial infarction, it is still much
shortly before or after a coronary event, who present with
a Q-wave myocardial infarction, who are treated with
could still make a compelling argument that lipid-lowering
unstable angina or a non-Q wave myocardial infarction. In
combination therapy [ 30 ] and determine whether there is a
Dr Aronow has received honoraria as a speaker and
advisory board member for Pfizer and as a speaker for
```
```
grep -w 11 technical/911report/chapter-13.1.txt

That is now the job of the generation that experienced 9/11. Those attacks showed,
Some of the saddest aspects of the 9/11 story are the outstanding efforts of so many
Much of the public commentary about the 9/11 attacks has dealt with "lost
opportunities,"some of which we reviewed in chapter 11. These are often
"connecting the dots." In chapter 11 we explained that these labels are too narrow.
Since 9/11, those issues have not been resolved. In some ways joint work has gotten
mistakes of 9/11. They try to share information. They circulate-even to the
Before 9/11, the CIA was plainly the lead agency confronting al Qaeda. The FBI
Counterterrorist Center that played such a key role before 9/11. A third major
already become 50 percent larger since 9/11. But our impression, after talking
have become apparent before and after 9/11:
Congress after 9/11. An unintended consequence of these developments has been
Before 9/11, the CIA did not invest in developing a robust capability to
The post-9/11 Afghanistan precedent of using joint CIA-military teams for
office" side of government operations. In the 9/11 story, for example, we sometimes
9/11 between intelligence and law enforcement has opened up new opportunities
FBI's top priority, two years after 9/11 we also found gaps between some of the
```

The -w add-on makes it so that whatever string is being searched for, only searches for the string as a word.
For example: if "is" is searched for, lines containing "this" or "miss" will not qualify to be printed after the command is inputted. It's important to use this command when a word is really common within other words like "a" or "I".

### Variation 3: `grep -l <pattern> <file path>`

```
grep -l 9/11 technical/911report/chapter-*

technical/911report/chapter-1.txt
technical/911report/chapter-10.txt
technical/911report/chapter-11.txt
technical/911report/chapter-12.txt
technical/911report/chapter-13.1.txt
technical/911report/chapter-13.2.txt
technical/911report/chapter-13.3.txt
technical/911report/chapter-13.4.txt
technical/911report/chapter-13.5.txt
technical/911report/chapter-2.txt
technical/911report/chapter-3.txt
technical/911report/chapter-5.txt
technical/911report/chapter-6.txt
technical/911report/chapter-7.txt
technical/911report/chapter-8.txt
technical/911report/chapter-9.txt
```
```
grep -l AIDS technical/plos/*.txt

technical/plos/journal.pbio.0020052.txt
technical/plos/journal.pbio.0020187.txt
technical/plos/journal.pbio.0020307.txt
technical/plos/journal.pbio.0030076.txt
technical/plos/pmed.0010010.txt
technical/plos/pmed.0010034.txt
technical/plos/pmed.0010036.txt
technical/plos/pmed.0010041.txt
technical/plos/pmed.0010070.txt
technical/plos/pmed.0010071.txt
technical/plos/pmed.0020002.txt
technical/plos/pmed.0020016.txt
technical/plos/pmed.0020023.txt
technical/plos/pmed.0020028.txt
technical/plos/pmed.0020035.txt
technical/plos/pmed.0020036.txt
technical/plos/pmed.0020039.txt
technical/plos/pmed.0020050.txt
technical/plos/pmed.0020099.txt
technical/plos/pmed.0020118.txt
technical/plos/pmed.0020182.txt
technical/plos/pmed.0020216.txt
technical/plos/pmed.0020246.txt
technical/plos/pmed.0020247.txt
technical/plos/pmed.0020249.txt
technical/plos/pmed.0020257.txt
technical/plos/pmed.0020278.txt
```

The -l add-on displays the name of the files that contain the pattern that is searched for. This is really helpful when you're looking for specific files instead of lines inside the files that contain the pattern (where you don't even know which files the lines are from).

### Variation 4:`grep -o <pattern> <file path>`

```
grep -o Management technical/government/About_LSC/Comments_on_semiannual.txt
Management
Management
Management
Management
Management
Management
Management
Management
```

```
grep -o "Management*\|w\S*" technical/government/About_LSC/Comments_on_semiannual.txt

working
with
work
which
wide.1
ws
ways
which
w-income
w
ws
w
which
w
w
wide.
with
with
ware
which
will
with
who
was
with
which
will
ward
wide
with
while
well
will
which
ws
was
wenty-five
ward,
within
weights
with
www.ain.lsc.gov.
w
w
ways
w-income
wing
warding
with
wenty-three
wide
web
would
with
wide
web
Management
ware
was
Management
with
wide
with
written
ws.
w
while
ws.
ws
w
were
was
wo
wo
will
work,
which
work
with
work
will
work.
w
wing
work,
web
work.
was
wing
will
which
was
with
which
wer,
well
who
were
written
was
with
wenty-eight
were
wide
will
will
will
workshop
was
were
work
were
when
with
Management
workshop
ways
which
w
with
with
will
w
work
within
Management
with
w
w
which
will
will
ween
will
would
where
wsuit
which
was
w
w
with
which,
wing
w
way
Management
Management
Management
Management
```
The -o add-on displays only the part of the line in which the pattern is present. If you want to count, -o is a good substitute for the wc (word count) command. Also, with more complex parameters, the -o add-on becomes more helpful, showing substrings of words inside lines and even sentences between two words.

Source:

[The Geek Stuff](https://www.thegeekstuff.com/2009/03/15-practical-unix-grep-command-examples/)

[ChatGPT](https://chat.openai.com)
