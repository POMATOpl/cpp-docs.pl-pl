---
description: 'Dowiedz się więcej na temat: _com_ptr_t:: CreateInstance'
title: _com_ptr_t::CreateInstance
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::CreateInstance
helpviewer_keywords:
- CreateInstance method [C++]
ms.assetid: ab89b0e1-9da3-4784-a079-58b17340f111
ms.openlocfilehash: dd7ef236f25c22b25c9c083aea8439f5f5175d5b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295526"
---
# <a name="_com_ptr_tcreateinstance"></a>_com_ptr_t::CreateInstance

**Specyficzne dla firmy Microsoft**

Tworzy nowe wystąpienie obiektu z `CLSID` lub `ProgID` .

## <a name="syntax"></a>Składnia

```
HRESULT CreateInstance(
   const CLSID& rclsid,
   IUnknown* pOuter=NULL,
   DWORD dwClsContext = CLSCTX_ALL
) throw( );
HRESULT CreateInstance(
   LPCWSTR clsidString,
   IUnknown* pOuter=NULL,
   DWORD dwClsContext = CLSCTX_ALL
) throw( );
HRESULT CreateInstance(
   LPCSTR clsidStringA,
   IUnknown* pOuter=NULL,
   DWORD dwClsContext = CLSCTX_ALL
) throw( );
```

#### <a name="parameters"></a>Parametry

*rclsid*<br/>
`CLSID`Obiektu.

*clsidString*<br/>
Ciąg Unicode, który zawiera `CLSID` (Zaczynając od "**{**") lub `ProgID` .

*clsidStringA*<br/>
Ciąg wielobajtowy przy użyciu strony kodowej ANSI, która zawiera `CLSID` (Zaczynając od "**{**") lub `ProgID` .

*dwClsContext*<br/>
Kontekst do uruchamiania kodu wykonywalnego.

*pOuter*<br/>
Nieznana zewnętrzna do [agregacji](../atl/aggregation.md).

## <a name="remarks"></a>Uwagi

Te funkcje członkowskie wywołują `CoCreateInstance` do utworzenia nowego obiektu com, a następnie zapytania dla tego typu interfejsu wskaźnika inteligentnego. Wskaźnik wyników jest następnie hermetyzowany w obrębie tego `_com_ptr_t` obiektu. `Release` jest wywoływana, aby zmniejszyć liczbę odwołań dla poprzednio hermetyzowanego wskaźnika. Ta procedura zwraca wynik HRESULT wskazujący powodzenie lub niepowodzenie.

- **CreateInstance (**  *rclsid* **,**  *dwClsContext*  **)** Tworzy nowe uruchomione wystąpienie obiektu danego elementu `CLSID` .

- **CreateInstance (**  *clsidString* **,**  *dwClsContext*  **)** Tworzy nowe uruchomione wystąpienie obiektu o podanym ciągu Unicode, który zawiera `CLSID` (Zaczynając od "**{**") lub `ProgID` .

- **CreateInstance (**  *clsidStringA* **,**  *dwClsContext*  **)** Tworzy nowe uruchomione wystąpienie obiektu o podanym ciągu znaków wielobajtowych, który zawiera `CLSID` (Zaczynając od "**{**") lub `ProgID` . Wywołuje [MultiByteToWideChar](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar), w którym zakłada się, że ciąg znajduje się na stronie kodowej ANSI, a nie na stronie kodowej OEM.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Klasa _com_ptr_t](../cpp/com-ptr-t-class.md)
