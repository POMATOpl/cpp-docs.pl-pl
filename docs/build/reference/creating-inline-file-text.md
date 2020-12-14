---
description: 'Dowiedz się więcej na temat: Tworzenie tekstu pliku wbudowanego'
title: Tworzenie tekstu pliku wbudowanego
ms.date: 11/04/2016
helpviewer_keywords:
- inline files, creating text
- NMAKE program, inline files
- text, inline file
ms.assetid: b8a332ed-8244-4ff8-89e6-029d7f659725
ms.openlocfilehash: 849273fff4ca0853e4589a38096cbb067c380aae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97196857"
---
# <a name="creating-inline-file-text"></a>Tworzenie tekstu pliku wbudowanego

Pliki śródwierszowe są tymczasowe lub trwałe.

## <a name="syntax"></a>Składnia

```
inlinetext
.
.
.
<<[KEEP | NOKEEP]
```

## <a name="remarks"></a>Uwagi

Określ *inlinetext* w pierwszym wierszu po poleceniu. Oznacz koniec z podwójnymi nawiasami ostrymi (<<) na początku oddzielnego wiersza. Plik zawiera wszystkie *inlinetext* przed nawiasem ograniczającym. *Inlinetext* może mieć rozwinięcia makra i podstawienia, ale nie dyrektywy ani Komentarze pliku reguł programu make. Spacje, tabulatory i znaki nowego wiersza są traktowane jako dosłownie.

Plik tymczasowy istnieje na czas trwania sesji i może być ponownie używany przez inne polecenia. Po nawiasie zamykającym należy określić wartość **Zachowaj** , aby zachować plik po sesji NMAKE; plik bez nazwy jest zachowywany na dysku z wygenerowaną nazwą pliku. Określ wartość **nokeep** lub Nothing dla pliku tymczasowego. **Zachowaj** i nie **zachowuj** wielkości liter.

## <a name="see-also"></a>Zobacz też

[Pliki wbudowane w pliku reguł programu make](inline-files-in-a-makefile.md)
