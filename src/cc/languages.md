# Decidable Languages

Decidable
A language is decidable if there exists an algorithm that always halts and correctly answers yes or no for any string. Given a string $w$, a deciding algorithm accepts or rejects:

$$
\begin{cases}
  \text{accept}  & w \in L \\
  \text{reject} & w \notin L
\end{cases}
$$

Given the languages $L_1 = \{01, 11\}, L_2 = \{10, 11\}$

### Operations

- Union: $\{01, 10, 11\}$
- Concatenation: $\{0110, 0111, 1110, 1111 \}$ concat every string from $L_1$ with every string from $L_2$
- Intersect: $\{11\}$
- Complement $\neq$ invert the property but invert the decision.

A class of languages is a set of languages with a shared property. For example, all Decidable Languages have algorithms that decide membership.
A class of languages is closed under an operation if, for any languages in the class, applying the operation results in a language that is also in the class (i.e., you can build an algorithm for the result).

Example:

```
Given L1 X L2 where X is the Concatenation operation. Write an algorithm that checks if an input string w is the output from L1 X L2
```

```vim
for each position i from 0 to length(w):
    x = w[0...i-1]  // first part
    y = w[i...end]  // second part
    if (x ∈ L₁) AND (y ∈ L₂):
        accept w

reject w  // if no split worked
```

## Prerequisites to add:

- **Formal language basics**

  - Alphabets ($\Sigma$), strings, languages as sets
  - Kleene star ($\Sigma^*$)
  - Language membership notation

- **Automata hierarchy**

  - Finite automata (DFA/NFA)
  - Pushdown automata (PDA)
  - Turing machines (TM)
  - Connection to language classes

- **Turing machine fundamentals**
  - Definition and components
  - Configurations and transitions
  - Acceptance/rejection/looping
  - Church-Turing thesis

## Missing concepts for decidable languages:

- **Examples of decidable languages**

  - $\{a^n b^n \mid n \geq 0\}$
  - Regular languages (all are decidable)
  - Context-free languages (all are decidable)
  - $\{w \mid w \text{ has equal 0s and 1s}\}$

- **Decidability vs recognizability**

  - Recognizable (RE): TM halts and accepts if $w \in L$
  - Decidable (R): TM always halts with yes/no
  - $R \subseteq RE$

- **Closure properties (complete list)**

  - Union, intersection, concatenation ✓
  - Complement ✓
  - Kleene star
  - Reversal
  - Homomorphism

- **Undecidability introduction**

  - The halting problem
  - Diagonalization proof technique
  - Examples: $A_{TM}$, $E_{TM}$, $EQ_{TM}$

- **Reduction techniques**

  - Mapping reductions
  - Using reductions to prove undecidability

- **Rice's theorem**
  - Non-trivial properties of TM languages are undecidable
