---
title: 'Porady: deklarowanie i użycie wewnętrznych wskaźników i zarządzanych tablic (C + +/ CLI) | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 10/12/2018
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- pointers, interior
- arrays [C++], managed
ms.assetid: e61a2c09-a7d0-4867-91ea-6b8788a01079
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a18170d66ef2b2fe374085557d7fca4411c48ec6
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/25/2018
ms.locfileid: "50080627"
---
# <a name="how-to-declare-and-use-interior-pointers-and-managed-arrays-ccli"></a>Poradnik: Deklarowanie wewnętrznych wskaźników i zarządzanych tablic oraz posługiwanie się nimi (C++/CLI)

Następujące C + +/ CLI przykład pokazuje, jak zadeklarować i użyj wnętrza wskaźnika do tablicy.

> [!IMPORTANT]
> Tej funkcji języka jest obsługiwana przez `/clr` — opcja kompilatora, ale nie za `/ZW` — opcja kompilatora.

## <a name="example"></a>Przykład

### <a name="code"></a>Kod

```cpp
// interior_ptr_arrays.cpp
// compile with: /clr
#define SIZE 10

int main() {
   // declare the array
   array<int>^ arr = gcnew array<int>(SIZE);

   // initialize the array
   for (int i = 0 ; i < SIZE ; i++)
      arr[i] = i + 1;

   // create an interior pointer into the array
   interior_ptr<int> ipi = &arr[0];

   System::Console::WriteLine("1st element in arr holds: {0}", arr[0]);
   System::Console::WriteLine("ipi points to memory address whose value is: {0}", *ipi);

   ipi++;
   System::Console::WriteLine("after incrementing ipi, it points to memory address whose value is: {0}", *ipi);
}
```

```Output
1st element in arr holds: 1
ipi points to memory address whose value is: 1
after incrementing ipi, it points to memory address whose value is: 2
```

## <a name="see-also"></a>Zobacz też

[interior_ptr (C++/CLI)](../windows/interior-ptr-cpp-cli.md)