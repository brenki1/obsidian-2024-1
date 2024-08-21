A Lei de Amdahl define o speedup (S), que consiste do ganho em desempenho que pode ser obtido ao melhorar determinada característica do computador:
 $$S = \frac {TempoExecuçãoTodaOperaçãoSemMelhoria}{TempoExecuçãoTodaOperaçãoComMelhoria}$$
$$S = \frac{DesempenhoOperaçãoComMelhoria}{DesempenhoOperaçãoSemMelhoria}$$

A Lei de Amdahl depende de dois fatores:
- A fração do tempo de execução afetado pelo melhoramento;
- A taxa de melhoria obtida pela parte melhorada

$$Time_e = Time_o((1-Fraction_e) + \frac{Fraction_e}{Speedup_e})$$

	$$SpeedupOverall = \frac{Time_o}{Time_e} = \frac{1}{(1 - Fraction_e)+\frac{Fraction_e}{Speedup_e}}$$
	