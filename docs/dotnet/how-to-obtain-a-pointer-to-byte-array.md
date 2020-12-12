---
description: 'Dowiedz się więcej o: Instrukcje: uzyskiwanie wskaźnika do tablicy bajtów'
title: 'Porady: uzyskiwanie wskaźnika do tablicy typu Byte'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- pointers, to Byte array
- Byte arrays
ms.assetid: aea18073-3341-47f4-9f0e-04e03327037e
ms.openlocfilehash: d76aa9040be5b908edac3a87ae6f0698f6d6a5dc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286387"
---
# <a name="how-to-obtain-a-pointer-to-byte-array"></a>Porady: uzyskiwanie wskaźnika do tablicy typu Byte

Możesz uzyskać wskaźnik do bloku Array w <xref:System.Byte> tablicy, pobierając adres pierwszego elementu i przypisując go do wskaźnika.

## <a name="example"></a>Przykład

```cpp
// pointer_to_Byte_array.cpp
// compile with: /clr
using namespace System;
int main() {
   Byte bArr[] = {1, 2, 3};
   Byte* pbArr = &bArr[0];

   array<Byte> ^ bArr2 = gcnew array<Byte>{1,2,3};
   interior_ptr<Byte> pbArr2 = &bArr2[0];
}
```

## <a name="see-also"></a>Zobacz także

[Korzystanie z międzyoperacyjności języka C++ (niejawne PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
