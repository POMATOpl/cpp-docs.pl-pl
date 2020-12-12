---
description: 'Dowiedz się więcej na temat: importidl'
title: importidl (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.importidl
helpviewer_keywords:
- importidl attribute
ms.assetid: 4b0a4b55-6c57-4e6e-bc7b-a12cc8063941
ms.openlocfilehash: b10caa9f4b1467727c70b6d968ca6aa33b58da0c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329879"
---
# <a name="importidl"></a>importidl

Wstawia określony plik IDL do wygenerowanego pliku IDL.

## <a name="syntax"></a>Składnia

```cpp
[ importidl(idl_file) ];
```

### <a name="parameters"></a>Parametry

*idl_file*<br/>
Określa nazwę pliku. idl, który ma zostać scalony z plikiem. idl, który zostanie wygenerowany dla aplikacji.

## <a name="remarks"></a>Uwagi

Atrybut **importidl** C++ umieszcza sekcję poza blokiem biblioteki (w *idl_file*) w wygenerowanym przez program pliku IDL i sekcji biblioteki (w *idl_file*) do sekcji Biblioteka wygenerowanego pliku. idl programu.

Możesz użyć **importidl**, na przykład, jeśli chcesz użyć ręcznie zakodowanego pliku. idl z wygenerowanym plikiem. idl.

## <a name="example"></a>Przykład

```cpp
// cpp_attr_ref_importidl.cpp
// compile with: /LD
[module(name="MyLib")];
[importidl("import.idl")];
```

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
[Atrybuty autonomiczne](stand-alone-attributes.md)<br/>
[zaimportować](import.md)<br/>
[importlib](importlib.md)<br/>
[być](include-cpp.md)<br/>
[includelib —](includelib-cpp.md)
