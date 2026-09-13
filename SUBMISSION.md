# Week 1 Submission

**Student number:** 20119105
**Name:** Darragh Breheny O'Donovan

> Answer the questions below, then run `python make_submission.py` in this
> folder. That produces the single file you upload.
>
> Delete each  as you finish that section. The script will not build
> your submission while any remain — that is deliberate, so you never upload
> a half-finished file by accident.

---

## 1. Environment check

Run `python setup_check.py` and paste the whole output below.

The line that matters is the last one. Aim for **0 blocking**. The
"sort out later" items have deadlines in Weeks 3 and 7, not today.

========================================================================
Week 1 Lab · environment check
========================================================================
[  OK  ] Python                             3.14.2 on Windows AMD64
[ NOTE ] environment                        local machine (Colab also fine)
------------------------------------------------------------------------
[  OK  ] numpy                              2.5.3
[  OK  ] pandas                             3.0.5
[  OK  ] sklearn                            1.9.1
[  OK  ] matplotlib                         3.11.2
[  OK  ] scipy                              1.18.1
[  OK  ] torch                              2.14.0+cpu
[  OK  ] transformers                       5.17.0
[  OK  ] datasets                           5.0.1
[ NOTE ] shap                               not installed (needed from Week 3 onward) — bash setup.sh --full
[ NOTE ] lime                               not installed (needed from Week 3 onward) — bash setup.sh --full
[  OK  ] ipywidgets                         8.1.9
------------------------------------------------------------------------
[ NOTE ] accelerator                        CPU only — fine for Weeks 1-5;use Colab later
------------------------------------------------------------------------
[ NOTE ] HuggingFace token                  none set — fine for open models; needed for gated ones (Week 7)
[  OK  ] HuggingFace cache                  C:\Users\PC/.cache/huggingface
[  OK  ] Ollama                             1 model(s): llama3.2:1b
[  OK  ] git identity                       Dazzmondo <145718955+Dazzmondo@users.noreply.github.com>
========================================================================
13 ready · 5 to sort out later · 0 blocking

Nothing blocking. You are ready for the timeline exercise.
---

## 2. Exercise 1 — Read the tags

`load()` gives you the timeline as a DataFrame. Plot milestones per decade by
family.

**When does connectionism overtake symbolic AI, and does the crossover match
the story in the lecture?**

Two or three sentences.

Save your plot as `submission-crossover.png` **in this folder**. Do not put it
in `figures/` — that folder is in `.gitignore` and is emptied when the scripts
regenerate, so anything saved there will be lost.

Connectionism overtakes symbolic AI in the 2000s, according to the plot. The crossover matches the story of the lecture. Symbolic dominated from Dartmouth in the 1950s to the 1990s, including both crashes and subsequent winters that overpromised. The lecture suggested the crossover happened between 2005 and 2012 when AlexNet arrived, but there are in fact no symbolic milestones after Deep Blue defeated Gary Kasparov in 1997.
---

## 3. Exercise 2 — Argue with the supply dates

`SUPPLY` in `timeline_data.py` says architecture arrived in 1986, compute in
2007 and data in 2009.

**Change at least one, defend your version in three sentences, and say what it
does to the gap before AlexNet.**

There is no correct answer here. There are defensible ones.

SUPPLY = {
    "architecture": (1989, "LeNet / digit recognition", "Deep learning in production, reading cheques, a decade before it was famous."),
    "compute": (2007, "CUDA: commodity gaming silicon becomes general-purpose parallel compute."),
    "data": (1998, "MNIST: labelled data at a scale nobody had assembled before (60,000 images)"),
}

LeNet in 1989 built on the backpropagation from 1986, and brought it from a research concept to a more practical architecture that could solve real-world recognition problems. This represents a better point of availability at commodity scale than the earlier year of 1986.
While ImageNet in 2009 offered data at an even greater scale, I would argue that data was already available at a large enough scale in 1998, when MNIST built on the existing NIST dataset to reach 60,000 images. This could already be seen as data being available at commodity scale long before ImageNet. See https://en.wikipedia.org/wiki/MNIST_database and https://www.kaggle.com/discussions/questions-and-answers/269387

---

## 4. Exercise 3 — Find the dormant field

**List every milestone that occurred inside a winter. What does that do to the
claim that the field was dead?**

(1969, "Perceptrons (Minsky and Papert)", "shock",   "symbolic", None, "XOR: correct about one layer, read as a refutation of the idea."),
(1969, "Shakey the robot", "system", "symbolic", None,
 "'The first electronic person', in a prepared room."),
(1970, "SHRDLU", "system", "symbolic", None,
 "Genuine understanding, of blocks."),
(1972, "Prolog", "system", "symbolic", None,
 "Logic as a programming language."),
(1973, "Lighthill report", "shock", "neither", None,
 "UK funding withdrawn. Winter I begins."),
(1974, "WINTER I begins", "shock", "neither", None,
 "Combinatorial explosion meets promises that assumed it away."),
(1975, "MYCIN evaluated", "system", "symbolic", None,
 "Matches specialist physicians. Never deployed: liability, workflow, trust."),
(1979, "Neocognitron", "system", "connectionist", "architecture",
 "Convolutional structure, a decade before it could be trained."),
(1980, "XCON at DEC", "system", "symbolic", None,
 "Configures orders; credited with about $40M a year saved."),
(1980, "Expert systems boom", "institution", "symbolic", None,
 "A smaller, sellable promise. It works, for seven years."),
(1987, "WINTER II begins", "shock", "neither", None,
 "Brittleness, the knowledge bottleneck, and maintenance present their invoices."),
(1989, "LeNet / digit recognition", "system", "connectionist", "architecture",
 "Deep learning in production, reading cheques, a decade before it was famous."),
(1990, "The great rebrand", "institution", "statistical", None,
 "'AI' becomes toxic; the work continues as 'machine learning'."),

The existence of so many milestones within the winter years shows that the field was never really dead. Rather it was dormant with less attention and investment during these winters. AI's development through history has remained continuous with increasing a decreasing waves of attention, investment and innovation throughout time. Similar to the Dark Ages, there may be less attention and cultural events than during the Roman or Renaissance periods, but that does not mean history didn't continue with numerous notable events during this time.

---

## 5. Anything that did not work

Optional, and genuinely useful. If something took far longer than it should
have, or an instruction was wrong, say so. This is how the lab improves.

bash setup.sh shortcut doesn't work with Windows because the script uses source bin instead of Scripts. It was relatively easy to set up the virtual environment by hand instead, but if someone wanted the option to do the quick installation, perhaps having a guide on Tutors and a specific bash setup.sh for windows where everything else is installed in the same way but source .venv/Scripts/activate is called instead might be useful/more efficient.