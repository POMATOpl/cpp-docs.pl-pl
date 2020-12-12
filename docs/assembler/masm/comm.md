---
description: 'Dowiedz się więcej o: komunikacji'
title: COMM
ms.date: 12/06/2019
f1_keywords:
- COMM
helpviewer_keywords:
- COMM directive
ms.assetid: a23548c4-ad04-41fa-91da-945f228de742
ms.openlocfilehash: dc8a9ed97d55b4b6e45cb8057f46885536ba0b2f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97120955"
---
# <a name="comm"></a>COMM

Tworzy zmienną gminną z atrybutami określonymi w *definicji*.

## <a name="syntax"></a>Składnia

>  ⟦ *Definicji* komunikacji __,__ *Definicja* ... ⟧

## <a name="remarks"></a>Uwagi

Zmienne gminne są przydzielone przez konsolidator i nie mogą być inicjowane. Oznacza to, że nie można zależeć od lokalizacji lub sekwencji takich zmiennych.

Każda *Definicja* ma następującą postać:

⟦*Language-Type*⟧ ⟦**blisko**  |  ⟧ _etykieta_**:**_Type_⟦**:**_Count_⟧

Argumenty *typu Language*, **Near** i **daleko** są prawidłowe tylko w 32-bitowym MASM.

Opcjonalny *Typ języka* ustawia konwencje nazewnictwa dla następującej nazwy. Zastępuje dowolny język określony przez **. Dyrektywa modelu** . Opcjonalna, **zbliżona** lub **znacznie** zastąp bieżący model pamięci. *Etykieta* to nazwa zmiennej. *Typ* może być dowolnym specyfikatorem typu ([Byte](byte-masm.md), [Word](word.md)itd.) lub liczbą całkowitą określającą liczbę bajtów. Opcjonalna *Liczba* określa liczbę elementów w zadeklarowanym obiekcie danych. Domyślna *Liczba* to 1.

## <a name="example"></a>Przykład

Ten przykład tworzy tablicę elementów bajtów 512:

```asm
COMM FAR ByteArray:BYTE:512
```

## <a name="see-also"></a>Zobacz też

[Dokumentacja dyrektyw](directives-reference.md)\
[MASM BNF, gramatyka](masm-bnf-grammar.md)
