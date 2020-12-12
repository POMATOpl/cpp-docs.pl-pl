---
description: 'Dowiedz się więcej na temat: dołączanie nazw plików w cudzysłowie'
title: Łącznie z nazwami plików w cudzysłowie
ms.date: 11/04/2016
ms.assetid: 789a047e-ea38-4c99-b71d-a2ad9c81daee
ms.openlocfilehash: b07d8dc04106a330644c30bffd1e8f36fc81fb6d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137634"
---
# <a name="including-quoted-filenames"></a>Łącznie z nazwami plików w cudzysłowie

**3.8.2 ANSI** Obsługa nazw ujętych w cudzysłów dla plików źródłowych zawarcia

Jeśli określisz kompletną, jednoznaczną specyfikację ścieżki dla pliku dołączanego między dwoma zestawami podwójnych cudzysłowów (""), preprocesor przeszukuje tylko tę specyfikację ścieżki i ignoruje katalogi standardowe.

W przypadku plików dołączanych określonych jako [#include](../preprocessor/hash-include-directive-c-cpp.md) "path-spec" wyszukiwanie w katalogu rozpoczyna się od katalogów pliku nadrzędnego, a następnie przechodzi przez katalogi plików nadrzędnych. W rezultacie wyszukiwanie rozpoczyna się względem katalogu zawierającego plik źródłowy, który jest aktualnie przetwarzany. Jeśli nie ma pliku nadrzędnego i nie znaleziono pliku, wyszukiwanie jest kontynuowane tak, jakby nazwa pliku została ujęta w nawiasy ostre.

## <a name="see-also"></a>Zobacz też

[Dyrektywy przetwarzania wstępnego](../c-language/preprocessing-directives.md)
