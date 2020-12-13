---
description: 'Dowiedz się więcej na temat: make_public pragma'
title: make_public, pragma
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.make_public
- make_public_CPP
helpviewer_keywords:
- pragmas, make_public
- make_public pragma
ms.assetid: c3665f4d-268a-4932-9661-c37c8ae6a341
ms.openlocfilehash: 327a9882e13f9c51182e0673443566b56177d320
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333406"
---
# <a name="make_public-pragma"></a>make_public, pragma

Wskazuje, że typ natywny powinien mieć dostępność zestawu publicznego.

## <a name="syntax"></a>Składnia

> **make_public #pragma (** *Typ* **)**

### <a name="parameters"></a>Parametry

*Wprowadź*\
Nazwa typu, który ma mieć dostęp do zestawu publicznego.

## <a name="remarks"></a>Uwagi

**make_public** jest przydatne w przypadku, gdy natywny typ, do którego chcesz się odwołać pochodzi z pliku nagłówkowego, którego nie można zmienić. Jeśli chcesz użyć typu natywnego w podpisie funkcji publicznej w typie z widocznością zestawu publicznego, typ natywny musi mieć również dostęp do zestawu publicznego lub kompilator wyda ostrzeżenie.

należy określić **make_public** w zakresie globalnym. Działa tylko od punktu, w którym jest zadeklarowany na końcu pliku kodu źródłowego.

Typ natywny może być niejawnie lub jawnie prywatny. Aby uzyskać więcej informacji, zobacz [typu widoczność](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility).

## <a name="examples"></a>Przykłady

Poniższy przykład to zawartość pliku nagłówkowego, który zawiera definicje dwóch natywnych struktur.

```cpp
// make_public_pragma.h
struct Native_Struct_1 { int i; };
struct Native_Struct_2 { int i; };
```

Poniższy przykład kodu zużywa plik nagłówkowy. Pokazuje, że, chyba że jawnie oznaczy natywne struktury jako publiczne przy użyciu **make_public**, kompilator generuje ostrzeżenie przy próbie użycia natywnych struktur w sygnaturze funkcji publicznej w publicznym typie zarządzanym.

```cpp
// make_public_pragma.cpp
// compile with: /c /clr /W1
#pragma warning (default : 4692)
#include "make_public_pragma.h"
#pragma make_public(Native_Struct_1)

public ref struct A {
   void Test(Native_Struct_1 u) {u.i = 0;}   // OK
   void Test(Native_Struct_2 u) {u.i = 0;}   // C4692
};
```

## <a name="see-also"></a>Zobacz też

[Dyrektywy pragma i słowo kluczowe __pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
