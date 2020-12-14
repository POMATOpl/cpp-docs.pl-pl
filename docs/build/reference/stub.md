---
description: 'Dowiedz się więcej na temat: STUB'
title: STUB
ms.date: 11/04/2016
f1_keywords:
- STUB
helpviewer_keywords:
- STUB .def file statement
ms.assetid: 0a3b9643-19ed-47e9-8173-ee16bc8ed056
ms.openlocfilehash: 79a2002c119bf211652e2aab51d9656b36e3d159
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230292"
---
# <a name="stub"></a>STUB

W przypadku użycia w pliku definicji modułu, który kompiluje sterownik urządzenia wirtualnego (VxD), umożliwia określenie nazwy pliku, która zawiera strukturę IMAGE_DOS_HEADER (zdefiniowaną w programie WINNT. H), która ma być używana w sterowniku urządzenia wirtualnego (VxD), a nie w domyślnym nagłówku.

```
STUB:filename
```

## <a name="remarks"></a>Uwagi

Odpowiednikiem metody określania *nazwy pliku* jest [/stub](stub-ms-dos-stub-file-name.md) opcja konsolidatora.

Element ZASTĘPCZy jest prawidłowy w pliku definicji modułu tylko w przypadku kompilowania sterownika VxD.

## <a name="see-also"></a>Zobacz też

[Reguły dla instrukcji Module-Definition](rules-for-module-definition-statements.md)
