# garchur

**GARCH Unit Root Test with Endogenous Structural Breaks**

[![CRAN status](https://www.r-pkg.org/badges/version/garchur)](https://CRAN.R-project.org/package=garchur)
[![License: GPL-3](https://img.shields.io/badge/License-GPL--3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

## Overview

`garchur` implements the trend-GARCH(1,1) unit root test of Narayan and Liu
(2015) that allows for up to **three endogenous structural breaks** in the
mean equation while modelling **conditional heteroskedasticity** via GARCH(1,1).

**Mean equation:**
$$y_t = a_0 + a_1 t + \rho y_{t-1} + \sum_{j=1}^{m} \gamma_j DU_{jt} + \varepsilon_t$$

**Variance equation:**
$$h_t = \kappa + \alpha \varepsilon_{t-1}^2 + \beta h_{t-1}$$

## Installation

```r
install.packages("garchur")
```

## Quick Start

```r
library(garchur)

set.seed(42)
y <- cumsum(rnorm(100))

# Two breaks, constant + trend
res <- garchur(y, breaks = 2, model = "ct")
print(res)
```

## Reference

Narayan, P. K., & Liu, R. (2015). A unit root model for trending time-series energy variables. *Energy Economics*, 46, 1–9. <https://doi.org/10.1016/j.eneco.2014.11.021>

## Author

Muhammad Alkhalaf <muhammedalkhalaf@gmail.com>
