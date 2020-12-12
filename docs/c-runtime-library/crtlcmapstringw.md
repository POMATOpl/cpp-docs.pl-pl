---
description: 'Dowiedz się więcej na temat: __crtLCMapStringW'
title: __crtLCMapStringW
ms.date: 11/04/2016
api_name:
- __crtLCMapStringW
api_location:
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcrt.dll
- msvcr120.dll
- msvcr110.dll
- msvcr80.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __crtLCMapStringW
helpviewer_keywords:
- __crtLCMapStringW
ms.assetid: 45b4ac0e-438c-4fa3-b4d1-34195f4467d9
ms.openlocfilehash: 57b3f7e961de94d8a3dbd045a1fa1d74681cbfdc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97246764"
---
# <a name="__crtlcmapstringw"></a>__crtLCMapStringW

Mapuje jeden ciąg znaków na inny, wykonując określoną transformację zależną od ustawień regionalnych. Ta funkcja może również służyć do generowania klucza sortowania dla ciągu wejściowego.

## <a name="syntax"></a>Składnia

```cpp
int __crtLCMapStringW(
   LCID    Locale,
   DWORD   dwMapFlags,
   LPCWSTR lpSrcStr,
   int     cchSrc,
   LPWSTR  lpDestStr,
   int     cchDest)
```

#### <a name="parameters"></a>Parametry

*Ustawienie*<br/>
Identyfikator ustawień regionalnych. Ustawienia regionalne zapewniają kontekst mapowania ciągów lub generowania klucza sortowania. Aplikacja może użyć `MAKELCID` makra do utworzenia identyfikatora ustawień regionalnych.

*dwMapFlags*<br/>
Typ transformacji, która ma być używana podczas mapowania ciągu lub generowania klucza sortowania.

*lpSrcStr*<br/>
Wskaźnik do ciągu źródłowego, który funkcja mapuje lub używa do generowania klucza sortowania. Przyjęto, że ten parametr jest ciągiem Unicode.

*cchSrc*<br/>
Rozmiar ciągu wskazywanego przez parametr w znakach `lpSrcStr` . Ta liczba może zawierać terminator o wartości null lub nie zawierać go.

`cchSrc`Wartość-1 określa, że ciąg wskazywany przez `lpSrcStr` jest zakończony znakiem null. W takim przypadku, gdy ta funkcja jest używana w trybie mapowania ciągów, funkcja oblicza samą długość ciągu, a wartość null kończy zamapowanego ciągu przechowywanego w `*lpDestStr` .

*lpDestStr*<br/>
Długi wskaźnik do buforu, do którego funkcja przechowuje zamapowany ciąg lub klucz sortowania.

*cchDest*<br/>
Rozmiar (w znakach) buforu wskazywanego przez `lpDestStr` .

## <a name="return-value"></a>Wartość zwracana

Jeśli wartość `cchDest` jest różna od zera, liczba znaków lub bajty, jeśli `LCMAP_SORTKEY` jest określona, zapisywana w buforze wskazuje na powodzenie. Ta liczba obejmuje pomieszczenie dla terminatora o wartości null.

Jeśli wartość `cchDest` jest równa zero, rozmiar buforu w znakach lub bajty, jeśli `LCMAP_SORTKEY` jest określony, wymagane do odebrania przetłumaczonego ciągu lub klucza sortowania wskazuje na powodzenie. Ten rozmiar obejmuje pomieszczenie dla terminatora o wartości null.

Zero wskazuje na błąd. Aby uzyskać rozszerzone informacje o błędzie, wywołaj `GetLastError` funkcję.

## <a name="remarks"></a>Uwagi

Jeśli `cchSrc` jest większa od zera i `lpSrcStr` jest ciągiem zakończonym wartością null, `__crtLCMapStringW` ustawia `cchSrc` Długość ciągu. Następnie `__crtLCMapStringW` wywołuje funkcję szerokiego ciągu (Unicode) `LCMapString` funkcji z określonymi parametrami. Aby uzyskać więcej informacji na temat parametrów i wartości zwracanej przez tę funkcję, zobacz [LCMapString](/windows/win32/api/winnls/nf-winnls-lcmapstringw).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|__crtLCMapStringW|awint. h|
