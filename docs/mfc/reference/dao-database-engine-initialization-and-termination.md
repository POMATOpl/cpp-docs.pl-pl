---
description: 'Dowiedz się więcej o: inicjalizacji i zakończeniu aparatu bazy danych DAO'
title: Inicjowanie i kończenie działania aparatu bazy danych DAO
ms.date: 09/17/2019
helpviewer_keywords:
- DAO (Data Access Objects), termination
- DAO (Data Access Objects), initialization
ms.assetid: a7edf31c-e7c2-4f3e-aada-63c3e48781da
ms.openlocfilehash: 9e9b522d744eabc84074b201051151b80ed75d7e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220399"
---
# <a name="dao-database-engine-initialization-and-termination"></a>Inicjowanie i kończenie działania aparatu bazy danych DAO

Obiekty DAO są używane z bazami danych programu Access i są obsługiwane za pomocą pakietu Office 2013. Element DAO 3,6 jest wersją ostateczną i jest uznawany za przestarzały. W przypadku korzystania z obiektów MFC DAO aparat bazy danych DAO musi zostać najpierw zainicjowany, a następnie przerwany przed zakończeniem działania aplikacji lub biblioteki DLL. Dwie funkcje `AfxDaoInit` i `AfxDaoTerm` , wykonaj te zadania.

### <a name="dao-database-engine-initialization-and-termination"></a>Inicjowanie i kończenie działania aparatu bazy danych DAO

|Nazwa|Opis|
|-|-|
|[AfxDaoInit](#afxdaoinit)|Inicjuje aparat bazy danych DAO.|
|[AfxDaoTerm](#afxdaoterm)|Kończy działanie aparatu bazy danych DAO.|

## <a name="afxdaoinit"></a><a name="afxdaoinit"></a> AfxDaoInit

Ta funkcja inicjuje aparat bazy danych DAO.

```

void AfxDaoInit();

throw(CDaoException*);
```

### <a name="remarks"></a>Uwagi

W większości przypadków nie trzeba wywoływać, `AfxDaoInit` ponieważ aplikacja automatycznie wywołuje ją, gdy jest potrzebna.

Aby uzyskać informacje pokrewne, a na przykład wywoływanie `AfxDaoInit` , zobacz [uwagi techniczne 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

### <a name="requirements"></a>Wymagania

  **Nagłówek** afxdao. h

## <a name="afxdaoterm"></a><a name="afxdaoterm"></a> AfxDaoTerm

Ta funkcja przerywa aparat bazy danych DAO.

```

void AfxDaoTerm();
```

### <a name="remarks"></a>Uwagi

Zazwyczaj należy wywołać tę funkcję tylko w zwykłej bibliotece MFC DLL; Aplikacja zostanie automatycznie wywołana w `AfxDaoTerm` razie konieczności.

W zwykłych bibliotekach DLL MFC Wywołaj `AfxDaoTerm` przed `ExitInstance` funkcją, ale po zniszczeniu wszystkich obiektów MFC DAO.

Aby uzyskać powiązane informacje, zobacz [Uwagi techniczne 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

### <a name="requirements"></a>Wymagania

  **Nagłówek** afxdao. h

## <a name="see-also"></a>Zobacz też

[Makra i Globals](../../mfc/reference/mfc-macros-and-globals.md)
