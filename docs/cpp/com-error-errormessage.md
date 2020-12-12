---
description: 'Dowiedz się więcej na temat: _com_error:: ErrorMessage'
title: _com_error::ErrorMessage
ms.date: 11/04/2016
f1_keywords:
- _com_error::ErrorMessage
helpviewer_keywords:
- ErrorMessage method [C++]
ms.assetid: e47335b6-01af-4975-a841-121597479eb7
ms.openlocfilehash: e7f91882d55e629744df5f26f7dcc64df1dddb22
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97296007"
---
# <a name="_com_errorerrormessage"></a>_com_error::ErrorMessage

**Specyficzne dla firmy Microsoft**

Pobiera komunikat ciągu dla HRESULT przechowywanego w `_com_error` obiekcie.

## <a name="syntax"></a>Składnia

```
const TCHAR * ErrorMessage( ) const throw( );
```

## <a name="return-value"></a>Wartość zwracana

Zwraca komunikat ciągu dla HRESULT zarejestrowanego w `_com_error` obiekcie. Jeśli HRESULT jest mapowanym 16-bitowym [kodostrzeżenia](../cpp/com-error-wcode.md), zwracany jest komunikat generyczny " `IDispatch error #<wCode>` ". Jeśli wiadomość nie zostanie znaleziona, zostanie zwrócony komunikat generyczny " `Unknown error #<hresult>` ". Zwrócony ciąg jest ciągiem Unicode lub wielobajtowym, w zależności od stanu makra _UNICODE.

## <a name="remarks"></a>Uwagi

Pobiera odpowiedni tekst komunikatu systemowego dla HRESULT zarejestrowanego w `_com_error` obiekcie. Tekst komunikatu systemowego jest uzyskiwany przez wywołanie funkcji Win32 [FormatMessage](/windows/win32/api/winbase/nf-winbase-formatmessage) . Zwracany ciąg jest przypisywany przez `FormatMessage` interfejs API i jest wydawany, gdy `_com_error` obiekt zostanie zniszczony.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Klasa _com_error](../cpp/com-error-class.md)
