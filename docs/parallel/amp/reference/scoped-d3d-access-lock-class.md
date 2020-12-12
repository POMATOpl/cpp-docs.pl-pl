---
description: Dowiedz się więcej na temat klasy scoped_d3d_access_lock
title: scoped_d3d_access_lock — Klasa
ms.date: 11/04/2016
f1_keywords:
- scoped_d3d_access_lock
- AMPRT/scoped_d3d_access_lock
- AMPRT/concurrency::direct3d::scoped_d3d_access_lock::scoped_d3d_access_lock
ms.assetid: 0ad333e6-9839-4736-a722-16d95d70c4b1
ms.openlocfilehash: 1106673ba9ca095b33660f6a713a40ae8498d384
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329904"
---
# <a name="scoped_d3d_access_lock-class"></a>scoped_d3d_access_lock — Klasa

Otoka RAII na blokadę dostępu D3D na obiekcie accelerator_view.

## <a name="syntax"></a>Składnia

```cpp
class scoped_d3d_access_lock;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[Konstruktor scoped_d3d_access_lock](#ctor)|Przeciążone. Konstruuje `scoped_d3d_access_lock` obiekt. Blokada jest wydana, gdy ten obiekt wykracza poza zakres.|
|[~ scoped_d3d_access_lock destruktor](#dtor)|Zwalnia blokadę dostępu D3D dla skojarzonego `accelerator_view` obiektu.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[operator =](#operator_eq)|Przejmuje na własność blokadę z innego `scoped_d3d_access_lock` .|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`scoped_d3d_access_lock`

## <a name="requirements"></a>Wymagania

**Nagłówek:** amprt. h

**Przestrzeń nazw:** concurrency::d irect3d

## <a name="scoped_d3d_access_lock"></a><a name="ctor"></a> scoped_d3d_access_lock

Konstruuje `scoped_d3d_access_lock` obiekt. Blokada jest wydana, gdy ten obiekt wykracza poza zakres.

```cpp
explicit scoped_d3d_access_lock(// [1] constructor
    accelerator_view& _Av);

explicit scoped_d3d_access_lock(// [2] constructor
    accelerator_view& _Av,
    adopt_d3d_access_lock_t _T);

scoped_d3d_access_lock(// [3] move constructor
    scoped_d3d_access_lock&& _Other);
```

### <a name="parameters"></a>Parametry

*_Av*<br/>
`accelerator_view`Dla blokady do przyjęcia.

*_T*<br/>
Obiekt `adopt_d3d_access_lock_t`.

*_Other*<br/>
`scoped_d3d_access_lock`Obiekt, z którego ma zostać przeniesiona istniejąca blokada.

## <a name="construction"></a>Budownictwo

[1] Konstruktor uzyskuje blokadę dostępu D3D dla danego obiektu [accelerator_view](accelerator-view-class.md) . Bloki konstrukcyjne do momentu uzyskania blokady.

[2] Konstruktor przyjmuje blokadę dostępu D3D z danego obiektu [accelerator_view](accelerator-view-class.md) .

[3] Konstruktor przenoszenia pobiera istniejącą blokadę dostępu D3D z innego `scoped_d3d_access_lock` obiektu. Konstrukcja nie jest blokowana.

## <a name="scoped_d3d_access_lock"></a><a name="dtor"></a> ~ scoped_d3d_access_lock

Zwalnia blokadę dostępu D3D dla skojarzonego `accelerator_view` obiektu.

```cpp
~scoped_d3d_access_lock();
```

## <a name="operator"></a><a name="operator_eq"></a> operator =

Przejmuje na własność blokadę dostępu D3D z innego `scoped_d3d_access_lock` obiektu, zwalniając poprzednią blokadę.

```cpp
scoped_d3d_access_lock& operator= (scoped_d3d_access_lock&& _Other);
```

### <a name="parameters"></a>Parametry

*_Other*<br/>
Accelerator_view, z którego ma zostać przeniesiona blokada dostępu D3D.

### <a name="return-value"></a>Wartość zwracana

Odwołanie do tego `scoped_accelerator_view_lock` .

## <a name="see-also"></a>Zobacz też

[Concurrency::direct3d — Przestrzeń nazw](concurrency-direct3d-namespace.md)
