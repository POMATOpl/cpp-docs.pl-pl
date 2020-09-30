---
title: Funkcje matematyczne niezależne od typu
description: Opisuje makra w <tgmath. h>, które ułatwiają pisanie kodu w języku C, który wywołuje prawą funkcję matematyczną w oparciu o typ argumentu.
ms.topic: conceptual
ms.date: 9/3/2020
helpviewer_keywords:
- CRT tgmath.h
ms.openlocfilehash: 98c786d91963973ad9384cea2fe6563d1e3174ac
ms.sourcegitcommit: 9451db8480992017c46f9d2df23fb17b503bbe74
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2020
ms.locfileid: "91590228"
---
# <a name="type-generic-math"></a>Funkcje matematyczne niezależne od typu

W przypadku ISO C standard 11 (C11) i nowszych, \<tgmath.h> nagłówek, oprócz \<math.h> i \<complex.h> , zawiera makra, które wywołują odpowiednią funkcję matematyczną na podstawie typów parametrów.

Funkcje matematyczne biblioteki środowiska uruchomieniowego języka C są dostępne w rzeczywistych i złożonych odmianach. Każdy wariant ma trzy typy, w zależności od typu argumentu: `float` , `double` , i `long double` . Ponieważ język C nie obsługuje przeciążania, takiego jak C++, każdy wariant ma inną nazwę. Na przykład aby uzyskać bezwzględną wartość rzeczywistej wartości zmiennoprzecinkowej, należy wywołać metodę `fabsf` , `fabs` lub w `fabsl` zależności od tego, czy przekazujesz `float` `double` `long double` odpowiednio wartość, lub. Aby uzyskać złożoną wartość bezwzględną, należy wywołać jedną z `cabsf` , `cabs` lub `cabsl` w zależności od tego, czy przechodzą `float` `double` odpowiednio wartości,, i `long double` złożone. Jeśli argumenty nie są zgodne z żadnym z powyższych typów, funkcja jest wybierana tak, jakby argumenty były podwajane.

\<tgmath.h> zawiera makra, które upraszczają wybór prawej funkcji matematycznej do wywołania. Makra przeanalizują typ, który są przepuszczane, a następnie Wywołaj prawą funkcję. Na przykład `sqrt` makro tworzy powiązanie `sqrt(9.9f)` z `sqrtf()` , a w związku `sqrt(9.9)` z tym `sqrt()` . Jeśli co najmniej jeden argument makra dla parametru generycznego jest skomplikowany, makro wiąże się z funkcją złożoną; w przeciwnym razie wywołuje rzeczywistą funkcję.

Makra generyczne typu w programie \<tgmath.h> umożliwiają pisanie bardziej przenośnego kodu, ponieważ nie trzeba zarządzać rzutowania ani wybierać różnych nazw funkcji w zależności od typu argumentu.

Te makra znajdują się we własnym nagłówku, dzięki czemu programy utworzone przy użyciu `<math.h>` nagłówka nie będą przerywane. `double x = sin(42);`Zachowuje się tak, jakby zawsze było uwzględniane \<math.h> . Nawet w przypadku, gdy \<tgmath.h> nagłówek zostanie uwzględniony, zamiast \<math.h> lub \<complex.h> .

Poniższa tabela zawiera listę makr, które są dostępne w programie \<tgmath.h> i ich rozszerzanie. `modf` nie znajduje się w tej tabeli, ponieważ nie ma odpowiedniego makra generycznego typu, ponieważ nie jest jasne, w jaki sposób należy go bezpiecznie bez skomplikowanej rozdzielczości.

|Makro  |Rzeczywiste</br>`float`  | Rzeczywiste</br>`double` | Rzeczywiste</br>`long double` | Complex</br>`float` | Complex</br>`double` | Complex</br>`long double` |
|---------|---------|---------|---------|---------|---------|---------|
`acos` | [acosf —](reference/mbsnbicmp-mbsnbicmp-l.md) | [Acos](reference/mbsnbicmp-mbsnbicmp-l.md) | [acosl](reference/mbsnbicmp-mbsnbicmp-l.md) | [cacosf](reference/cacos-cacosf-cacosl.md) | [cacos](reference/cacos-cacosf-cacosl.md) | [cacosl](reference/cacos-cacosf-cacosl.md) |
`acosh` | [acoshf —](reference/acosh-acoshf-acoshl.md) | [ACOSH —](reference/acosh-acoshf-acoshl.md) | [acoshl](reference/acosh-acoshf-acoshl.md) | [cacoshf](reference/cacosh-cacoshf-cacoshl.md) | [cacosh](reference/cacosh-cacoshf-cacoshl.md) | [cacoshl](reference/cacosh-cacoshf-cacoshl.md) |
`asin` | [asinf —](reference/asin-asinf-asinl.md) | [Asin](reference/asin-asinf-asinl.md) | [asinl](reference/asin-asinf-asinl.md) | [casinf](reference/casin-casinf-casinl.md) | [casin](reference/casin-casinf-casinl.md) | [casinl](reference/casin-casinf-casinl.md) |
`asinh` | [asinhf —](reference/asin-asinf-asinl.md) | [ASINH —](reference/asin-asinf-asinl.md) | [asinhl](reference/asin-asinf-asinl.md) | [casinhf](reference/casinh-casinhf-casinhl.md) | [casinh](reference/casinh-casinhf-casinhl.md) | [casinhl](reference/casinh-casinhf-casinhl.md) |
`atan` | [atanf —](reference/atan-atanf-atanl-atan2-atan2f-atan2l.md) | [atan](reference/atan-atanf-atanl-atan2-atan2f-atan2l.md) | [atanl](reference/atan-atanf-atanl-atan2-atan2f-atan2l.md) | [catanf](reference/catan-catanf-catanl.md) | [catan](reference/catan-catanf-catanl.md) | [catanl](reference/catan-catanf-catanl.md) |
`atanh` | [atanhf —](reference/atanh-atanhf-atanhl.md) | [ATANH —](reference/atanh-atanhf-atanhl.md) | [atanhl](reference/atanh-atanhf-atanhl.md) | [catanhf](reference/catanh-catanhf-catanhl.md) | [catanh](reference/catanh-catanhf-catanhl.md) | [catanhl](reference/catanh-catanhf-catanhl.md) |
`cos` | [cosf —](reference/cos-cosf-cosl.md) | [cosinus](reference/cos-cosf-cosl.md) | [cosl](reference/cos-cosf-cosl.md) | [ccosf](reference/ccos-ccosf-ccosl.md) | [ccos](reference/ccos-ccosf-ccosl.md) | [ccosl](reference/ccos-ccosf-ccosl.md) |
`cosh` | [coshf —](reference/cosh-coshf-coshl.md) | [cosh —](reference/cosh-coshf-coshl.md) | [coshl](reference/cosh-coshf-coshl.md) | [ccoshf](reference/ccosh-ccoshf-ccoshl.md) | [ccosh](reference/ccosh-ccoshf-ccoshl.md) | [ccoshl](reference/ccosh-ccoshf-ccoshl.md) |
`exp` | [expf —](reference/exp-expf.md) | [EXP](reference/exp-expf.md) | [expl](reference/exp-expf.md) | [cexpf](reference/cexp-cexpf-cexpl.md) | [cexp](reference/cexp-cexpf-cexpl.md) | [cexpl](reference/cexp-cexpf-cexpl.md) |
`fabs` | [fabsf —](reference/fabs-fabsf-fabsl.md) | [fabs —](reference/fabs-fabsf-fabsl.md) | [fabsl](reference/fabs-fabsf-fabsl.md) | [cabsf](reference/cabs-cabsf-cabsl.md) | [OOZ](reference/cabs-cabsf-cabsl.md) | [OOZ](reference/cabs-cabsf-cabsl.md) |
`log` | [logf —](reference/log-logf-log10-log10f.md) | [rejestrowane](reference/log-logf-log10-log10f.md) | [logl](reference/log-logf-log10-log10f.md) | [clogf](reference/clog-clogf-clogl.md) | [clog](reference/clog-clogf-clogl.md) | [clogl](reference/clog-clogf-clogl.md) |
`pow` | [powf —](reference/pow-powf-powl.md) | [pow](reference/pow-powf-powl.md) | [powl](reference/pow-powf-powl.md) | [cpowf](reference/cpow-cpowf-cpowl.md) | [cpow](reference/cpow-cpowf-cpowl.md) | [cpowl](reference/cpow-cpowf-cpowl.md) |
`sin` | [SINF —](reference/sin-sinf-sinl.md) | [sinus](reference/sin-sinf-sinl.md) | [sinl](reference/sin-sinf-sinl.md) | [csinf](reference/csin-csinf-csinl.md) | [csin](reference/csin-csinf-csinl.md) | [csinl](reference/csin-csinf-csinl.md) |
`sinh` | [sinhf —](reference/sinh-sinhf-sinhl.md) | [SINH](reference/sinh-sinhf-sinhl.md) | [SINH](reference/sinh-sinhf-sinhl.md) | [csinhf](reference/csinh-csinhf-csinhl.md) | [csinh](reference/csinh-csinhf-csinhl.md) | [csinhl](reference/csinh-csinhf-csinhl.md) |
`sqrt` | [sqrtf —](reference/sqrt-sqrtf-sqrtl.md) | [sqrt](reference/sqrt-sqrtf-sqrtl.md) | [sqrt](reference/sqrt-sqrtf-sqrtl.md) | [csqrtf](reference/csqrt-csqrtf-csqrtl.md) | [csqrt](reference/csqrt-csqrtf-csqrtl.md) | [csqrtl](reference/csqrt-csqrtf-csqrtl.md) |
`tan` | [TANF —](reference/tan-tanf-tanl.md) | [Tan](reference/tan-tanf-tanl.md) | [tanl](reference/tan-tanf-tanl.md) | [ctanf](reference/ctan-ctanf-ctanl.md) | [ctan](reference/ctan-ctanf-ctanl.md) | [ctanl](reference/ctan-ctanf-ctanl.md) |
`tanh` | [tanhf —](reference/tanh-tanhf-tanhl.md) | [TANH —](reference/tanh-tanhf-tanhl.md) | [tanhl](reference/tanh-tanhf-tanhl.md) | [ctanhf](reference/ctanh-ctanhf-ctanhl.md) | [ctanh](reference/ctanh-ctanhf-ctanhl.md) | [ctanhl](reference/ctanh-ctanhf-ctanhl.md) |
`atan2` | [atan2f —](reference/atan-atanf-atanl-atan2-atan2f-atan2l.md) | [atan2](reference/atan-atanf-atanl-atan2-atan2f-atan2l.md) | [atan2l](reference/atan-atanf-atanl-atan2-atan2f-atan2l.md) | - | - | - |
`cbrt` | [cbrtf —](reference/cbrt-cbrtf-cbrtl.md) | [cbrt —](reference/cbrt-cbrtf-cbrtl.md) | [cbrtl](reference/cbrt-cbrtf-cbrtl.md) | - | - | - |
`ceil` | [ceilf —](reference/ceil-ceilf-ceill.md) | [CEIL —](reference/ceil-ceilf-ceill.md) | [ceill](reference/ceil-ceilf-ceill.md) | - | - | - |
`copysign` | [copysignf —](reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md) | [copysign —](reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md) | [copysignl](reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md) | - | - | - |
`erf` | [erff —](reference/erf-erff-erfl-erfc-erfcf-erfcl.md) | [Funkcja](reference/erf-erff-erfl-erfc-erfcf-erfcl.md) | [erfl](reference/erf-erff-erfl-erfc-erfcf-erfcl.md) | - | - | - |
`erfc` | [erfcf —](reference/erf-erff-erfl-erfc-erfcf-erfcl.md) | [ERFC —](reference/erf-erff-erfl-erfc-erfcf-erfcl.md) | [erfcl](reference/erf-erff-erfl-erfc-erfcf-erfcl.md) | - | - | - |
`exp2` | [exp2f —](reference/exp2-exp2f-exp2l.md) | [exp2 —](reference/exp2-exp2f-exp2l.md) | [exp2l](reference/exp2-exp2f-exp2l.md) | - | - | - |
`expm1` | [expm1f —](reference/expm1-expm1f-expm1l.md) | [expm1 —](reference/expm1-expm1f-expm1l.md) | [expm1l](reference/expm1-expm1f-expm1l.md) | - | - | - |
`fdim` | [fdimf —](reference/fdim-fdimf-fdiml.md) | [fdim —](reference/fdim-fdimf-fdiml.md) | [fdiml](reference/fdim-fdimf-fdiml.md) | - | - | - |
`floor` | [floorf —](reference/floor-floorf-floorl.md) | [wykładzin](reference/floor-floorf-floorl.md) | [piętro](reference/floor-floorf-floorl.md) | - | - | - |
`fma` | [fmaf —](reference/fma-fmaf-fmal.md) | [FMA](reference/fma-fmaf-fmal.md) | [fmal](reference/fma-fmaf-fmal.md) | - | - | - |
`fmax` | [fmaxf —](reference/fmax-fmaxf-fmaxl.md) | [Fmax —](reference/fmax-fmaxf-fmaxl.md) | [fmaxl](reference/fmax-fmaxf-fmaxl.md) | - | - | - |
`fmin` | [fminf —](reference/fmin-fminf-fminl.md) | [fmin —](reference/fmin-fminf-fminl.md) | [fminl](reference/fmin-fminf-fminl.md) | - | - | - |
`fmod` | [fmodf —](reference/fmod-fmodf.md) | [FMOD —](reference/fmod-fmodf.md) | [fmodl](reference/fmod-fmodf.md) | - | - | - |
`frexp` | [frexpf —](reference/frexp.md) | [frexp](reference/frexp.md) | [frexpl](reference/frexp.md) | - | - | - |
`hypot` | [hypotf —](reference/hypot-hypotf-hypotl-hypot-hypotf-hypotl.md) | [hypot —](reference/hypot-hypotf-hypotl-hypot-hypotf-hypotl.md) | [hypotl](reference/hypot-hypotf-hypotl-hypot-hypotf-hypotl.md) | - | - | - |
`ilogb` | [ilogbf —](reference/ilogb-ilogbf-ilogbl2.md) | [ilogb —](reference/ilogb-ilogbf-ilogbl2.md) | [ilogbl](reference/ilogb-ilogbf-ilogbl2.md) | - | - | - |
`ldexp` | [ldexpf —](reference/ldexp.md) | [ldexp](reference/ldexp.md) | [ldexpl](reference/ldexp.md) | - | - | - |
`lgamma` | [lgammaf —](reference/lgamma-lgammaf-lgammal.md) | [lgamma —](reference/lgamma-lgammaf-lgammal.md) | [lgammal](reference/lgamma-lgammaf-lgammal.md) | - | - | - |
`llrint` | [llrintf](reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md) | [llrint](reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md) | [llrintl](reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md) | - | - | - |
`llround` | [llroundf](reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md) | [llround](reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md) | [llroundl](reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md) | - | - | - |
`log10` | [log10f —](reference/log-logf-log10-log10f.md) | [log10 —](reference/log-logf-log10-log10f.md) | [log10l](reference/log-logf-log10-log10f.md) | - | - | - |
`log1p` | [log1pf —](reference/log1p-log1pf-log1pl2.md) | [log1p —](reference/log1p-log1pf-log1pl2.md) | [log1pl](reference/log1p-log1pf-log1pl2.md) | - | - | - |
`log2` | [log2f —](reference/log2-log2f-log2l.md) | [log2 —](reference/log2-log2f-log2l.md) | [log2l](reference/log2-log2f-log2l.md) | - | - | - |
`logb` | [logbf —](reference/logb-logbf-logbl-logb-logbf.md) | [logb —](reference/logb-logbf-logbl-logb-logbf.md) | [logbl](reference/logb-logbf-logbl-logb-logbf.md) | - | - | - |
`lrint` | [lrintf](reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md) | [lrint](reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md) | [lrintl](reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md) | - | - | - |
`lround` | [lroundf](reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md) | [lround](reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md) | [lroundl](reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md) | - | - | - |
`nearbyint` | [nearbyintf —](reference/nearbyint-nearbyintf-nearbyintl1.md) | [nearbyint —](reference/nearbyint-nearbyintf-nearbyintl1.md) | [nearbyintl](reference/nearbyint-nearbyintf-nearbyintl1.md) | - | - | - |
`nextafter` | [nextafterf —](reference/nextafter-functions.md) | [nextafter —](reference/nextafter-functions.md) | [nextafterl](reference/nextafter-functions.md) | - | - | - |
`nexttoward` | [nexttowardf](reference/nextafter-functions.md) | [nexttoward](reference/nextafter-functions.md) | [nexttowardl](reference/nextafter-functions.md) | - | - | - |
`remainder` | [remainderf —](reference/remainder-remainderf-remainderl.md) | [pozostałej części](reference/remainder-remainderf-remainderl.md) | [reszta](reference/remainder-remainderf-remainderl.md) | - | - | - |
`remquo` | [remquof —](reference/remquo-remquof-remquol.md) | [remquo —](reference/remquo-remquof-remquol.md) | [remquol](reference/remquo-remquof-remquol.md) | - | - | - |
`rint` | [rintf](reference/rint-rintf-rintl.md) | [rukuj](reference/rint-rintf-rintl.md) | [rintl](reference/rint-rintf-rintl.md) | - | - | - |
`round` | [roundf —](reference/round-roundf-roundl.md) | [Nit](reference/round-roundf-roundl.md) | [Zaokrąglij](reference/round-roundf-roundl.md) | - | - | - |
`scalbln` | [scalblnf](reference/scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl.md) | [scalbln](reference/scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl.md) | [scalblnl](reference/scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl.md) | - | - | - |
`scalbn` | [scalbnf —](reference/scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl.md) | [scalbn —](reference/scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl.md) | [scalbnl](reference/scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl.md) | - | - | - |
`tgamma` | [tgammaf —](reference/tgamma-tgammaf-tgammal.md) | [tgamma —](reference/tgamma-tgammaf-tgammal.md) | [tgammal](reference/tgamma-tgammaf-tgammal.md) | - | - | - |
`trunc` | [truncf —](reference/trunc-truncf-truncl.md) | [TRUNC —](reference/trunc-truncf-truncl.md) | [truncl](reference/trunc-truncf-truncl.md) | - | - | - |
`carg` | - | - | - | [cargf](reference/carg-cargf-cargl.md) | [carg](reference/carg-cargf-cargl.md) | [cargl](reference/carg-cargf-cargl.md) |
`conj` | - | - | - | [conjf](reference/conj-conjf-conjl.md) | [conj](reference/conj-conjf-conjl.md) | [conjl](reference/conj-conjf-conjl.md) |
`creal` | - | - | - | [crealf](reference/creal-crealf-creall.md) | [creal](reference/creal-crealf-creall.md) | [creall](reference/creal-crealf-creall.md) |
`cimag` | - | - | - | [cimagf](reference/cimag-cimagf-cimagl.md) | [cimag](reference/cimag-cimagf-cimagl.md) | [cimagl](reference/cimag-cimagf-cimagl.md) |
`cproj` | - | - | - | [cprojf](reference/cproj-cprojf-cprojl.md) | [cproj](reference/cproj-cprojf-cprojl.md) | [cprojl](reference/cproj-cprojf-cprojl.md) |

## <a name="requirements"></a>Wymagania

wymagana jest wartość [std: c++ 11](../build/reference/std-specify-language-standard-version.md) lub nowsza.

Windows SDK w wersji 10.0.20201.0 lub nowszej.

## <a name="see-also"></a>Zobacz też

[Dokumentacja biblioteki wykonawczej języka C](c-run-time-library-reference.md)
