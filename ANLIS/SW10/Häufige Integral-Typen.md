Folgende Tabelle gibt häufige [[Integration|Integral]]-Typen an, welche bei der [[1. Substitutionsregel]] und [[2. Substitutionsregel]] verwendet werden können.

| Integraltyp | Substitution | Beispiel | Substitution |
| ---- | ---- | ---- | ---- |
| $$\int f(ax+b) \, dx $$*Merkmal:* Die Variable $x$ tritt in der linearen From $ax+b$ auf ($a\ne 0$) | $$u=ax+b$$$$dx=\frac{du}{a}$$ | $$\int (2x-3)^6 \, dx $$ | $u=2x-3$ |
| $$\int f(x)\cdot f'(x) \, dx $$*Merkmal*: Der Integrand ist das Produkt aus einer [[ANLIS/SW01/Funktionen/Funktion]] ($f(x)$) und ihrer Ableitung $f'(x)$ | $$u=f(x)$$$$dx=\frac{du}{f'(x)}$$ | $$\int \sin x\cdot \cos x \, dx $$ | $u=\sin x$ |
| $$\int f(\sqrt{ a^{2}-x^{2} }) \, dx $$*Merkmal:* Der Integrand enthält eine Wurzel von Typ $\sqrt{ a^{2}-x^{2} }$ | $$x=a\cdot \sin(u)$$$$dx=a\cdot \cos u\cdot du$$$$\sqrt{ a^{2}-x^{2} } = a \cdot \cos u$$ | $$\int \sqrt{ x^{2}-1 } \, dx $$ | $x=\sin u$ |
| $$\int f(\sqrt{ a^{2}+x^{2} }) \, dx $$*Merkmal:* Der Integrand enthält eine Wurzel von Typ $\sqrt{ a^{2}+x^{2} }$ | $$x=a\cdot \sinh(u)$$$$dx=a\cdot \cosh u\cdot du$$$$\sqrt{ a^{2}+x^{2} } = a \cdot \cosh u$$ | $$\int \frac{1}{\sqrt{ x^{2}+4 }} \, dx $$ | $x=2\sinh u$ |
| $$\int f(\sqrt{x^{2}-a^{2} }) \, dx $$*Merkmal:* Der Integrand enthält eine Wurzel von Typ $\sqrt{ x^{2}-a^{2} }$ | $$x=a\cdot \cosh(u)$$$$dx=a\cdot \sinh u\cdot du$$$$\sqrt{ x^{2}-a^{2} }=a\cdot \sinh u$$ | $$\int \frac{x}{\sqrt{ x^{2}-25 }} \, dx $$ | $x=5\cdot \cosh u$ |
