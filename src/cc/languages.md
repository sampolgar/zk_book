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
- Complement:  $L_1 = \{00, 10\}$ ..

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