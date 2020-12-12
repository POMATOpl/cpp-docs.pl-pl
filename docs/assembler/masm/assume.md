---
description: 'Dowiedz się więcej o: przyjmij'
title: ASSUME
ms.date: 11/05/2019
f1_keywords:
- ASSUME
helpviewer_keywords:
- ASSUME directive
ms.assetid: cd162070-aee9-4c65-babc-005c6cc73d7c
ms.openlocfilehash: b597e50dafe07950d87cb04cf5e697b63c55611c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97121748"
---
# <a name="assume"></a>ASSUME

Włącza sprawdzanie błędów dla wartości rejestru. (tylko 32-bitowy MASM).

## <a name="syntax"></a>Składnia

> **Przyjmij**  *segregister*__:__*name* ⟦__,__ *segregister*__:__*name*... ⟧\
> **Przyjmij**  *Rejestr*__danych:__*wpisz* ⟦__,__ *dataregister*__:__*Type*... ⟧\
> **Przyjmij**  *Rejestr*__: błąd__ ⟦__,__ *register*__: błąd__... ⟧\
> **Załóżmy, że**  ⟦*register*__:__⟧**Nothing** ⟦__,__ *register*__: Nothing__... ⟧

## <a name="remarks"></a>Uwagi

Po **założeniu** , że program asembler obserwuje zmiany wartości danego rejestru. **Błąd** powoduje wygenerowanie błędu, jeśli rejestr jest używany. **Nic nie** usuwa sprawdzania błędów rejestru. Można połączyć różne rodzaje założeń w jednej instrukcji.

## <a name="see-also"></a>Zobacz też

[Dokumentacja dyrektyw](directives-reference.md)\
[MASM BNF, gramatyka](masm-bnf-grammar.md)
