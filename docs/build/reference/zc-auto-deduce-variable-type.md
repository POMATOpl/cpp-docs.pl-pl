---
description: 'Dowiedz się więcej na temat: `/Zc:auto` (wywnioskowanie typu zmiennej)'
title: /Zc:auto (Dedukuj typ zmiennej)
ms.date: 02/28/2018
f1_keywords:
- /Zc:auto
helpviewer_keywords:
- -Zc compiler options (C++)
- Deduce variable type (C++)
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 5f5bc102-44c3-4688-bbe1-080594dcee5c
ms.openlocfilehash: d20f377fc653e9c3cceb5c3e81b5e5e8a815bcad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114718"
---
# <a name="zcauto-deduce-variable-type"></a>`/Zc:auto` (Wywnioskowanie typu zmiennej)

**`/Zc:auto`** Opcja kompilatora instruuje kompilator, jak używać [ `auto` słowa kluczowego](../../cpp/auto-cpp.md) do deklarowania zmiennych. Jeśli określisz opcję domyślną, kompilator wystawia **`/Zc:auto`** Typ zadeklarowanej zmiennej z jej wyrażenia inicjującego. Jeśli określisz **`/Zc:auto-`** , kompilator przydzieli zmienną do automatycznej klasy magazynu.

## <a name="syntax"></a>Składnia

> **`/Zc:auto`**[**`-`**]

## <a name="remarks"></a>Uwagi

Standard C++ definiuje oryginalne i zmienione znaczenie **`auto`** słowa kluczowego. Przed Visual Studio 2010 słowo kluczowe deklaruje zmienną w klasie magazynu automatycznego; oznacza to, że zmienna, która ma lokalny okres istnienia. Począwszy od programu Visual Studio 2010, słowo kluczowe ustala typ zmiennej w wyrażeniu inicjalizacji deklaracji. Użyj **`/Zc:auto`** opcji kompilatora, aby poinformować kompilator, aby używał zweryfikowanego znaczenia **`auto`** słowa kluczowego. **`/Zc:auto`** Opcja jest domyślnie włączona. [`/permissive-`](permissive-standards-conformance.md)Opcja nie zmienia domyślnego ustawienia **`/Zc:auto`** .

Kompilator emituje odpowiedni komunikat diagnostyczny, jeśli użycie **`auto`** słowa kluczowego wyklucza bieżącą **`/Zc:auto`** opcję kompilatora. Aby uzyskać więcej informacji, zobacz [ `auto` słowo kluczowe](../../cpp/auto-cpp.md). Aby uzyskać więcej informacji na temat problemów ze zgodnością Visual C++, zobacz [niestandardowe zachowanie](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Aby ustawić tę opcję kompilatora w programie Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz   >  stronę właściwości konfiguracja wiersza polecenia **C/C++**  >   .

1. Dodaj **`/Zc:auto`** lub **`/Zc:auto-`** do **opcji dodatkowe:** okienko.

## <a name="see-also"></a>Zobacz też

[`/Zc` Zgodności](zc-conformance.md)<br/>
[`auto` Kodu](../../cpp/auto-cpp.md)
