---
description: 'Dowiedz się więcej: formatowanie danych wyjściowych niestandardowego kroku kompilacji lub zdarzenia kompilacji'
title: Formatowanie danych wyjściowych niestandardowego kroku budowania lub zdarzenia kompilacji
ms.date: 08/27/2018
helpviewer_keywords:
- builds [C++], build events
- custom build steps [C++], output format
- events [C++], build
- build events [C++], output format
- build steps [C++], output format
- builds [C++], custom build steps
ms.assetid: 92ad3e38-24d7-4b89-90e6-5a16f5f998da
ms.openlocfilehash: c2631e3c6cbd8e66d88527ff75ff7bcac9869b4f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97156427"
---
# <a name="formatting-the-output-of-a-custom-build-step-or-build-event"></a>Formatowanie danych wyjściowych niestandardowego kroku budowania lub zdarzenia kompilacji

Jeśli dane wyjściowe niestandardowego kroku kompilacji lub zdarzenia kompilacji są sformatowane prawidłowo, użytkownicy uzyskują następujące korzyści:

- Ostrzeżenia i błędy są zliczane w oknie **danych wyjściowych** .

- Dane wyjściowe są wyświetlane w oknie **Lista zadań** .

- Kliknięcie danych wyjściowych w oknie **danych wyjściowych** spowoduje wyświetlenie odpowiedniego tematu.

- Operacje F1 są włączane w oknie **Lista zadań** lub w oknie **danych wyjściowych** .

Format danych wyjściowych powinien być:

> {<em>filename</em>**(**<em>wiersz #</em> \[ **,** <em>kolumna #</em>]**)** &#124; *ToolName*} **:** \[ <em>dowolny tekst</em> ] {**error** &#124; **Warning**} <em>kod + numer</em>**:**<em>Lokalizowalny ciąg</em> \[ <em>dowolny tekst</em> ]

Gdzie:

- {*a* &#124; *b*} to wybór *a* lub *b*.

- \[<em>element</em>] jest opcjonalnym ciągiem lub parametrem.

- **Pogrubienie** reprezentuje literał.

Na przykład:

> C: \\ *SourceFile. cpp*(134): błąd C2143: błąd składniowy: Brak znaku ";" przed "}"
>
> LINK: błąd krytyczny LNK1104: nie można otworzyć pliku "*somelib. lib*"

## <a name="see-also"></a>Zobacz też

[Ogólne informacje o niestandardowych krokach budowania lub zdarzeniach kompilacji](understanding-custom-build-steps-and-build-events.md)
