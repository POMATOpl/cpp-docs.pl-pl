---
description: 'Dowiedz się więcej o języku: opakowanie (C++/CLI)'
title: Konwersja boxing (C++/CLI)
ms.date: 11/04/2016
ms.assetid: f4ee27a8-6a34-432d-b9ec-39285d513b23
ms.openlocfilehash: 4914271dc5b1ae0bcee2a82b3cddb4433a2dc84f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282591"
---
# <a name="boxing-ccli"></a>Konwersja boxing (C++/CLI)

Opakowanie to proces konwersji typu wartości na typ `object` lub dowolny typ interfejsu, który jest implementowany przez typ wartości. Gdy typ wartości pola środowiska uruchomieniowego języka wspólnego (CLR), zawija `System.Object` on wartość i zapisuje je na zarządzanym stosie. Rozpakowywanie wyodrębnia typ wartości z obiektu. Opakowanie jest niejawne; Rozpakowywanie jest jawne.

## <a name="related-articles"></a>Powiązane artykuły

|Tytuł|Opis|
|-----------|-----------------|
|[Jak jawnie zażądać opakowania](../dotnet/how-to-explicitly-request-boxing.md)|Opisuje, jak jawnie zażądać opakowania na zmiennej.|
|[Instrukcje: użycie gcnew do tworzenia typów wartości i użycie niejawnego opakowania](../dotnet/how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing.md)|Pokazuje, jak używać **`gcnew`** do tworzenia opakowanych typów wartości, które można umieścić na zarządzanej stercie.|
|[Instrukcje: Rozpakowywanie](../dotnet/how-to-unbox.md)|Pokazuje, jak Unbox i modyfikować wartość.|
|[Konwersje standardowe i niejawny opakowanie](../dotnet/standard-conversions-and-implicit-boxing.md)|Pokazuje, że konwersja standardowa jest wybierana przez kompilator nad konwersją wymagającą opakowania.|
|[Programowanie .NET w języku C++/interfejsie wiersza polecenia (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)|Artykuł najwyższego poziomu dla programowania .NET w dokumentacji Visual C++.|
