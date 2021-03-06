---
description: Dowiedz się więcej na temat:. FPO (32-bitowy MASM)
title: .FPO
ms.date: 11/05/2019
f1_keywords:
- .FPO
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
ms.openlocfilehash: 058189329cbe849086a3b1540ac7883ecac4d026
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97131706"
---
# <a name="fpo-32-bit-masm"></a>. FPO (32-bitowy MASM)

**. Dyrektywa FPO** steruje emisją rekordów debugowania do segmentu lub sekcji. Debug $ F. (tylko 32-bitowy MASM).

## <a name="syntax"></a>Składnia

> **. FPO** (*cdwLocals*, *cdwParams*, *cbProlog*, *cbRegs*, *fUseBP*, *cbFrame*)

### <a name="parameters"></a>Parametry

*cdwLocals*\
Liczba zmiennych lokalnych, nieniepodpisana wartość bitowa 32.

*cdwParams*\
Rozmiar parametrów w elementach DWORD, wartość 16-bitowa bez znaku.

*cbProlog*\
Liczba bajtów w kodzie prologu funkcji, 8-bitowej wartości bez znaku.

*cbRegs*\
Zapisano numery rejestrów.

*fUseBP*\
Wskazuje, czy rejestr EBP został przydzielony. wartość 0 lub 1.

*cbFrame*\
Wskazuje typ ramki.  Aby uzyskać więcej informacji, zobacz [FPO_DATA](/windows/win32/api/winnt/ns-winnt-fpo_data) .

## <a name="see-also"></a>Zobacz też

[Dokumentacja dyrektyw](directives-reference.md)\
[MASM BNF, gramatyka](masm-bnf-grammar.md)
