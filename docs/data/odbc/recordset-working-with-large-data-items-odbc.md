---
description: 'Dowiedz się więcej o: zestaw rekordów: Praca z dużymi elementami danych (ODBC)'
title: 'Zestaw rekordów: praca z dużymi elementami danych (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- BLOB (binary large object), recordsets
- ODBC recordsets, binary large objects
- recordsets, binary large objects
- binary large objects
- CLongBinary class, using in recordsets
ms.assetid: 3e80b5a8-b6e7-43c6-a816-e54befc513a3
ms.openlocfilehash: 7a4ca6de9c0b5be32626c8ca3c7c66cc516057e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204371"
---
# <a name="recordset-working-with-large-data-items-odbc"></a>Zestaw rekordów: praca z dużymi elementami danych (ODBC)

Ten temat dotyczy zarówno klas MFC ODBC, jak i klas MFC DAO.

> [!NOTE]
> Jeśli używasz klas MFC DAO, Zarządzaj dużymi elementami danych przy użyciu klasy [CByteArray](../../mfc/reference/cbytearray-class.md) zamiast klasy [CLongBinary](../../mfc/reference/clongbinary-class.md). Jeśli używasz klas MFC ODBC z pobraniem wierszy zbiorczych, użyj `CLongBinary` zamiast `CByteArray` . Aby uzyskać więcej informacji na temat pobierania wierszy zbiorczych, zobacz [zestaw rekordów: pobieranie rekordów zbiorczo (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Załóżmy, że baza danych może przechowywać duże fragmenty danych, takie jak mapy bitowe (fotografie pracowników, mapy, obrazy produktów, obiekty OLE itd.). Ten rodzaj danych jest często określany jako obiekt binarny (lub obiekt BLOB), ponieważ:

- Każda wartość pola jest duża.

- W przeciwieństwie do liczb i innych prostych typów danych, nie ma rozmiaru przewidywalnego.

- Dane są niezgodne z perspektywą programu.

W tym temacie wyjaśniono, co obsługuje Klasa bazy danych do pracy z takimi obiektami.

## <a name="managing-large-objects"></a><a name="_core_managing_large_objects"></a> Zarządzanie dużymi obiektami

Zestawy rekordów mają dwa sposoby rozwiązywania szczególnych trudności związanych z zarządzaniem dużymi obiektami binarnymi. Można użyć klasy [CByteArray](../../mfc/reference/cbytearray-class.md) lub użyć klasy [CLongBinary](../../mfc/reference/clongbinary-class.md). Ogólnie rzecz biorąc, `CByteArray` jest preferowanym sposobem zarządzania dużymi danymi binarnymi.

`CByteArray` wymaga większego nakładu pracy `CLongBinary` , ale jest bardziej możliwe, zgodnie z opisem w [klasie CByteArray](#_core_the_cbytearray_class). `CLongBinary` został krótko opisany w [klasie CLongBinary](#_core_the_clongbinary_class).

Aby uzyskać szczegółowe informacje na temat używania `CByteArray` programu do pracy z dużymi elementami danych, zobacz [uwagi techniczne 45](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md).

## <a name="cbytearray-class"></a><a name="_core_the_cbytearray_class"></a> Klasa CByteArray

`CByteArray` jest jedną z klas kolekcji MFC. `CByteArray`Obiekt przechowuje dynamiczną tablicę bajtów — w razie konieczności można zwiększyć tablicę. Klasa zapewnia szybki dostęp według indeksu, tak jak w przypadku wbudowanych tablic języka C++. `CByteArray` obiekty mogą być serializowane i zrzucane w celach diagnostycznych. Klasa dostarcza funkcje członkowskie do pobierania i ustawiania określonych bajtów, wstawiania i dołączania bajtów oraz usuwania jednego bajtu lub wszystkich bajtów. Te obiekty umożliwiają łatwiejsze analizowanie danych binarnych. Na przykład jeśli obiekt binarny jest obiektem OLE, może być konieczne przechodzenie przez niektóre bajty nagłówka w celu uzyskania dostępu do rzeczywistego obiektu.

## <a name="using-cbytearray-in-recordsets"></a><a name="_core_using_cbytearray_in_recordsets"></a> Używanie CByteArray w zestawach rekordów

Dostarczając element członkowski danych pola w zestawie rekordów, `CByteArray` należy podać stałą podstawę, z której [RFX](../../data/odbc/record-field-exchange-rfx.md) może zarządzać transferem takiego obiektu między zestawem rekordów a źródłem danych i za pomocą którego można manipulować danymi wewnątrz obiektu. RFX potrzebuje określonej lokacji do pobierania danych i potrzebujesz dostępu do danych bazowych.

Aby uzyskać szczegółowe informacje na temat używania `CByteArray` programu do pracy z dużymi elementami danych, zobacz [uwagi techniczne 45](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md).

## <a name="clongbinary-class"></a><a name="_core_the_clongbinary_class"></a> Klasa CLongBinary

Obiekt [CLongBinary](../../mfc/reference/clongbinary-class.md) jest prostą powłoką wokół `HGLOBAL` dojścia do bloku magazynu przydzieloną na stercie. Gdy tworzy powiązanie kolumny tabeli zawierającej duży obiekt binarny, RFX przydziela `HGLOBAL` dojście, gdy musi przesłać dane do zestawu rekordów i przechowuje uchwyt w `CLongBinary` polu zestawu rekordów.

Z kolei można używać `HGLOBAL` dojścia, `m_hData` aby współdziałać z danymi, na przykład na wszystkich dowolnych danych. Jest to miejsce, w którym [CByteArray](../../mfc/reference/cbytearray-class.md) dodaje możliwości.

> [!CAUTION]
> Nie można używać obiektów CLongBinary jako parametrów w wywołaniach funkcji. Ponadto ich implementacja, która wywołuje `::SQLGetData` , niekoniecznie spowalnia wydajność przewijania dla migawki, którą można przewijać. Może to również być prawdziwe, jeśli używasz `::SQLGetData` wywołania do pobierania dynamicznych kolumn schematu.

## <a name="see-also"></a>Zobacz też

[Zestaw rekordów (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Zestaw rekordów: uzyskiwanie sum i innych wyników agregacji (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)<br/>
[Wymiana pól rekordów (RFX)](../../data/odbc/record-field-exchange-rfx.md)
