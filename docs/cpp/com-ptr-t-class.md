---
description: Dowiedz się więcej na temat klasy _com_ptr_t
title: _com_ptr_t — Klasa
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t
helpviewer_keywords:
- _com_ptr_t class
ms.assetid: 3753a8a0-03d4-4cfd-8a9a-74872ea53971
ms.openlocfilehash: a68b522806cec14baffe7857c71ac171ed0407f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295617"
---
# <a name="_com_ptr_t-class"></a>_com_ptr_t — Klasa

**Specyficzne dla firmy Microsoft**

Obiekt **_com_ptr_t** hermetyzuje wskaźnik interfejsu com i jest nazywany wskaźnikiem "inteligentny". Ta klasa szablonu zarządza alokacją zasobów i dealokacją przez wywołania funkcji do `IUnknown` funkcji składowych: `QueryInterface` , `AddRef` , i `Release` .

Inteligentny wskaźnik zazwyczaj odwołuje się do definicji typedef dostarczonej przez makro _COM_SMARTPTR_TYPEDEF. To makro przyjmuje nazwę interfejsu i identyfikator IID i deklaruje specjalizację **_com_ptr_t** z nazwą interfejsu oraz sufiksem `Ptr` . Na przykład:

```cpp
_COM_SMARTPTR_TYPEDEF(IMyInterface, __uuidof(IMyInterface));
```

deklaruje  specjalizację _com_ptr_t `IMyInterfacePtr` .

Zestaw [szablonów funkcji](../cpp/relational-function-templates.md), nie należących do tej klasy szablonu, obsługują porównania z inteligentnym wskaźnikiem po prawej stronie operatora porównania.

### <a name="construction"></a>Budownictwo

| Nazwa | Opis |
|-|-|
|[_com_ptr_t](../cpp/com-ptr-t-com-ptr-t.md)|Konstruuje obiekt **_com_ptr_t** .|

### <a name="low-level-operations"></a>Operacje Low-Level

| Nazwa | Opis |
|-|-|
|[AddRef](../cpp/com-ptr-t-addref.md)|Wywołuje `AddRef` funkcję elementu członkowskiego `IUnknown` na wyhermetyzowanym wskaźniku interfejsu.|
|[Dołącz](../cpp/com-ptr-t-attach.md)|Hermetyzuje pierwotny wskaźnik interfejsu tego typu inteligentnego wskaźnika.|
|[CreateInstance](../cpp/com-ptr-t-createinstance.md)|Tworzy nowe wystąpienie obiektu z `CLSID` lub `ProgID` .|
|[Odłącz](../cpp/com-ptr-t-detach.md)|Wyodrębnia i zwraca wskaźnik interfejsu hermetyzowanego.|
|[GetActiveObject](../cpp/com-ptr-t-getactiveobject.md)|Dołącza do istniejącego wystąpienia obiektu danego a `CLSID` lub `ProgID` .|
|[GetInterfacePtr](../cpp/com-ptr-t-getinterfaceptr.md)|Zwraca wskaźnik interfejsu hermetyzowanego.|
|[QueryInterface](../cpp/com-ptr-t-queryinterface.md)|Wywołuje `QueryInterface` funkcję elementu członkowskiego `IUnknown` na wyhermetyzowanym wskaźniku interfejsu.|
|[Wersja](../cpp/com-ptr-t-release.md)|Wywołuje `Release` funkcję elementu członkowskiego `IUnknown` na wyhermetyzowanym wskaźniku interfejsu.|

### <a name="operators"></a>Operatory

| Nazwa | Opis |
|-|-|
|[operator =](../cpp/com-ptr-t-operator-equal.md)|Przypisuje nową wartość do istniejącego obiektu **_com_ptr_t** .|
|[Operatory = =,! =, \<, > , \<=, >=](../cpp/com-ptr-t-relational-operators.md)|Porównaj obiekt inteligentnego wskaźnika z innym wskaźnikiem inteligentnym, nieprzetworzonym wskaźnikiem interfejsu lub wartością NULL.|
|[Ekstraktory](../cpp/com-ptr-t-extractors.md)|Wyodrębnij zhermetyzowany wskaźnik interfejsu COM.|

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<comip.h>

**Lib:** comsuppw. lib lub comsuppwd. lib (patrz [/Zc: Wchar_t (Wchar_t jest typem natywnym)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) , aby uzyskać więcej informacji.

## <a name="see-also"></a>Zobacz też

[Klasy obsługi kompilatora COM](../cpp/compiler-com-support-classes.md)
