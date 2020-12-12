---
description: 'Dowiedz się więcej na temat: _set_com_error_handler'
title: _set_com_error_handler
ms.date: 11/04/2016
helpviewer_keywords:
- _set_com_error_handler function
ms.assetid: 49fe4fca-5e37-4d83-abaf-15be5ce37f94
ms.openlocfilehash: 88c59f30276089f28dc6e40b1ab5829bf68a7b4a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116967"
---
# <a name="_set_com_error_handler"></a>_set_com_error_handler

Zastępuje domyślną funkcję, która jest używana do obsługi błędów COM. **_set_com_error_handler** to specyficzny dla firmy Microsoft.

## <a name="syntax"></a>Składnia

```cpp
void __stdcall _set_com_error_handler(
   void (__stdcall *pHandler)(
      HRESULT hr,
      IErrorInfo* perrinfo
   )
);
```

#### <a name="parameters"></a>Parametry

*pHandler*<br/>
Wskaźnik do funkcji zastępczej.

*godz.*<br/>
Informacje o HRESULT.

*perrinfo*<br/>
`IErrorInfo` Stream.

## <a name="remarks"></a>Uwagi

Domyślnie [_com_raise_error](../cpp/com-raise-error.md) obsługuje wszystkie błędy com. Można zmienić to zachowanie przy użyciu **_set_com_error_handler** do wywołania własnej funkcji obsługi błędów.

Funkcja zastępująca musi mieć sygnaturę odpowiadającą elementowi `_com_raise_error` .

## <a name="example"></a>Przykład

```cpp
// _set_com_error_handler.cpp
// compile with /EHsc
#include <stdio.h>
#include <comdef.h>
#include <comutil.h>

// Importing ado dll to attempt to establish an ado connection.
// Not related to _set_com_error_handler
#import "C:\Program Files\Common Files\System\ado\msado15.dll" no_namespace rename("EOF", "adoEOF")

void __stdcall _My_com_raise_error(HRESULT hr, IErrorInfo* perrinfo)
{
   throw "Unable to establish the connection!";
}

int main()
{
   _set_com_error_handler(_My_com_raise_error);
   _bstr_t bstrEmpty(L"");
   _ConnectionPtr Connection = NULL;
   try
   {
      Connection.CreateInstance(__uuidof(Connection));
      Connection->Open(bstrEmpty, bstrEmpty, bstrEmpty, 0);
   }
   catch(char* errorMessage)
   {
      printf("Exception raised: %s\n", errorMessage);
   }

   return 0;
}
```

```Output
Exception raised: Unable to establish the connection!
```

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<comdef.h>

**Lib:** Jeśli określono opcję kompilatora **/Zc: wchar_t** (wartość domyślna), użyj comsuppw. lib lub comsuppwd. lib. Jeśli jest określona opcja **/Zc: wchar_t-** Compiler, użyj comsupp. lib. Aby uzyskać więcej informacji, w tym o sposobie ustawiania tej opcji w IDE, zobacz [/Zc: wchar_t (Wchar_t jest typem natywnym)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).

## <a name="see-also"></a>Zobacz też

[Funkcje globalne kompilatora COM](../cpp/compiler-com-global-functions.md)
