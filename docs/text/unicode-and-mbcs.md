---
description: 'Dowiedz się więcej na temat: Unicode i MBCS'
title: Unicode i MBCS
ms.date: 11/04/2016
helpviewer_keywords:
- MBCS [C++], Unicode
- MFC [C++], character sets
- character sets [C++], multibyte
- run-time libraries [C++], language portability
- character sets [C++], Unicode
- Unicode [C++], MFC and C run-time functions
- multibyte characters [C++]
- runtime [C++], language portability
ms.assetid: 677baec6-71b4-4579-94df-64f18bc117c4
ms.openlocfilehash: 4fc5afc447612a3f08067185072cd4f116ab80c3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114978"
---
# <a name="unicode-and-mbcs"></a>Unicode i MBCS

Microsoft Foundation Classes (MFC), Biblioteka wykonawcza C dla Visual C++ i środowisko deweloperskie Visual C++ są włączone, aby pomóc w programowaniu międzynarodowym. Zapewniają one:

- Obsługa standardu Unicode w systemie Windows. Unicode jest bieżącym standardem i powinien być używany zawsze, gdy jest to możliwe.

   Unicode jest kodowaniem znaków 16-bitowym, co zapewnia wystarczającą liczbę kodowań dla wszystkich języków. Wszystkie znaki ASCII są zawarte w kodzie Unicode jako znaki rozszerzone.

- Obsługa formy zestawu znaków wielobajtowych (MBCS) o nazwie podwójnego bajtu (DBCS) na wszystkich platformach.

   Znaki DBCS składają się z 1 lub 2 bajtów. Niektóre zakresy bajtów są przeznaczone do użycia jako bajty potencjalnego klienta. Bajt wiodący określa, że i następujący bajt końcowy zawiera pojedynczy dwubajtowy znak. Należy śledzić, które bajty mają potencjalną liczbę bajtów. W konkretnym zestawie znaków wielobajtowych potencjalni klienci mieszczą się w określonym zakresie, tak jak w przypadku bajtów końcowych. Gdy te zakresy nakładają się na siebie, może być konieczne oszacowanie kontekstu, aby określić, czy dany bajt działa jako bajt wiodący czy bajt końcowy.

- Obsługa narzędzi, które upraszczają MBCS Programowanie aplikacji pisanych na rynki międzynarodowe.

   W przypadku uruchamiania w MBCSej wersji systemu operacyjnego Windows, system programistyczny, Visual C++ w tym zintegrowany edytor kodu źródłowego, debuger i narzędzia wiersza polecenia — są całkowicie MBCS. Aby uzyskać więcej informacji, zobacz [Obsługa MBCS w Visual C++](../text/mbcs-support-in-visual-cpp.md).

> [!NOTE]
> W tej dokumentacji MBCS jest używany do opisywania całej obsługi znaków wielobajtowych w formacie Unicode. W Visual C++ MBCS zawsze oznacza DBCS. Zestawy znaków większe niż 2 bajty nie są obsługiwane.

Zgodnie z definicją zestaw znaków ASCII jest podzbiorem wszystkich zestawów znaków wielobajtowych. W wielu zestawach znaków wielobajtowych każdy znak w zakresie 0x00-0x7F jest identyczny ze znakiem, który ma taką samą wartość w zestawie znaków ASCII. Na przykład w przypadku ciągów znaków ASCII i MBCS, 1-bajtowy znak NULL (' \ 0 ') ma wartość 0x00 i wskazuje kończący znak null.

## <a name="see-also"></a>Zobacz też

[Tekst i ciągi](../text/text-and-strings-in-visual-cpp.md)<br/>
[Włączanie międzynarodowe](../text/international-enabling.md)
