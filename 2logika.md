 Výpočetní logika. Rezoluční metoda v predikátové logice. Zjemnění rezoluce a Hornovy klauzule. SLD-rezoluce. Výpočetní model logického programu. Jazyk Prolog. Tablové důkazy ve výrokové, predikátové a modální logice. Induktivní inference ve výrokové a predikátové logice. Vícehodnotové logiky.  


Vyrokova logika:

Syntaxe:
Proměnné – A,B,C….
Operátory - ∧(and), ∨(or), ￢(Negace),→(implikace),↔(ekvivalence)
Formule - α β γ

Vsechny formule jde vytvorit indukci z:
Formule obsahujici jednu promenou (α : A)
opakovanim pravidel. pokud α a β jsou formule, pak:
(α ∧ β) je formule
(α ∨ β) je formule
(¬β) je formule
(α ⟹ β) je formule
(α ⟺ β) je formule

Příklad formule:  𝛾: A ∧ ((A → B) → B)


Vyplývání :   A ⊨ B - A vyplyva z B
ekvivalence : A ≡ B  prave tehdy kdyz   A⊢B a zaroven  B⊢A

satisfiability = Splnitelnost = α ≢ false   <- α neni ekvivalentni nepravde - existuje alespon jeden pripad, kdy je pravdiva
validity = tautologie : 𝛾 ≡ true  : 𝛾 je platna vzdy

Tautologie je vzdy splnitelna
Tautologie 𝛾 je tautoligii tehdy, kdyz Negace(𝛾) je nesplnitelna
α ⊨ β prave tehdy kdyz α ⟹β je tautologie = α vyplyva z β prave tehdy, kdyz  α ⟹β je tautologie

priklady:
α ∨ ¬α je tautoligii
α ∨ β je splnitelna, ale neni tautoligii
α ∧ ¬α neni splnitelna 

Semantika(prirazuje symbolum pravdivostni hodnotu):
Pravdivostní ohodnocení (interpretace) je funkce přiřazující všem atomickým formulím dané úvahy pravdivostní hodnoty (tj. každému výrokovému symbolu přiřadí 0 nebo 1). 
Valuace je rozšíření interpretace z atomických na všechny formule dle tabulky pro výrokové spojky.

Interpretace I splňuje formuli A (formule je pravdivá v I, resp. odpovídající valuace I'(A) = 1), pokud

A je výrokový symbol a I(A) = 1
A je ¬ B a I nesplňuje B, resp. I'(B) = 0
A je tvaru B ∧ C a I splňuje B i C, resp. I'(B) = I'(C) = 1
A je tvaru B ∨ C a I splňuje B nebo C, resp. I'(B) = 1 nebo I'(C) = 1
A je tvaru B → C a I nesplňuje B nebo splňuje C, resp. I'(B) = 0 nebo I'(C) = 1
A je tvaru B ⟺ C a I splňuje B i C nebo I nesplňuje B i C, resp. I'(B) = I'(C)

Jsou to intuitivni pravidla, proste davas promennym hodnoty 1/0 a pro formuli vytvorenou z logickych spojek pak 0/1 dle pravdivosti


predikatova logika 
1. řádu: „Není pravda, že všichni lidé jsou spokojení.“ ¬∀ x: (clovek(x) ⇒ spokojeny(x))
2. řádu: „Existuje vlastnost, kterou mají všichni lidé.“ ∃ P ∀ x: (clovek(x) ⇒ P(x))

Syntaxe:
Variables x, y, z, . . .
Terms x, f (t0, . . . , tn)  - 
Relations R(t0, . . . , tn) and equality t0 = t1   = predikaty, n-arni relace
Operators ∧, ∨, ¬,→,↔
Quantifiers ∃x, ∀x

Termy jsou z fnkcnich symbolu, konstrant a promenych

α ∶= ∀x∃y[f(y) = x] ,
α ∶= ∀x∀y∀z[x ≤ y ∧ y ≤ z → x ≤ z] .


Prenexace
Cílem Prenexové normální formy je převést libovolnou (uzavřenou) formuli do tvaru, v němž jsou všechny kvantifikátory na začátku a následuje otevřené (= bez kvantifikátorů) jádro v KNF (DNF).

Skolemizace
Odebereme existencni kvantifikatory a predelame je na "pro vsechny"
∀¯x∃y'(¯x, y)  prepiseme na ∀¯x'(¯x, f (¯x))



Misova adresa
Address
ALzsUsiFv927uwDj6Wj9fZoN8kuJYWJpsq
Encrypted Key
6PYLtA5WHERCmQFXpqv22ooynrnuonUBsNtDHTDQUUbqF8yFKsbBZt2GPv
Private Key Backup Code
U2FsdGVkX19q+2c8W3R4lPazRdGS0fPFguw/Jc9vp2ulMNKxSZFX9NpndNGDved1fbLuTcYMPzJ8hJmhoilK1reIikMwXqgd/7qHbGabC3k=



