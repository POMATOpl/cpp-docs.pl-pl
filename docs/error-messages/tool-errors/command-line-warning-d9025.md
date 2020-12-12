---
description: 'Dowiedz się więcej na temat: Command-Line Warning D9025'
title: Ostrzeżenie D9025 dla wiersza polecenia
ms.date: 11/04/2016
f1_keywords:
- D9025
helpviewer_keywords:
- D9025
ms.assetid: 6edff72c-1508-46c2-99f4-0e4b3c5e60c9
ms.openlocfilehash: 8cec7bdb5f3816c33d395e8ae93a861a29e94c64
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115498"
---
# <a name="command-line-warning-d9025"></a>Ostrzeżenie D9025 dla wiersza polecenia

zastępowanie "opcja1" opcją "opcja2"

Opcja *opcja1* została określona, ale została przesłonięta przez *opcja2*. Użyto opcji *opcja2* .

Jeśli dwie opcje określają sprzeczne lub niezgodne dyrektywy, zostanie użyta dyrektywa określona lub implikowana w opcji znajdującej się najdalej z prawej strony w wierszu polecenia.

Jeśli zostanie wyświetlone to ostrzeżenie podczas kompilowania ze środowiska programistycznego i nie ma pewności, gdzie są dostępne opcje powodujące konflikt, należy wziąć pod uwagę następujące kwestie:

- Opcję można określić w kodzie lub w ustawieniach projektu projektu. Jeśli widzisz [strony właściwości wiersza polecenia](../../build/reference/command-line-property-pages.md) kompilatora i jeśli w polu **wszystkie opcje** zostaną wyświetlone opcje powodujące konflikt, opcje są ustawiane na stronach właściwości projektu, w przeciwnym razie opcje są ustawiane w kodzie źródłowym.

   Jeśli opcje są ustawione na stronach właściwości projektu, należy poszukać na stronie właściwości preprocesora kompilatora (z węzłem projektu wybranym w Eksplorator rozwiązań).  Jeśli ta opcja nie jest widoczna, sprawdź ustawienia strony właściwości preprocesora dla każdego pliku kodu źródłowego (w Eksplorator rozwiązań), aby upewnić się, że nie został on dodany.

   Jeśli opcje są ustawione w kodzie, można ustawić je w kodzie lub w nagłówkach systemu Windows.  Możesz spróbować utworzyć wstępnie przetworzony plik ([/p](../../build/reference/p-preprocess-to-a-file.md)) i wyszukać go dla symbolu.
