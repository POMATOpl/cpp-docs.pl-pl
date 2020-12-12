---
description: 'Dowiedz się więcej o:/Zc: sizedDealloc (Włącz funkcje cofania alokacji o rozmiarze globalnym)'
title: '/Zc: sizedDealloc (Włącz funkcje cofania alokacji o rozmiarze globalnym)'
ms.date: 03/06/2018
f1_keywords:
- sizedDealloc
- /Zc:sizedDealloc
helpviewer_keywords:
- -Zc compiler options (C++)
- sizedDealloc
- Enable Global Sized Deallocation Functions
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 3a73ace0-4d36-420a-b699-0ca6fc0dd134
ms.openlocfilehash: 4e40355dc3c61f725ca9996dc4c91c0604866fe4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269071"
---
# <a name="zcsizeddealloc-enable-global-sized-deallocation-functions"></a>/Zc: sizedDealloc (Włącz funkcje cofania alokacji o rozmiarze globalnym)

Opcja kompilatora **/Zc: sizedDealloc** instruuje kompilator, aby preferencyjnie wywoływać globalne `operator delete` lub `operator delete[]` funkcje, które mają drugi parametr typu, `size_t` gdy rozmiar obiektu jest dostępny. Te funkcje mogą używać `size_t` parametru do optymalizowania wydajności dealokacji.

## <a name="syntax"></a>Składnia

> **/Zc: sizedDealloc**[ **-** ]

## <a name="remarks"></a>Uwagi

W standardzie C++ 11 można definiować statyczne funkcje członkowskie, `operator delete` `operator delete[]` które pobierają drugi `size_t` parametr. Zazwyczaj są one używane w połączeniu z [operatorami New](../../cpp/new-operator-cpp.md) Functions w celu implementowania bardziej wydajnych przystawek i dealokacji dla obiektu. Jednak język C++ 11 nie definiuje równoważnego zestawu funkcji cofania alokacji w zakresie globalnym. W języku C++ 11 globalne funkcje cofania alokacji, które mają drugi parametr typu, `size_t` są uznawane za funkcje usuwania umieszczania. Muszą być jawnie wywoływane przez przekazanie argumentu size.

Standard C++ 14 zmienia zachowanie kompilatora. Podczas definiowania globalnego `operator delete` i `operator delete[]` który przyjmuje drugi parametr typu `size_t` , kompilator preferuje wywołania tych funkcji, gdy wersje zakresów elementów członkowskich nie są wywoływane i rozmiar obiektu jest dostępny. Kompilator przekazuje argument size niejawnie. Wersje pojedynczego argumentu są wywoływane, gdy kompilator nie może określić rozmiaru cofania przydziału obiektu. W przeciwnym razie zwykle stosowane są reguły umożliwiające wybranie wersji funkcji cofania alokacji. Wywołania funkcji globalnych można jawnie określić przez zaczekanie operatora rozpoznawania zakresu ( `::` ) do wywołania funkcji cofania alokacji.

Domyślnie Visual C++ począwszy od programu Visual Studio 2015 implementuje to standardowe zachowanie języka C++ 14. Można to jawnie określić, ustawiając opcję kompilatora **/Zc: sizedDealloc** . Reprezentuje to potencjalnie nieprzerwaną zmianę. Użyj opcji **/Zc: sizedDealloc-** , aby zachować stare zachowanie, na przykład gdy kod definiuje operatory usuwania umieszczania, które używają drugiego parametru typu `size_t` . Domyślne implementacje bibliotek programu Visual Studio globalnych funkcji cofania alokacji, które mają drugi parametr typu, `size_t` wywołują pojedyncze wersje parametrów. Jeśli kod zawiera tylko jeden parametr globalny operator delete i operator delete [], domyślne implementacje funkcji cofania alokacji o rozmiarze globalnym wywołują funkcje globalne.

Opcja kompilatora **/Zc: sizedDealloc** jest domyślnie włączona. Opcja [/permissive-](permissive-standards-conformance.md) nie ma wpływu na **/Zc: sizedDealloc**.

Aby uzyskać więcej informacji na temat problemów ze zgodnością w Visual C++, zobacz [niestandardowe zachowanie](../../cpp/nonstandard-behavior.md).

## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Z menu rozwijanego **konfiguracje** wybierz pozycję **wszystkie konfiguracje**.

1. Wybierz   >  stronę właściwości konfiguracja wiersza polecenia **C/C++**  >   .

1. Zmodyfikuj właściwość **Opcje dodatkowe** , aby uwzględnić **/Zc: sizedDealloc** lub **/Zc: sizedDealloc-** , a następnie wybierz **przycisk OK**.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)<br/>
[/Zc (Zgodność)](zc-conformance.md)<br/>
