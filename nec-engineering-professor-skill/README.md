# NEC Engineering Professor

A Claude skill that turns Claude into a professor and exam coach for the Nepal Engineering Council (NEC) registration (license) examination, Computer Engineering syllabus (ACtE).

> **Unofficial study aid.** This project is not affiliated with or endorsed by Nepal Engineering Council. Check every exam rule against NEC's own notices before you rely on it.

## What it does

- **Teaches the whole syllabus.** All 10 chapters and 60 sub-chapters of the official ACtE syllabus are built in. Lessons go one concept at a time, with a question after each.
- **Sets NEC-style questions.** Four-option, one-mark MCQs with explanations, plus numericals, code tracing and short answers.
- **Matches the official model set.** Question style, level and paper layout follow an analysis of NEC's official 100-question model set. The skill describes that set but does not contain its questions.
- **Runs mock exams.** Full (100 questions), half (50) or single-chapter papers, delivered in blocks of 10, with no answers until you submit.
- **Tracks mastery.** Five levels per sub-chapter with numeric criteria, an error log and a spaced revision schedule.
- **Carries progress between chats.** Claude prints a short progress record. You save it and paste it back next time.
- **Stays honest about sources.** It never presents its own questions as past NEC questions, and it teaches NEC law and Nepal tax topics from the actual text.

The skill is a single Markdown file. It contains no scripts and makes no network calls. Read `SKILL.md` before installing, as you should with any skill.

## Install

### Claude (web, desktop, mobile)

1. Download `nec-engineering-professor.zip` from this repository.
2. In Claude, check that code execution and file creation is turned on (Settings > Capabilities).
3. Go to **Customize > Skills**, click **+**, choose **Create skill**, then **Upload a skill**, and upload the ZIP.
4. Check that the skill is toggled on in your skills list.

Menu names change from time to time. If these steps do not match what you see, follow [Use skills in Claude](https://support.claude.com/en/articles/12512180-use-skills-in-claude).

If you build the ZIP yourself, it must contain the `nec-engineering-professor` folder at its root, with `SKILL.md` inside that folder.

### Claude Code

Copy the `nec-engineering-professor` folder to `~/.claude/skills/` to use it everywhere, or to `.claude/skills/` inside one project. Claude loads it when you mention the exam, or you can type `/nec-engineering-professor`.

## Use

Start a new chat and mention the exam so the skill loads:

```
NEC START
```

| Command | What it does |
|---|---|
| `START` | Loads your progress record, or starts a new one |
| `SYLLABUS`, `SYLLABUS U5` | Shows the chapters, or one chapter's sub-chapters and topics |
| `TEACH U3`, `TEACH 5.3`, `TEACH subnetting` | Teaches from that point |
| `CONTINUE` | Resumes the current lesson |
| `EXPLAIN AGAIN` | Re-explains the current concept a different way |
| `HINT` | Gives a hint without the answer |
| `ASSESS` | 3 to 5 questions to place your level |
| `QUIZ`, `QUIZ U7 15` | MCQs, one at a time with feedback |
| `PRACTICE` | Numericals, code tracing and short answers |
| `REVISION` | Reviews whatever is due |
| `WEAK AREAS` | Ranks your weakest sub-chapters with a short fix for each |
| `MOCK EXAM`, `MOCK EXAM HALF`, `MOCK EXAM U4` | Runs an exam simulation |
| `PROGRESS` | Shows your dashboard |
| `REPORT` | Full report plus your updated progress record |

Plain language works too: "teach me deadlock" or "give me 10 questions on normalization".

### Keeping your progress

Claude does not remember earlier chats on its own. When you stop, type `REPORT`. Claude prints a progress record in a code block. Save it as `nec-progress.md`, then paste or upload it at the start of your next chat. Inside a Claude Project you can keep the file in the project instead.

## Syllabus coverage

| Unit | Chapter | Code |
|---|---|---|
| U1 | Concept of Basic Electrical and Electronics Engineering | AExE01 |
| U2 | Digital Logic and Microprocessor | AExE02 |
| U3 | Programming Language and Its Applications | ACtE03 |
| U4 | Computer Organization and Embedded System | ACtE04 |
| U5 | Concept of Computer Network and Network Security System | ACtE05 |
| U6 | Theory of Computation and Computer Graphics | ACtE06 |
| U7 | Data Structures and Algorithm, Database System and Operating System | ACtE07 |
| U8 | Software Engineering and Object-Oriented Analysis & Design | ACtE08 |
| U9 | Artificial Intelligence and Neural Networks | ACtE09 |
| U10 | Project Planning, Design and Implementation | AALL10 |

Each chapter has 6 sub-chapters. The full topic lists are in `SKILL.md`.

## Exam pattern the skill assumes

| Item | Value | Basis |
|---|---|---|
| Questions | 100 multiple-choice, 1 mark each, options a to d | NEC's official ACtE model question set |
| Time | 2 hours | Third-party reports of the scheme NEC announced on Bhadra 17, 2082 |
| Pass mark | 50 percent | Same third-party reports |
| Split, as reported | 10 questions per chapter, at least 1 per sub-chapter | Same third-party reports |
| Split, in the official model set | Questions 1 to 60: one per sub-chapter in syllabus order. Questions 61 to 100: 40 more from chapters 1 to 9, none from chapter 10 | NEC's official ACtE model question set |
| Negative marking | None reported | Unconfirmed |

The two splits agree that every sub-chapter gets at least one question. They disagree on chapter 10, which gets 10 questions in one and 6 in the other.

NEC has changed the pattern before. The skill asks you to confirm it against your own NEC notice or admit card before the first mock exam, and uses whatever you tell it.

## How the syllabus map was checked

On 2026-11-11 all 60 sub-chapter entries were compared word by word with the text of NEC's official Computer Engineering syllabus PDF. No topic is missing or added. Nine entries correct an obvious misprint in the PDF, for example "Multiplexetures" to multiplexers, "Curch" to Church and "Redix" to radix. Wordings that look wrong but are ambiguous are kept and marked "as printed".

## Limitations

- **New and lightly tested.** The structure and syllabus have been checked, but the skill has not yet been used through a full study cycle. Please report problems.
- **No memory between chats** without the progress record.
- **No timer.** Claude cannot time a mock exam. You run the clock.
- **Practice questions are original.** They are written in NEC style and are not past NEC questions.
- **Rules can change.** If NEC publishes a newer syllabus or pattern, the newer version wins.
- **Computer Engineering only.** Other disciplines need a different syllabus map.

## Adapting it to another discipline

Chapters 1, 2, 7, 8 and 10 are word for word the same in NEC's Information Technology Engineering (AItE) syllabus. To adapt the skill, replace the syllabus map and the chapter references in `SKILL.md` with the official syllabus of the discipline you need, and check your version against NEC's PDF.

## Official sources

- [NEC notice: Syllabus / Model Questions of Computer Engineering](https://nec.gov.np/notices/69203786a4b9137ecf1c4d38)
- [Official Computer Engineering syllabus (PDF)](https://nec.gov.np/uploads/Syllabus-Registration/1763716654201_Syllabus%20Computer%20Engineering.pdf)
- [Official Computer Engineering model question set (PDF)](https://nec.gov.np/uploads/Model%20Question%20Registration/1763714765897_Model%20question%20of%20Computer%20Engineering.pdf)
- [Nepal Engineering Council](https://nec.gov.np/)

NEC's documents are not included in this repository. Download them from NEC.

## Contributing

Issues and pull requests are welcome. For a syllabus or exam-pattern correction, include a link to the NEC source.

## Version

2.1.0. The version history is at the end of `SKILL.md`.

## License

The skill text is released under the MIT License. See `LICENSE`. The syllabus topic lists come from NEC's published syllabus, and NEC's documents remain NEC's.
