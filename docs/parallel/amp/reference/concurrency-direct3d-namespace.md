---
description: 'Dowiedz się więcej na temat: concurrency::d irect3d Namespace'
title: Concurrency::direct3d — Przestrzeń nazw
ms.date: 11/04/2016
f1_keywords:
- amp/Concurrency::direct3d
- amprt/Concurrency::direct3d
- amp_short_vectors/Concurrency::direct3d
- amp_graphics/Concurrency::direct3d
- amp_math/Concurrency::direct3d
helpviewer_keywords:
- direct3d namespace
ms.assetid: 9566a2f1-4d5f-43e4-a3ac-676643d38420
ms.openlocfilehash: 9fb0e7d4f5abbccbd9cd931fe2c4520e9410cbc9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247738"
---
# <a name="concurrencydirect3d-namespace"></a>Concurrency::direct3d — Przestrzeń nazw

`direct3d`Przestrzeń nazw zawiera funkcje, które obsługują współdziałanie D3D. Umożliwia korzystanie z zasobów D3D do obliczeń w kodzie AMP. Umożliwia również korzystanie z zasobów utworzonych w AMP w kodzie D3D bez tworzenia nadmiarowych kopii pośrednich. Można stopniowo przyspieszyć obszary obliczeniowe w aplikacjach DirectX za pomocą C++ AMP i korzystać z interfejsu API D3D na danych wyprodukowanych z obliczeń AMP.

## <a name="syntax"></a>Składnia

```cpp
namespace direct3d;
```

## <a name="members"></a>Elementy członkowskie

### <a name="classes"></a>Klasy

|Nazwa|Opis|
|----------|-----------------|
|[Klasa scoped_d3d_access_lock](scoped-d3d-access-lock-class.md)|Otoka RAII dla blokady dostępu D3D na `accelerator_view` obiekcie.|

### <a name="structures"></a>Struktury

|Nazwa|Opis|
|----------|-----------------|
|[adopt_d3d_access_lock_t — Struktura](adopt-d3d-access-lock-t-structure.md)|Typ tagu wskazujący, że blokada dostępu D3D powinna zostać przyjęta, a nie pobrana.|

### <a name="functions"></a>Funkcje

|Nazwa|Opis|
|----------|-----------------|
|[ABS](concurrency-direct3d-namespace-functions-amp.md#abs)|Zwraca wartość bezwzględną argumentu.|
|[opraw](concurrency-direct3d-namespace-functions-amp.md#clamp)|Przeciążone. Ogranicza _X do określonego _Min i zakresu _Max|
|[countbits —](concurrency-direct3d-namespace-functions-amp.md#countbits)|Zlicza liczbę bitów zestawu w _X|
|[create_accelerator_view](concurrency-direct3d-namespace-functions-amp.md#create_accelerator_view)|Tworzy [klasę accelerator_view](accelerator-view-class.md) ze wskaźnika do interfejsu urządzenia Direct3D|
|[d3d_access_lock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_lock)|Uzyskuje blokadę accelerator_view do bezpiecznego wykonywania operacji D3D na zasobach współużytkowanych z accelerator_view|
|[d3d_access_try_lock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_try_lock)|Spróbuj uzyskać blokadę dostępu D3D na accelerator_view bez blokowania.|
|[d3d_access_unlock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_unlock)|Zwolnij blokadę dostępu D3D dla danego accelerator_view.|
|[firstbithigh —](concurrency-direct3d-namespace-functions-amp.md#firstbithigh)|Pobiera lokalizację pierwszego zestawu bit w _X, rozpoczynając od najwyższego porządku i działającego w dół|
|[firstbitlow —](concurrency-direct3d-namespace-functions-amp.md#firstbitlow)|Pobiera lokalizację pierwszego zestawu bit w _X, rozpoczynając od najniższego bitu kolejności i działającego w górę|
|[get_buffer](concurrency-direct3d-namespace-functions-amp.md#get_buffer)|Pobierz interfejs buforu D3D jako tablicę źródłową.|
|[Imax](concurrency-direct3d-namespace-functions-amp.md#imax)|Porównuje dwie wartości, zwracając wartość, która jest większa.|
|[imin](concurrency-direct3d-namespace-functions-amp.md#imin)|Porównuje dwie wartości, zwracając wartość, która jest mniejsza.|
|[is_timeout_disabled](concurrency-direct3d-namespace-functions-amp.md#is_timeout_disabled)|Zwraca flagę logiczną wskazującą, czy limit czasu jest wyłączony dla określonego accelerator_view.|
|[Mad —](concurrency-direct3d-namespace-functions-amp.md#mad)|Przeciążone. Wykonuje arytmetyczną operację mnożenia/dodawania na trzech argumentach: _X \* _Y i _Z|
|[make_array](concurrency-direct3d-namespace-functions-amp.md#make_array)|Utwórz tablicę ze wskaźnika interfejsu buforu D3D.|
|[noise](concurrency-direct3d-namespace-functions-amp.md#noise)|Generuje losową wartość przy użyciu algorytmu szumu w języku Perl|
|[radianach](concurrency-direct3d-namespace-functions-amp.md#radians)|Konwertuje _X z stopni na radiany|
|[Analiza](concurrency-direct3d-namespace-functions-amp.md#rcp)|Oblicza szybką i przybliżoną odwrotność argumentu|
|[reversebits —](concurrency-direct3d-namespace-functions-amp.md#reversebits)|Odwraca kolejność bitów w _X|
|[Saturate —](concurrency-direct3d-namespace-functions-amp.md#saturate)|Powoduje, że _X w zakresie od 0 do 1|
|[sign](concurrency-direct3d-namespace-functions-amp.md#sign)|Przeciążone. Zwraca znak argumentu.|
|[smoothstep —](concurrency-direct3d-namespace-functions-amp.md#smoothstep)|Zwraca gładką interpolację Hermite z zakresu od 0 do 1, jeśli _X należy do zakresu [_Min, _Max].|
|[czynności](concurrency-direct3d-namespace-functions-amp.md#step)|Porównuje dwie wartości, zwracając wartość 0 lub 1 na podstawie wartości większej|
|[UMAX](concurrency-direct3d-namespace-functions-amp.md#umax)|Porównuje dwie wartości bez znaku, zwracając wartość, która jest większa.|
|[umin](concurrency-direct3d-namespace-functions-amp.md#umin)|Porównuje dwie wartości bez znaku, zwracając wartość, która jest mniejsza.|

## <a name="requirements"></a>Wymagania

**Nagłówek:** amp. h

**Przestrzeń nazw:** Współbieżności

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności (C++ AMP)](concurrency-namespace-cpp-amp.md)
