# acud simulation tool

acud is a lightweight capacity expansion, economic dispatch and unit commitment simulation
tool written in Python which uses csv and Excel files as input and output data format.
It is an optimisation-based simulation tool that leverages multiple state-of-art data handling
Python packages including pandas and xarray, powered by open source (e.g. glpk, cbc) or 
commercial (e.g. cplex, gurobi) solver engines. The optimisation is defined as a 
Linear Programming (LP) or Mixed-Integer Linear Programming (MIP) problem, depending on the 
desired level of accuracy and complexity. It is able to handle multiple time resolutions,
producing both chronological and duration curve-based results.

acud applies a fundamental power market modelling approach. Fundamental market models use cost-based 
bid and offer curves to derive estimations of electricity prices and other market outcomes. These models
give insight into fundamental price drivers and market mechanisms. Therefore, fundamental market models
can be used for the development of trading strategies as well as for investments or acquisitions.

## History

acud earliest´s predecessor was written in GNU MathProg, a specialised modelling language used to
describe linear and mixed integer mathematical programming models.
[MathProg](https://www.gnu.org/software/glpk/glpk.html) is a subset of
the AMPL modelling language, and as such, benefits from the expresiveness and 
succintness of the AMPL language, leading to compact and easy to understand
problem formulation implementations. For acud, the main drawbacks of using Mathprog as modelling framework
were only being able to use GLPK as solver and the low level support of MathProg for
data analysis tasks related e.g. to solution reporting.

These limitations finally lead to the switch from MathProg to PuLP as the mathematical programming framework
underlying acud. PuLP provides interfaces to multiple commercial and open source solvers (GLPK included)
thus providing more options. As a Python package, PuLP can be made to seamlessly work with 
a vast collection of data analysis tools coded in this general programming language

[PYPOWER](https://github.com/rwl/PYPOWER) was a major source of inspiration during this transition to Python,
especially regarding data handling routines. More recently, projects such as
[Calliope](https://www.callio.pe/), [PyPSA](https://pypsa.org/) and [Dispa-SET](http://www.dispaset.eu)
provided some very good ideas. Calliope is a multi-energy modelling system (in contrast to acud that is
basically an electricity model) and PyPSA offers very detailed network flow analysis (transmission in acud
is modelled as a transport problem based on net transfer capacities). Of these three models, acud is probably
closest to Dispa-SET, with a focus on detailed representation of economic and technical aspects of generation resources.  

## Project status

acud is very usable in its current form. In fact the analysis of several consulting assignments
undertaken over the last ten years were based on acud results. It does not 
however meet the standards of modern open source projects in terms of 
documentation and automated unit testing. As soon as it is in publishable shape
it will be made publicly available through a major open source project hosting platform such as GitHub, Bitbucket or GitLab.

In the meantime you can check the project [online documentation](https://acud.readthedocs.io/en/latest/) at
[Read the Docs](https://acud.rtfd.io) and a related side project called
[acud_extras](https://bitbucket.org/qheuristics/acud_extras).
