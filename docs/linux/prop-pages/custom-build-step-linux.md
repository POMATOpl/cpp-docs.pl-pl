---
description: 'Dowiedz się więcej na temat: niestandardowe właściwości kroku kompilacji (Linux C++)'
title: Właściwości niestandardowego kroku kompilacji (Linux C++)
ms.date: 06/07/2019
ms.assetid: 77a9c1fb-7c41-4a9b-9418-18ac17ce4e74
ms.openlocfilehash: d8a120d147d107cd96f77556a412aa8ee6636548
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169778"
---
# <a name="custom-build-step-properties-linux-c"></a>Właściwości niestandardowego kroku kompilacji (Linux C++)

::: moniker range="msvc-140"

Obsługa systemu Linux jest dostępna w programie Visual Studio 2017 i nowszych.

::: moniker-end

::: moniker range=">=msvc-150"

| Właściwość | Opis |
|--|--|
| Wiersz polecenia | Polecenie wykonywane przez krok niestandardowej kompilacji. |
| Opis | Komunikat, który jest wyświetlany podczas wykonywania kroku niestandardowej kompilacji. |
| Dane wyjściowe | Plik wyjściowy, generowany przez krok niestandardowej kompilacji. To ustawienie jest wymagane, aby kompilacje przyrostowe działały poprawnie. |
| Dodatkowe zależności | Rozdzielana średnikami lista wszelkich dodatkowych plików wejściowych dla kroku niestandardowej kompilacji. |
| Wykonaj po i wykonaj przed | Te opcje definiują, kiedy krok niestandardowej kompilacji jest uruchamiany w procesie kompilacji w stosunku do wymienionych celów. Najczęściej wymienione cele to BuildGenerateSources, BuildCompile i BuildLink, ponieważ stanowią one najważniejsze kroki procesu kompilacji. Inne często wymienione cele to Midl, CLCompile i Link. |
| Traktuj dane wyjściowe jako zawartość | Ta opcja ma znaczenie tylko w przypadku aplikacji Microsoft Store lub Windows Phone, które obejmują wszystkie pliki zawartości w pakiecie. appx. |

::: moniker-end
