---
description: 'Dowiedz się więcej o: serializacji (C++/CLI)'
title: Serializacja (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- serialization [C++]
- SerializableAttribute class, managed applications
- NonSerializedAttribute class, managed applications
- managed code [C++], serializing
- .NET Framework [C++], serialization
- serialization [C++], about serialization
ms.assetid: 869010ca-74e1-4989-b409-4643cdb94084
ms.openlocfilehash: 1524ed5d4a000d2006f6f830b1d82119d170c3b2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164604"
---
# <a name="serialization-ccli"></a>Serializacja (C++/CLI)

Serializacja (proces przechowywania stanu obiektu lub elementu członkowskiego na stałe medium) zarządzanych klas (w tym poszczególnych pól lub właściwości) jest obsługiwana przez <xref:System.SerializableAttribute> <xref:System.NonSerializedAttribute> klasy i.

## <a name="remarks"></a>Uwagi

Zastosuj atrybut niestandardowy **SerializableAttribute** do zarządzanej klasy, aby serializować całą klasę lub zastosować tylko do określonych pól lub właściwości do serializacji części klasy zarządzanej. Użyj **Nieserializowanego** atrybutu niestandardowegoattribute do wykluczenia pól lub właściwości klasy zarządzanej z serializowania.

## <a name="example"></a>Przykład

### <a name="description"></a>Opis

W poniższym przykładzie Klasa `MyClass` (i Właściwość `m_nCount` ) są oznaczone jako możliwe do serializacji. Jednak `m_nData` Właściwość nie jest serializowana zgodnie ze wskazanym **nieserializowanym** atrybutem niestandardowym:

### <a name="code"></a>Kod

```cpp
// serialization_and_mcpp.cpp
// compile with: /LD /clr
using namespace System;

[ Serializable ]
public ref class MyClass {
public:
   int m_nCount;
private:
   [ NonSerialized ]
   int m_nData;
};
```

### <a name="comments"></a>Komentarze

Należy pamiętać, że obydwa atrybuty mogą być przywoływane przy użyciu "krótkiej nazwy" (**serializować** i **nieszeregowane**). Jest to dokładniej wyjaśnione w temacie [stosowanie atrybutów](/dotnet/standard/attributes/applying-attributes).

## <a name="see-also"></a>Zobacz też

[Programowanie .NET w języku C++/interfejsie wiersza polecenia (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
