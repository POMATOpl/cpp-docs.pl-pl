---
description: Dowiedz się więcej na temat:/INTEGRITYCHECK
title: /INTEGRITYCHECK
ms.date: 12/28/2017
f1_keywords:
- /INTEGRITYCHECK
helpviewer_keywords:
- -INTEGRITYCHECK editbin options
- /INTEGRITYCHECK editbin options
- INTEGRITYCHECK editbin options
ms.openlocfilehash: b1ea8275bdb356febcf18a2a55b6ab718d8eea96
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199665"
---
# <a name="integritycheck"></a>/INTEGRITYCHECK

Określa, że podpis cyfrowy obrazu binarnego musi być sprawdzany w czasie ładowania.

> **/INTEGRITYCHECK**[**: No**]

## <a name="remarks"></a>Uwagi

W nagłówku pliku DLL lub pliku wykonywalnego ta opcja ustawia flagę, która wymaga sprawdzenia podpisu cyfrowego przez Menedżera pamięci do załadowania obrazu w systemie Windows. W wersjach systemu Windows starszych niż Windows Vista zignoruj tę flagę. Ta opcja musi być ustawiona dla 64-bitowych bibliotek DLL, które implementują kod trybu jądra, i jest zalecana dla wszystkich sterowników urządzeń. Aby uzyskać więcej informacji, zobacz [wymagania dotyczące podpisywania kodu w trybie jądra](/windows-hardware/drivers/install/kernel-mode-code-signing-requirements--windows-vista-and-later-).

## <a name="see-also"></a>Zobacz też

[Opcje polecenia EDITBIN](editbin-options.md)
