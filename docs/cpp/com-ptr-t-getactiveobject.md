---
description: 'Dowiedz się więcej na temat: _com_ptr_t:: GetActiveObject'
title: _com_ptr_t::GetActiveObject
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::GetActiveObject
helpviewer_keywords:
- GetActiveObject method [C++]
ms.assetid: 2fa94853-0410-4620-91f2-136dae923f9f
ms.openlocfilehash: 96784e73d91d7be4b0674e09278183fc62e60af2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295474"
---
# <a name="_com_ptr_tgetactiveobject"></a>_com_ptr_t::GetActiveObject

**Specyficzne dla firmy Microsoft**

Dołącza do istniejącego wystąpienia obiektu danego a `CLSID` lub `ProgID` .

## <a name="syntax"></a>Składnia

```
HRESULT GetActiveObject(
   const CLSID& rclsid
) throw( );
HRESULT GetActiveObject(
   LPCWSTR clsidString
) throw( );
HRESULT GetActiveObject(
   LPCSTR clsidStringA
) throw( );
```

#### <a name="parameters"></a>Parametry

*rclsid*<br/>
`CLSID`Obiektu.

*clsidString*<br/>
Ciąg Unicode, który zawiera `CLSID` (Zaczynając od "**{**") lub `ProgID` .

*clsidStringA*<br/>
Ciąg wielobajtowy przy użyciu strony kodowej ANSI, która zawiera `CLSID` (Zaczynając od "**{**") lub `ProgID` .

## <a name="remarks"></a>Uwagi

Te funkcje członkowskie wywołują metodę **GetActiveObject** , aby pobrać wskaźnik do uruchomionego obiektu, który został zarejestrowany za pomocą OLE, a następnie wysyła zapytanie dla tego typu interfejsu wskaźnika inteligentnego. Wskaźnik wyników jest następnie hermetyzowany w obrębie tego `_com_ptr_t` obiektu. `Release` jest wywoływana, aby zmniejszyć liczbę odwołań dla poprzednio hermetyzowanego wskaźnika. Ta procedura zwraca wynik HRESULT wskazujący powodzenie lub niepowodzenie.

- **GetActiveObject (** `rclsid` **)** dołącza do istniejącego wystąpienia obiektu danego a `CLSID` .    

- **GetActiveObject (** `clsidString` **)** dołącza do istniejącego wystąpienia obiektu, w którym znajduje się ciąg Unicode, który zawiera `CLSID` (Zaczynając od "**{**") lub `ProgID` .    

- **GetActiveObject (** `clsidStringA` **)** dołącza do istniejącego wystąpienia obiektu, w którym znajduje się ciąg znaków wielobajtowych, który zawiera `CLSID` (Zaczynając od "**{**") lub `ProgID` .     Wywołuje [MultiByteToWideChar](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar), w którym zakłada się, że ciąg znajduje się na stronie kodowej ANSI, a nie na stronie kodowej OEM.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Klasa _com_ptr_t](../cpp/com-ptr-t-class.md)
