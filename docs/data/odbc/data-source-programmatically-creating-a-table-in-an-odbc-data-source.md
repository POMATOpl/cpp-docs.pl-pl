---
description: 'Dowiedz się więcej na temat: Źródło danych: programowe tworzenie tabeli w źródle danych ODBC'
title: Programowe tworzenie tabeli w źródle danych ODBC
ms.date: 11/04/2016
helpviewer_keywords:
- programmatically creating ODBC tables [C++]
- tables [C++]
- ODBC data sources, creating tables in
- tables [C++], creating programmatically
ms.assetid: 9ca68fb5-c3df-424a-a75c-e3fb01cc1b18
ms.openlocfilehash: b195cc4fb81f1caed0b280c5df6a2032f4944ddf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155712"
---
# <a name="data-source-programmatically-creating-a-table-in-an-odbc-data-source"></a>Źródło danych: programowe tworzenie tabeli w źródle danych ODBC

W tym temacie wyjaśniono, jak utworzyć tabelę dla źródła danych przy użyciu `ExecuteSQL` funkcji składowej klasy `CDatabase` , przekazując funkcję do ciągu, który zawiera **CREATE TABLE** instrukcji SQL.

Aby uzyskać ogólne informacje o źródłach danych ODBC w MFC, zobacz [Data Source (ODBC)](../../data/odbc/data-source-odbc.md). [Źródło danych tematu: programowe Konfigurowanie źródła danych ODBC](../../data/odbc/data-source-programmatically-configuring-an-odbc-data-source.md) opisuje Tworzenie źródeł danych.

Po ustanowieniu źródła danych można łatwo tworzyć tabele przy użyciu `ExecuteSQL` funkcji członkowskiej i **CREATE TABLE** instrukcji SQL. Na przykład jeśli `CDatabase` obiekt został wywołany `myDB` , można użyć następującego kodu MFC, aby utworzyć tabelę:

```
myDB.ExecuteSQL("CREATE TABLE OFFICES (OfficeID TEXT(4)" ",
                         OfficeName TEXT(10))");
```

Ten przykład kodu tworzy tabelę o nazwie "BIURAs" w połączeniu ze źródłem danych programu Microsoft Access obsługiwanym przez program `myDB` ; tabela zawiera dwa pola "OfficeId" i "OfficeName".

> [!NOTE]
> Typy pól określone w instrukcji SQL **CREATE TABLE** mogą się różnić w zależności od używanego sterownika ODBC. Program Microsoft Query (dystrybuowany z Visual C++ 1,5) jest jednym ze sposobów wykrywania, jakie typy pól są dostępne dla źródła danych. W programie Microsoft Query kliknij pozycję **plik**, kliknij pozycję **Table_Definition**, wybierz tabelę ze źródła danych i poszukaj typu wyświetlanego w polu kombi **Typ** . Istnieje również składnia SQL do tworzenia indeksów.

## <a name="see-also"></a>Zobacz też

[Źródło danych (ODBC)](../../data/odbc/data-source-odbc.md)
