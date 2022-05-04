# pypolys package

Python implementation of polynomials is presented.

## Installation

See doc/quickstart.txt

## Usage

~~~python
>>> from fractions import Fraction
>>> from pypolys.polys import Poly
>>> p = Poly(2, 3) + 4   # 2 * x ** 3 + 4
>>> p
Poly(4) + Poly(2, 3)
>>> p.is_zero()
False
>>> len(p)   # the number of terms
2
>>> p * Poly(3, 5)
Poly(12, 5) + Poly(6, 8)
>>> p ** 2
Poly(16) + Poly(16, 3) + Poly(4, 6)
>>> p.diff()
Poly(6, 2)                    # 6 * x ** 2
>>> p.integrate()
Poly(4, 1) + Poly(Fraction(1, 2), 4)   # 4 * x + x ** 4 / 2
>>> p.combine(Poly(5, 7))
Poly(4) + Poly(250, 21)
>>> p.eval(Fraction(3, 5))
Fraction(554, 125)
>>> p.eval(0.6)
4.432
>>> p.leading_term(key=Poly.key_deg)
Poly(2, 3)
>>> p.leading_monomial(key=Poly.key_deg)
Poly(1, 3)
>>> p.leading_coefficient(key=Poly.key_deg)
2
>>> Poly(6, 5) / Poly(3, 2)   # for monomials only
Poly(2, 3)
>>> Poly(6, 3).lcm(Poly(3, 2))
Poly(1, 3)
>>> list(p.iterterms())
[Poly(4), Poly(2, 3)]
>>> sorted(term.degree() for term in p.iterterms())
[0, 3]
>>> [p[i] for i in range(8)]  # coefficient list
[4, 0, 0, 2, 0, 0, 0, 0]
~~~

## Contributors

Andrzej Kapanowski (project leader)

Adrian Szumski

EOF
