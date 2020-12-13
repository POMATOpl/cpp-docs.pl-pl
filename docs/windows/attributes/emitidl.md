---
description: 'Dowiedz się więcej na temat: emitidl'
title: emitidl (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.emitidl
helpviewer_keywords:
- emitidl attribute
ms.assetid: 85b80c56-578e-4392-ac03-8443c74ebb7d
ms.openlocfilehash: 21c4f7fc067eb37b8816bdedd1f338908950566e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337799"
---
# <a name="emitidl"></a>emitidl

Określa, czy wszystkie kolejne atrybuty IDL są przetwarzane i umieszczane w wygenerowanym pliku IDL.

## <a name="syntax"></a>Składnia

```cpp
[ emitidl(state, defaultimports=boolean) ];
```

### <a name="parameters"></a>Parametry

*Państwu*<br/>
Jedna z tych możliwych wartości: **`true`** , **`false`** ,,, `forced` `restricted` `push` lub `pop` .

- Jeśli **`true`** atrybuty kategorii IDL napotkane w pliku kodu źródłowego są umieszczane w wygenerowanym pliku IDL. Jest to ustawienie domyślne dla **emitidl**.

- Jeśli **`false`** atrybuty kategorii IDL napotkane w pliku kodu źródłowego nie zostaną umieszczone w wygenerowanym pliku IDL.

- Jeśli `restricted` , zezwala, aby atrybuty IDL znajdować się w pliku bez atrybutu [modułu](module-cpp.md) . Kompilator nie generuje pliku IDL.

- Jeśli `forced` , zastępuje następny `restricted` atrybut, który wymaga, aby plik miał atrybut, `module` Jeśli w pliku istnieją atrybuty IDL.

- `push` umożliwia zapisanie bieżących ustawień **emitidl** w wewnętrznym stosie **emitidl** i `pop` pozwala ustawić **emitidl** dla każdej wartości w górnej części wewnętrznego stosu **emitidl** .

`defaultimports=`*wartość logiczna* \( obowiązkowe

- Jeśli *wartość logiczna* to **`true`** , docobj. idl zostanie zaimportowany do wygenerowanego pliku IDL. Ponadto, jeśli plik. idl o takiej samej nazwie jak plik. h, który znajduje się w `#include` kodzie źródłowym, znajduje się w tym samym katalogu, co plik. h, wygenerowany plik. idl zawiera instrukcję import dla tego pliku IDL.

- Jeśli *wartość logiczna* to **`false`** , docobj. idl nie jest zaimportowana do wygenerowanego pliku IDL. Należy jawnie zaimportować pliki. idl przy użyciu [importu](import.md).

## <a name="remarks"></a>Uwagi

Po napotkaniu atrybutu **emitidl** C++ w pliku z kodem źródłowym atrybuty kategorii IDL są umieszczane w wygenerowanym pliku IDL. Jeśli nie istnieje atrybut **emitidl** , atrybuty IDL w pliku kodu źródłowego są wyprowadzane do wygenerowanego pliku IDL.

W pliku kodu źródłowego można mieć wiele atrybutów **emitidl** . Jeśli `[emitidl(false)];` program zostanie napotkany w pliku bez kolejnych `[emitidl(true)];` , wówczas żadne atrybuty nie są przetwarzane do wygenerowanego pliku IDL.

Za każdym razem, gdy kompilator napotyka nowy plik, **emitidl** jest niejawnie ustawiony na **`true`** .

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|Dowolne miejsce|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|Brak|
|**Nieprawidłowe atrybuty**|Brak|

Aby uzyskać więcej informacji, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty kompilatora](compiler-attributes.md)<br/>
[Atrybuty autonomiczne](stand-alone-attributes.md)
