---
description: 'Dowiedz się więcej na temat: _environ, _wenviron'
title: _environ, _wenviron
ms.date: 11/04/2016
f1_keywords:
- environ
- wenviron
- _wenviron
- _environ
helpviewer_keywords:
- environ function
- _environ function
- _wenviron function
- process environment
- wenviron function
ms.assetid: 7e639962-6536-47cd-8095-0cbe44a56e03
ms.openlocfilehash: e1a69bec6fa93373c74e1f73de469bc3b93158e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305055"
---
# <a name="_environ-_wenviron"></a>_environ, _wenviron

`_environ`Zmienna jest wskaźnikiem do tablicy wskaźników do ciągów znaków wielobajtowych, które stanowią środowisko procesu. Ta zmienna globalna została uznana za przestarzałą dla bezpieczniejszych wersji funkcjonalnych [getenv_s, _wgetenv_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md) i [_putenv_s _wputenv_s](../c-runtime-library/reference/putenv-s-wputenv-s.md), które powinny być używane zamiast zmiennej globalnej. `_environ` jest zadeklarowany w STDLIB. h.

> [!IMPORTANT]
> Tego interfejsu API nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows. Aby uzyskać więcej informacji, zobacz [funkcje CRT nieobsługiwane w aplikacjach platforma uniwersalna systemu Windows](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Składnia

```
extern char **_environ;
```

## <a name="remarks"></a>Uwagi

W programie, który używa `main` funkcji, `_environ` jest inicjowany podczas uruchamiania programu zgodnie z ustawieniami podanymi w środowisku systemu operacyjnego. Środowisko składa się z co najmniej jednego wpisu w formularzu

`ENVVARNAME` `=string`

`getenv_s` i `putenv_s` Użyj `_environ` zmiennej, aby uzyskać dostęp do tabeli środowiska i zmodyfikować ją. Gdy `_putenv` jest wywoływana w celu dodania lub usunięcia ustawień środowiska, tabela środowiskowa zmienia rozmiar. Jego lokalizacja w pamięci może także ulec zmianie, w zależności od wymagań dotyczących pamięci programu. Wartość `_environ` jest odpowiednio ustawiana automatycznie.

`_wenviron`Zmienna zadeklarowana w STDLIB. h jako:

```
extern wchar_t **_wenviron;
```

to wersja znaku dwubajtowego `_environ` . W programie, który używa `wmain` funkcji, `_wenviron` jest inicjowany podczas uruchamiania programu zgodnie z ustawieniami podanymi w środowisku systemu operacyjnego.

W programie, który używa `main` , `_wenviron` jest początkowo **wartość null** , ponieważ środowisko składa się z ciągów znaków wielobajtowych. Przy pierwszym wywołaniu `_wgetenv` lub `_wputenv` , odpowiednim środowisku ciągu znaków dwubajtowych jest tworzony i jest wskazywany przez `_wenviron` .

Podobnie w programie, który używa `wmain` , `_environ` jest początkowo **wartość null** , ponieważ środowisko składa się z ciągów znaków dwubajtowych. Przy pierwszym wywołaniu `_getenv` lub `_putenv` , odpowiednie środowisko ciągu znaków wielobajtowych jest tworzone i jest wskazywane przez `_environ` .

Gdy dwie kopie środowiska (MBCS i Unicode) istnieją jednocześnie w programie, system czasu wykonywania musi zachować obie kopie, co powoduje wolniejszy czas wykonywania. Na przykład za każdym razem, gdy `_putenv` jest wywoływana, wywołanie `_wputenv` jest również wykonywane automatycznie, dzięki czemu dwa ciągi środowiska odpowiadają.

> [!CAUTION]
> W rzadkich przypadkach, gdy system czasu wykonywania zachowuje zarówno wersję standardu Unicode, jak i wielobajtowe wersje środowiska, te systemy mogą nie odpowiadać dokładnie. Wynika to z faktu, że wszystkie unikatowe ciągi znaków wielobajtowych są mapowane na unikatowy ciąg Unicode, mapowanie z unikatowego ciągu Unicode na ciąg znaków wielobajtowych nie musi być unikatowe. W związku z tym dwa różne ciągi Unicode mogą być mapowane na ten sam ciąg wielobajtowy.

Sondowanie `_environ` w kontekście Unicode ma znaczenie bez względu [](../build/reference/md-mt-ld-use-run-time-library.md) na to, kiedy `/MDd` jest używane/MD lub połączenie. Dla biblioteki DLL CRT typ (szeroki lub wielobajtowy) programu jest nieznany. Tworzony jest tylko typ wielobajtowy, ponieważ jest to najbardziej prawdopodobną przyczyną scenariusza.

Następujący pseudo kod ilustruje, jak to możliwe.

```
int i, j;
i = _wputenv( "env_var_x=string1" );  // results in the implicit call:
                                      // putenv ("env_var_z=string1")
j = _wputenv( "env_var_y=string2" );  // also results in implicit call:
                                      // putenv("env_var_z=string2")
```

W notacji używanej w tym przykładzie ciągi znaków nie są literałami ciągu C. Zamiast tego są to symbole zastępcze reprezentujące literały ciągu środowiska Unicode w `_wputenv` ciągach środowiska wywołań i wielobajtowych w `putenv` wywołaniu. Symbole zastępcze znaku " `x` " i " `y` " w dwóch odrębnych ciągach środowiska Unicode nie są mapowane do znaków w bieżącym MBCS. Zamiast tego, obie mapują do pewnego znaku MBCS " `z` ", który jest domyślnym wynikiem próby konwersji ciągów.

W takim przypadku w środowisku wielobajtowym wartość " `env_var_z` " po pierwszym niejawnym wywołaniu `putenv` zostałby " `string1` ", ale ta wartość zostałaby zapisywana w drugim niejawnym wywołaniu do `putenv` , gdy wartość " `env_var_z` " jest ustawiona na "" `string2` . Środowisko Unicode (w programie `_wenviron` ) i środowisko wielobajtowe (w `_environ` ) różnią się w zależności od tej serii wywołań.

## <a name="see-also"></a>Zobacz też

[Zmienne globalne](../c-runtime-library/global-variables.md)<br/>
[getenv, _wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)<br/>
[getenv_s, _wgetenv_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)<br/>
[_putenv, _wputenv](../c-runtime-library/reference/putenv-wputenv.md)<br/>
[_putenv_s, _wputenv_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)
