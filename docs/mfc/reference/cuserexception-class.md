---
description: 'Dowiedz się więcej na temat: Klasa CUserException'
title: Klasa CUserException
ms.date: 11/04/2016
f1_keywords:
- CUserException
helpviewer_keywords:
- operations [MFC], stopping
- exceptions [MFC], throwing
- CUserException class [MFC]
- errors [MFC], trapping
- operations [MFC]
- throwing exceptions [MFC], stopping user operations
ms.assetid: 2156ba6d-2cce-415a-9000-6f02c26fcd7d
ms.openlocfilehash: 6104aa2883a80f88aed03634f09ad1947e9c6794
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344968"
---
# <a name="cuserexception-class"></a>Klasa CUserException

Zgłoszono, aby zatrzymać operację użytkownika końcowego.

## <a name="syntax"></a>Składnia

```
class CUserException : public CSimpleException
```

## <a name="remarks"></a>Uwagi

Użyj `CUserException` , gdy chcesz użyć mechanizmu wyjątków throw/catch dla wyjątków specyficznych dla aplikacji. "Użytkownik" w nazwie klasy może być interpretowany jako "mój użytkownik miał coś wyjątkowego, co muszę obsłużyć".

Element `CUserException` jest generowany zwykle po wywołaniu funkcji globalnej `AfxMessageBox` w celu powiadomienia użytkownika o niepomyślnej operacji. Podczas pisania procedury obsługi wyjątków, należy obsłużyć wyjątek specjalnie, ponieważ użytkownik zazwyczaj był już powiadomiony o niepowodzeniu. Platforma zgłasza ten wyjątek w niektórych przypadkach. Aby zgłosić swój `CUserException` alert, zgłoś użytkownika, a następnie wywołaj funkcję globalną `AfxThrowUserException` .

W poniższym przykładzie funkcja zawierająca operacje, które mogą kończyć się niepowodzeniem, ostrzega użytkownika i zgłasza `CUserException` . Funkcja wywołująca przechwytuje wyjątek i obsługuje go specjalnie:

[!code-cpp[NVC_MFCExceptions#24](../../mfc/codesnippet/cpp/cuserexception-class_1.cpp)]

Aby uzyskać więcej informacji na temat korzystania z programu `CUserException` , zobacz [Obsługa wyjątków artykułów (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CUserException`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxwin. h

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa CException](../../mfc/reference/cexception-class.md)
