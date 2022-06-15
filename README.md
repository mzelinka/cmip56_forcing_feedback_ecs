# Summary 
[![stable version](https://img.shields.io/badge/Current%20version-2.2-brightgreen.svg)](https://github.com/mzelinka/cmip56_forcing_feedback_ecs/releases/tag/v2.2)

[![DOI](https://zenodo.org/badge/259409949.svg)](https://zenodo.org/badge/latestdoi/259409949)


Three tables and a JSON file are provided containing effective climate sensitivity, effective 2xCO<sub>2</sub> radiative forcing, and radiative feedbacks for all CMIP5 and CMIP6 models that have published output from abrupt CO<sub>2</sub> quadrupling experiments. Two tables contain the "flagship" model variants for CMIP5 and CMIP6. These are typically but not always the 'r1i1p1' variant (CMIP5) or the 'r1i1p1f1' variant (CMIP6), and are updated from Tables S1 and S2 in [Zelinka et al. (2020)](https://agupubs.onlinelibrary.wiley.com/doi/10.1029/2019GL085782).  Results from other model variants are contained in the third "non-flagship" table. All models and variants are contained in the single JSON file (see details below).  Also provided is a figure showing Gregory plots for the CMIP6 models and two histograms of ECS values for CMIP5 and CMIP6. Methdology is described in [Zelinka et al. (2020)](https://agupubs.onlinelibrary.wiley.com/doi/10.1029/2019GL085782), but the CMIP6 results are regularly updated as new models are published.

## Table Contents
For each variant of each model, the following global mean values are provided:

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

The final two rows of the tables provide the multi-model average and standard deviation. 
Note: 
  * PL + LR + WV is equivalent to PL* + LR* + RH
  * CLD = SWCLD + LWCLD
  * ECS = -ERF2x/NET 
  

## Accessing Data from the JSON file via Python  
Load in the file:
```
import json
f = open('cmip56_forcing_feedback_ecs.json','r')
data = json.load(f)
```
To display the dictionaries within the file, type:
```
data.keys()
```
which returns:
```
dict_keys(['CMIP5', 'CMIP6', 'metadata', 'provenance'])
```
There are 4 dictionaries: two containing the CMIP5 and CMIP6 data, one containing the metadata for the json file, and one containing provenance information pointing back to the original data that went into the analysis (mainly for my personal use). 

To get a list of available CMIP6 models, type:
```
data['CMIP6'].keys() 
```
To see which variants are available for CanESM5, type:
```
data['CMIP6']['CanESM5'].keys()
```
which returns 
```
dict_keys(['r1i1p1f1', 'r1i1p2f1'])
```
To see the data from the r1i1p2f1 variant of CanESM5, type:
```
data['CMIP6']['CanESM5']['r1i1p2f1']
```
which returns 
```
{'ALB': 0.4781269675709477,
 'CLD': 0.792934477604314,
 'ECS': 5.615875344692928,
 'ERF2x': 3.639659171965616,
 'ERR': 0.03790795336163966,
 'LR': -0.589242644226542,
 'LR*': -0.09003163619198515,
 'LWCLD': 0.8111615864750927,
 'NET': -0.6481018449608463,
 'PL': -3.324746652302142,
 'PL*': -1.9354660083835276,
 'RH': 0.07050794199691038,
 'SWCLD': -0.018227108870778348,
 'WV': 1.9569180530309362}
```
Don't forget to close the file:
```
f.close()
```

## Reference
Zelinka, M. D., T. A. Myers, D. T. McCoy, S. Po-Chedley, P. M. Caldwell, P. Ceppi, S. A. Klein, and K. E. Taylor, 2020: Causes of higher climate sensitivity in CMIP6 models, <em>Geophys. Res. Lett.</em>, 47, [doi:10.1029/2019GL085782](https://agupubs.onlinelibrary.wiley.com/doi/10.1029/2019GL085782).
