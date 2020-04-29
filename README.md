# Summary
Two tables and a JSON file are provided containing effective climate sensitivity, effective 2xCO<sub>2</sub> radiative forcing, and radiative feedbacks for all CMIP5 and CMIP6 models that have published output from abrupt CO<sub>2</sub> quadrupling experiments. Also provided is a figure showing Gregory plots for the CMIP6 models. Methdology is described in [Zelinka et al. (2020)](https://agupubs.onlinelibrary.wiley.com/doi/10.1029/2019GL085782), but the CMIP6 results are regularly updated as new models are published.

## Table Contents
For each model, the following global mean values are provided:

| Abbreviation  | Description  | Units  |
| ------------- |:-------------:|:-------------:|
| ECS           | effective climate sensitivity |                              K |
| ERF2x         | 2xCO<sub>2</sub> effective radiative forcing | Wm<sup>-2</sup> |    
| PL            | Planck feedback |                              Wm<sup>-2</sup>K<sup>-1</sup> |
| PL*           | constant-RH Planck feedback |                  Wm<sup>-2</sup>K<sup>-1</sup> |
| LR            | lapse rate feedback |                          Wm<sup>-2</sup>K<sup>-1</sup> |
| LR*           | constant-RH lapse rate feedback |              Wm<sup>-2</sup>K<sup>-1</sup> |
| WV            | water vapor feedback |                         Wm<sup>-2</sup>K<sup>-1</sup> |
| RH            | relative humidity feedback |                   Wm<sup>-2</sup>K<sup>-1</sup> |
| ALB           | surface albedo feedback |                      Wm<sup>-2</sup>K<sup>-1</sup> |
| CLD           | net cloud feedback |                           Wm<sup>-2</sup>K<sup>-1</sup> |
| SWCLD         | shortwave cloud feedback |                     Wm<sup>-2</sup>K<sup>-1</sup> |
| LWCLD         | longwave cloud feedback |                      Wm<sup>-2</sup>K<sup>-1</sup> |
| NET           | net feedback |                                 Wm<sup>-2</sup>K<sup>-1</sup> |
| ERR           | kernel residual feedback |                     Wm<sup>-2</sup>K<sup>-1</sup> |

Note that PL + LR + WV is equivalent to PL* + LR* + RH, CLD = SWCLD + LWCLD, and ECS = -ERF2x/NET. The final two rows of the tables provide the multi-model average and standard deviation. 

## Reference
Zelinka, M. D., T. A. Myers, D. T. McCoy, S. Po-Chedley, P. M. Caldwell, P. Ceppi, S. A. Klein, and K. E. Taylor, 2020: Causes of higher climate sensitivity in CMIP6 models, <em>Geophys. Res. Lett.</em>, 47, [doi:10.1029/2019GL085782](https://agupubs.onlinelibrary.wiley.com/doi/10.1029/2019GL085782).
