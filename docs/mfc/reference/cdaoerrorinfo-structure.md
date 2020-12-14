---
description: Dowiedz się więcej o strukturze CDaoErrorInfo —
title: CDaoErrorInfo — Struktura
ms.date: 09/17/2019
f1_keywords:
- CDaoErrorInfo
helpviewer_keywords:
- CDaoErrorInfo structure [MFC]
- DAO (Data Access Objects), Errors collection
ms.assetid: cd37ef71-b0b3-401d-bc2b-540c9147f532
ms.openlocfilehash: 3d8ae4bd133c96ef1853c8d087904c7c6eba810d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250962"
---
# <a name="cdaoerrorinfo-structure"></a>CDaoErrorInfo — Struktura

`CDaoErrorInfo`Struktura zawiera informacje o obiekcie Error zdefiniowanym dla obiektów dostępu do danych (DAO). Element DAO 3,6 jest wersją ostateczną i jest uznawany za przestarzały.

## <a name="syntax"></a>Składnia

```
struct CDaoErrorInfo
{
    long m_lErrorCode;
    CString m_strSource;
    CString m_strDescription;
    CString m_strHelpFile;
    long m_lHelpContext;
};
```

#### <a name="parameters"></a>Parametry

*m_lErrorCode*<br/>
Liczbowy kod błędu DAO. Zapoznaj się z tematem "błędy dostępu do danych z pułapkami" w pomocy programu DAO.

*m_strSource*<br/>
Nazwa obiektu lub aplikacji, która pierwotnie wygenerowała błąd. Właściwość Source określa wyrażenie ciągu reprezentujące obiekt, który pierwotnie wygenerował błąd; wyrażenie jest zazwyczaj nazwą klasy obiektu. Aby uzyskać szczegółowe informacje, zobacz temat "Właściwość Source" w pomocy DAO.

*m_strDescription*<br/>
Opisowy ciąg skojarzony z błędem. Aby uzyskać szczegółowe informacje, zobacz temat "opis właściwości" w pomocy DAO.

*m_strHelpFile*<br/>
W pełni kwalifikowana ścieżka do pliku pomocy systemu Microsoft Windows. Aby uzyskać szczegółowe informacje, zobacz temat "atrybut HelpContext, HelpFile Properties" w pomocy DAO.

*m_lHelpContext*<br/>
Identyfikator kontekstu tematu w pliku pomocy systemu Microsoft Windows. Aby uzyskać szczegółowe informacje, zobacz temat "atrybut HelpContext, HelpFile Properties" w pomocy DAO.

## <a name="remarks"></a>Uwagi

MFC nie hermetyzuje obiektów błędów DAO w klasie. Zamiast tego Klasa [CDaoException](../../mfc/reference/cdaoexception-class.md) dostarcza interfejs do uzyskiwania dostępu do kolekcji Errors zawartej w obiekcie DAO `DBEngine` , obiekt, który również zawiera wszystkie obszary robocze. Gdy operacja MFC DAO zgłasza obiekt, `CDaoException` który przechwytuje, MFC wypełnia `CDaoErrorInfo` strukturę i zapisuje ją w elemencie członkowskim [m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) obiektu wyjątku. (W przypadku wybrania bezpośredniego wywoływania obiektów DAO należy wywoływać funkcję elementu członkowskiego [GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo) obiektu Exception do wypełnienia `m_pErrorInfo` ).

Aby uzyskać więcej informacji na temat obsługi błędów DAO, zobacz [wyjątki w artykule: wyjątki bazy danych](../../mfc/exceptions-database-exceptions.md). Aby uzyskać powiązane informacje, zobacz temat "błąd obiektu" w pomocy DAO.

Informacje pobierane przez funkcję członkowską [CDaoException:: GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo) są przechowywane w `CDaoErrorInfo` strukturze. Sprawdź element członkowski danych [m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) z `CDaoException` obiektu, który znajduje się w procedurze obsługi wyjątków, lub wywołaj `GetErrorInfo` z `CDaoException` obiektu, który utworzysz jawnie w celu sprawdzenia błędów, które mogły wystąpić podczas bezpośredniego wywołania interfejsów DAO. `CDaoErrorInfo` definiuje również `Dump` funkcję członkowską w kompilacjach debugowania. Możesz użyć, `Dump` aby zrzucić zawartość `CDaoErrorInfo` obiektu.

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxdao. h

## <a name="see-also"></a>Zobacz też

[Struktury, style, wywołania zwrotne i mapy komunikatów](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[Klasa CDaoException](../../mfc/reference/cdaoexception-class.md)
