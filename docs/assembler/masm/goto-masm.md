---
title: GOTO (MASM)
ms.date: 08/30/2018
f1_keywords:
- goto
helpviewer_keywords:
- GOTO directive
ms.assetid: 6a5f73e7-6784-4eae-ac52-4fc77a7f369f
ms.openlocfilehash: a03cbda5a8ff64f6c167766f416e7744a5382ad5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62203088"
---
# <a name="goto-masm"></a>GOTO (MASM)

Przenosi zaznaczony wiersz zestawu **:**_macrolabel_.

## <a name="syntax"></a>Składnia

> **GOTO** *macrolabel*

## <a name="remarks"></a>Uwagi

**Przejdź do** jest dozwolona tylko wewnątrz [— makro](macro.md), [dla](for-masm.md), [FORC](forc.md), [Powtórz](repeat.md), i [podczas](while-masm.md)bloków. *Macrolabel* docelowy musi być jedynym dyrektywy w wierszu i musi być poprzedzony przez wiodących średnikami.

## <a name="see-also"></a>Zobacz także

[Dokumentacja dyrektyw](../../assembler/masm/directives-reference.md)<br/>
