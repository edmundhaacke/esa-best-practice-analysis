# Best practice in coding/programming

## Key principles

Good quality code, and thus coding practice is crucial for several reasons

1. It allows for easy maintenance for both yourself, and others in the team
2. It enables others to peer review your code easily


#### Naming

All variables should be named clearly, in a meaningfully descriptive manner that gives the user context as to what the variable contains. A key test of this is whether you would, six months later, come back to the code, and immediately continue working on it.

There are different naming conventions, which may differ across programming languages.

1. **Snakecase**, where words are delimited by an underscore `variable_one`. This is the naming convention used by Python (van Rossum _et al_, 2001), and C.
2. **Pascalcase** (or Upper Camelcase), where words are delimited by capital letters `VariableOne`. 
3. **Camelcase**, where words are delimited by capital letters, except the initial word `variableOne`. This is the naming convention used by C++ for variables/functions.
4. **Hungarian Notation**, where the variable type/purpose is at the start of the variable name, followed by a description of the variable. Camelcase notation is used to delimit words. `arrAgeGroups` denotes an array called 'AgeGroups', and `iAgeLimit` denotes an integer called 'Age Limit'.

Note that R does not have a formal naming convention, with multiple naming conventions prevalent throughout. Uses can also use '.' within names, e.g. `variable.one`.

STATA places restrictions on the length of variable names, they are limited to 32 characters. You will often find that when loading data with column names above this limit, that STATA renames your columns to `var1` etc... You cannot change this limit. This therefore raises the need to use abbreviations (although this applies to naming in general). You should follow two principles in using abbreviations:

1. **Consistency**: if you use an abbreviation, it should be used everywhere instead of the full name. You should have only a single abbreviation for a name.
2. **Recognition**: the abbreviation should be commonly recognized, and understood.

Ultimately, which naming convention you choose is user-preference, however, it is important for legibility that you are consistent in using it across your code.

#### Whitespace and tabbing

Whitespace is any space in your code which isn't taken up by physical characters. Some languages ignore whitespace and tabbing, however some rely upon this to function (e.g. Python). Whitespace is important for organizing code, and is frequently used in nested loops and logical statements.

##### No whitespace

```r
# print even numbers between 0 and 10
for(i in 1:10){ if(i%%2==0){ print(i) } else {print('not even')} }
```

##### With whitespace

```r
# print even numbers between 0 and 10
for (i in 1:10){
	if (i%%2==0){
		print(i)
	} else {
		print('not even')
	}
}
```

Again it is important to use whitespace and tabbing in a consistent, readable style within any code.

#### Commenting 

Commenting is a key practice to help with organization and segment your code. Comments can help label code, and sections of code, and should be used in a consistent and intuitive manner, which help other users to easily understand your code. Conversely, you should not over-comment your code, as this may compromise ease of understanding.

#### Don't Repeat Yourself (DRY)

The Don't Repeat Yourself (DRY) principle essentially means avoid repeating code. Any duplication should be eliminated through automation (e.g. loops). These duplicates add unnecessary code into your codebase, which can require additional work to build on your code in the future. It decreases the quality of the code, and usually stems from copy paste programming. It can also lead to errors in the future, as you have to modify several instances of the same code, some of which may be missed.

#### You Aren't Going to Need It (YAGNI)

The You Aren't Going to Need It (YAGNI) principle states you shouldn't develop code for something that isn't necessary. Essentially, you should only implement things when you need them, not when you just foresee that you need them. 

#### Refactor

Refactoring code is when you review, and look for ways to optimize to your code, with the goal of making it more efficient without changing the results. It is normal to revisit, rewrite, or even redesign chunks of code, especially as your knowledge and familiarity of the project develop.

### Other considerations

Although the aforementioned principles to programming are

### Examples of code

Below are some examples of code that the ESA Team has produced

| Project | Programming language | Location | Authors |
| :--- | :--- | :--- | :--- |
| ED crowding | R | [NHS England GitHub](https://github.com/nhsengland/ESA_ED_Crowding) | Svetlana Batrakova, Ranya Alakraa, Dimitris Pipinis, Edmund Haacke |
| Avoidable ED attendances | C++ and R | [NHS England GitHub](https://github.com/nhsengland/ESA_Avoidable_ED_Attendances) | Edmund Haacke |

## Version control

### Version control in coding

Version control in development, is the process of tracking and managing changes to files over time. Version control can be used for versioning code, binary files and digital assets. A version control system allows for the following benefits:

1. Concurrent development - multiple users can work using the same set of files without the concern of overwriting other team members' work.
2. Collaboration - there is a single source of the truth available to all users. Each team member is working on the latest version of the code.
3. Tracked changes - version control systems let you identify who changed what, when and why. This gives an auditable log of all changes made to the code-base.

One of the most widely used version control systems is **Git**. 

When using a platform such as GitHub, it is **important you follow any organizational policies** relating to its use. You can find further details on the [ICT Architecture page](https://github.com). 

#### Ensuring data security

When using a platform such as GitHub, there are important steps which need to be taken to ensure that anything confidential such as data or results are not inadvertently shared or uploaded into the public domain. A `gitignore` file (located within the root of your project as a plaintext file named `.gitignore` specifies untracked files that Git should ignore, with each line specifying a pattern. This should be created before the first commit, as this ***will not*** remove files already uploaded.

```bash
# ignore specific files
.Rproj.user
.Rbuildignore
.Rhistory
.Rdata
# ignore all content within specific directories
data/**
outputs/**
```

Further details on `gitignore` can be found in the [gitignore documentation](https://git-scm.com/docs/gitignore).

## Documentation

Accompanying documentation is vital to ensure the maintainability of a codebase, irrespective of whom is working on it. The main purpose of the documentation is to describe ***why*** the code does what it does, and is an important part of the development process. The documentation should be sufficient to allow others to repeat the analysis. Documentation can aid in knowledge transfer, support in debugging of issues, revisiting your code in the future, to allow others to use your code easily and build upon it, and allow reproducibility and transparency.

1. Documentation should be **simple** and **concise**.
2. Documentation should be kept **up-to-date**. As code is updated, the associated documentation should be updated. You should trim your documentation as appropriate, removing anything outdated.

### Creating documentation

Markdown-based systems are one of the most popular documentation systems. Markdown is a lightweight markup language for creating formatted text using a plain-text editor. Markdown (specifically GitHub Flavored Markdown, GFM) is used across GitHub (e.g. README.md files), and is easy to pickup. A key benefit to using Markdown as opposed to Word for example, is that version control solutions can easily track any changes.

Mermaid is a Javascript-based diagramming and charting tool, which uses Markdown-inspired text definitions and a renderer to create and modify complex diagrams. These charts are created entirely using text through a simple syntax. Mermaid supports many different types of diagrams, including flowcharts; sequence, class, state and entity relationship diagrams, Gantt, and pie charts. These diagrams can also be generated through code. You can find substantial documentation [on their website](https://mermaid-js.github.io/mermaid/#/).

Visual Studio Code supports the creation of Markdown and Mermaid graphs (with export functionality) through extensions available in the marketplace. You can also use [StackEdit](https://stackedit.io) as a free solution to write Markdown and Mermaid which can be synced using Google Drive or Dropbox. [Mermaid Live](https://mermaid.live) is a free site that lets you render Mermaid graphs, which can be downloaded in the PNG or SVG image format.

## Literature Review

A review of the existing literature is can occur in the form of a _rapid literature review_, which, as the name suggests is conducted over a very short period of time. For larger, longer term projects, it may be desirable to conduct a more thorough review of the literature. There are three main goals when conducting a review of the literature:

1. Summarize and analyse previous research, theories and analytical approaches
2. Identify contested areas or conflicting findings
3. Highlight gaps within the literature

The literature review is important as it can help inform the analytical approach (e.g. what econometric model, what other factors need to be controlled for etc). Furthermore, it can provide a means to quality assure your analysis through a simple sense check, for example checking whether your findings are in alignment with, or contradictory to the majority of existing literature.

### Resources

- OpenAthens: You can register an OpenAthens account through the National Institute for Health and Care Excellence (NICE) 
- EconLit: Members and Associate Members (e.g. NHSE) of the Government Economics Service (GES) receive free access to [EconLit Journal Access](https://members.ges.gov.uk/your-career/your-continued-professional-development/core-resources-and-guidance/ebsco/). Note this is only open those with an Economics degree and working in the Economics profession.