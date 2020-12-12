---
description: 'Dowiedz się więcej na temat: _com_raise_error'
title: _com_raise_error
ms.date: 11/04/2016
f1_keywords:
- _com_raise_error
helpviewer_keywords:
- _com_raise_error function
ms.assetid: a98226c2-c3fe-44f1-8ff5-85863de11cd6
ms.openlocfilehash: 81697b565104971d22da04a7b8b0e33a7f9255ac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97178215"
---
# <a name="_com_raise_error"></a>_com_raise_error

**Specyficzne dla firmy Microsoft**

Zgłasza [_com_error](../cpp/com-error-class.md) w odpowiedzi na awarię.

## <a name="syntax"></a>Składnia

```cpp
void __stdcall _com_raise_error(
   HRESULT hr,
   IErrorInfo* perrinfo = 0
);
```

#### <a name="parameters"></a>Parametry

*godz.*<br/>
Informacje o HRESULT.

*perrinfo*<br/>
`IErrorInfo` Stream.

## <a name="remarks"></a>Uwagi

**_com_raise_error**, który jest zdefiniowany w \<comdef.h> , może być zastąpiona przez zapisaną przez użytkownika wersję o tej samej nazwie i prototypie. Można to zrobić, jeśli chcesz użyć, `#import` ale nie chcesz używać obsługi wyjątków C++. W takim przypadku wersja użytkownika **_com_raise_error** może zdecydować się na wykonanie `longjmp` lub wyświetlenie okna komunikatu i zatrzymanie. Wersja użytkownika nie powinna zwracać, chociaż, ponieważ kod obsługi języka COM kompilatora nie oczekuje, że zwraca.

Można również użyć [_set_com_error_handler](../cpp/set-com-error-handler.md) , aby zastąpić domyślną funkcję obsługi błędów.

Domyślnie **_com_raise_error** jest zdefiniowana w następujący sposób:

```cpp
void __stdcall _com_raise_error(HRESULT hr, IErrorInfo* perrinfo) {
   throw _com_error(hr, perrinfo);
}
```

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<comdef.h>

**Lib:** Jeśli **wchar_t jest opcja kompilatora typu natywnego** , użyj comsuppw. lib lub comsuppwd. lib. Jeśli **wchar_t jest typu natywnego** , użyj comsupp. lib. Aby uzyskać więcej informacji, zobacz [/Zc: wchar_t (Wchar_t jest typem natywnym)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).

## <a name="see-also"></a>Zobacz też

[Funkcje globalne kompilatora COM](../cpp/compiler-com-global-functions.md)<br/>
[_set_com_error_handler](../cpp/set-com-error-handler.md)
