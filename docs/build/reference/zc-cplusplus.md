---
description: 'Dowiedz się więcej o:/Zc: __cplusplus (Włącz zaktualizowane __cplusplus makro)'
title: /Zc:__cplusplus (Włącz zaktualizowane makro __cplusplus)
ms.date: 05/16/2019
f1_keywords:
- /Zc:__cplusplus
helpviewer_keywords:
- -Zc:__cplusplus compiler option (C++)
- __cplusplus macro (C++)
ms.openlocfilehash: 3aa5579a0315c2bba5e74a8a3c191801328fc589
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114679"
---
# <a name="zc__cplusplus-enable-updated-__cplusplus-macro"></a>/Zc:__cplusplus (Włącz zaktualizowane makro __cplusplus)

Opcja kompilatora **/Zc: __cplusplus** włącza makro preprocesora **\_ \_ cplusplus** , aby zgłosić zaktualizowaną wartość dla ostatnich obsługiwanych standardów języka C++. Domyślnie program Visual Studio zawsze zwraca wartość "199711L" dla makra preprocesora **\_ \_ cplusplus** .

## <a name="syntax"></a>Składnia

> **/Zc: __cplusplus**[ **-** ]

## <a name="remarks"></a>Uwagi

Makro preprocesora **\_ \_ cplusplus** jest często używane do raportowania obsługi określonej wersji standardu C++. Ze względu na to, że wiele istniejących kodów jest zależne od wartości tego makra pasującego do "199711L", kompilator nie zmienia wartości makra, chyba że jawnie zazrezygnujesz przy użyciu opcji kompilatora **/Zc: __cplusplus** . Opcja **/Zc: __cplusplus** jest dostępna począwszy od programu Visual Studio 2017 w wersji 15,7 i jest domyślnie wyłączona. We wcześniejszych wersjach programu Visual Studio i domyślnie, lub jeśli **/Zc: __cplusplus-** jest określony, program Visual Studio zwraca wartość "199711L" dla makra preprocesora **\_ \_ cplusplus** . Opcja [/permissive-](permissive-standards-conformance.md) nie włącza **/Zc: __cplusplus**.

Gdy opcja **/Zc: __cplusplus** jest włączona, wartość raportowana przez makro **\_ \_ cplusplus** zależy od ustawienia przełącznika wersji [/STD](std-specify-language-standard-version.md) . W tej tabeli przedstawiono możliwe wartości dla makra:

|/Zc: przełącznik __cplusplus|/std: przełącznik c++|wartość __cplusplus|
|-|-|-|
Zc: __cplusplus|/std: c++ 14 (wartość domyślna)|201402L
Zc: __cplusplus|/std: c++ 17|201703L
Zc: __cplusplus|/std: c + + Najnowsza|201704L
Zc: __cplusplus — (wyłączone)|Dowolna wartość|199711L
Nie określono|Dowolna wartość|199711L

Kompilator nie obsługuje przełączników Standards dla języków C++ 98, C++ 03 i C++ 11.

Aby uzyskać bardziej szczegółowe wykrywanie zmian w zestawie narzędzi kompilatora, Użyj wstępnie zdefiniowanego makra [_MSC_VER](../../preprocessor/predefined-macros.md) . Wartość tego wbudowanego makra jest zwiększana dla każdej aktualizacji zestawu narzędzi w programie Visual Studio 2017 i nowszych wersjach. Wstępnie zdefiniowane makro raportuje wersję standardową, czy opcja **/Zc: __cplusplus** jest włączona czy wyłączona. [_MSVC_LANG](../../preprocessor/predefined-macros.md) Gdy **/Zc: __cplusplus** jest włączona, `__cplusplus == _MSVC_LANG` .

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Aby ustawić tę opcję kompilatora w programie Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz   >  stronę właściwości konfiguracja wiersza polecenia **C/C++**  >   .

1. Dodaj **/Zc: __cplusplus** lub **/Zc: __cplusplus —** do okienka **Opcje dodatkowe:** .

## <a name="see-also"></a>Zobacz też

- [/Zc (Zgodność)](zc-conformance.md)
- [/std (Określ wersję standardu języka)](std-specify-language-standard-version.md)
- [Wstępnie zdefiniowane makra](../../preprocessor/predefined-macros.md)
