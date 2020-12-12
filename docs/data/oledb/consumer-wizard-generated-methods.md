---
description: 'Dowiedz się więcej na temat: metody Wizard-Generated konsumenta'
title: Metody konsumenta generowane przez kreatora
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB consumers, wizard-generated classes and methods
ms.assetid: d80ee51c-8bb3-4dca-8760-5808e0fb47b4
ms.openlocfilehash: 29d586a46f91e9244a09fce5628d0f3b274c554c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323290"
---
# <a name="consumer-wizard-generated-methods"></a>Metody konsumenta generowane przez kreatora

::: moniker range="msvc-160"

Kreator użytkownika ATL OLE DB nie jest dostępny w programie Visual Studio 2019 i nowszych. Można nadal ręcznie dodawać funkcje.

::: moniker-end

::: moniker range="<=msvc-150"

**Kreator użytkownika ATL OLE DB** i **Kreator aplikacji MFC** generują pewne funkcje, których należy wiedzieć. Niektóre metody są implementowane inaczej w projektach z atrybutami, więc istnieją pewne zastrzeżenia: Każdy przypadek jest objęty poniżej. Aby uzyskać informacje na temat wyświetlania wstrzykniętego kodu, zobacz [debugowanie wstrzykiwanego kodu](/visualstudio/debugger/how-to-debug-injected-code).

- `OpenAll` otwiera źródło danych, zestawy wierszy i włącza zakładki, jeśli są dostępne.

- `CloseAll` zamyka wszystkie otwarte zestawy wierszy i zwalnia wszystkie wykonania poleceń.

- `OpenRowset` jest wywoływany przez, `OpenAll` Aby otworzyć zestaw wierszy lub zestawy wierszy odbiorcy.

- `GetRowsetProperties` Pobiera wskaźnik do zestawu właściwości zestawu wierszy, za pomocą którego można ustawić właściwości.

- `OpenDataSource` otwiera źródło danych przy użyciu ciągu inicjującego określonego w oknie dialogowym **Właściwości łącza danych** .

- `CloseDataSource` w odpowiedni sposób zamyka źródło danych.

## <a name="openall-and-closeall"></a>Metody OpenAll i CloseAll

```cpp
HRESULT OpenAll();

void CloseAll();
```

Poniższy przykład pokazuje, jak można nawiązać połączenie `OpenAll` i `CloseAll` kiedy wielokrotnie wykonać to samo polecenie. Porównaj przykład kodu w [CCommand:: Close](./ccommand-class.md#close), który pokazuje odmianę, która wywołuje `Close` i `ReleaseCommand` zamiast `CloseAll` .

```cpp
int main(int argc, char* argv[])
{
   HRESULT hr;

   hr = CoInitialize(NULL);

   CCustOrdersDetail rs;      // Your CCommand-derived class
   rs.m_OrderID = 10248;      // Open order 10248
   hr = rs.OpenAll();         // (Open also executes the command)
   hr = rs.MoveFirst();         // Move to the first row and print it
   printf( "Name: %s, Unit Price: %d, Quantity: %d, Discount %d, Extended Price %d\n", rs.m_ProductName, rs.m_UnitPrice.int64, rs.m_Quantity, rs.m_Discount, rs.m_ExtendedPrice.int64 );

   // Close the first command execution
   rs.Close();

   rs.m_OrderID = 10249;      // Open order 10249 (a new order)
   hr = rs.Open();            // (Open also executes the command)
   hr = rs.MoveFirst();         // Move to the first row and print it
   printf( "Name: %s, Unit Price: %d, Quantity: %d, Discount %d, Extended Price %d\n", rs.m_ProductName, rs.m_UnitPrice.int64, rs.m_Quantity, rs.m_Discount, rs.m_ExtendedPrice.int64 );

   // Close the second command execution;
   // Instead of rs.CloseAll() you could call
   // rs.Close() and rs.ReleaseCommand():
   rs.CloseAll();

   CoUninitialize();
   return 0;
}
```

### <a name="remarks"></a>Uwagi

W przypadku zdefiniowania `HasBookmark` metody, `OpenAll` kod ustawia `DBPROP_IRowsetLocate` Właściwość. Upewnij się, że jest to możliwe tylko wtedy, gdy dostawca obsługuje tę właściwość.

## <a name="openrowset"></a>OpenRowset

```cpp
// OLE DB Template version:
HRESULT OpenRowset(DBPROPSET* pPropSet = NULL)
// Attribute-injected version:
HRESULT OpenRowset(const CSession& session, LPCWSTR szCommand = NULL);
```

`OpenAll` wywołuje tę metodę, aby otworzyć zestaw wierszy lub zestawy wierszy w odbiorcy. Zazwyczaj nie trzeba dzwonić, `OpenRowset` chyba że chcesz współpracować z wieloma źródłami danych/sesjami/zestawami wierszy. `OpenRowset` jest zadeklarowany w pliku nagłówkowym polecenia lub klasy tabeli:

```cpp
// OLE DB Template version:
HRESULT OpenRowset(DBPROPSET *pPropSet = NULL)
{
   HRESULT hr = Open(m_session, NULL, pPropSet);
   #ifdef _DEBUG
   if(FAILED(hr))
      AtlTraceErrorRecords(hr);
   #endif
   return hr;
}
```

Atrybuty implementują tę metodę inaczej. Ta wersja pobiera obiekt sesji i ciąg polecenia, który domyślnie jest ciągiem poleceń określonym w db_command, chociaż można przekazać inny. W przypadku zdefiniowania `HasBookmark` metody, `OpenRowset` kod ustawia `DBPROP_IRowsetLocate` Właściwość. Upewnij się, że jest to możliwe tylko wtedy, gdy dostawca obsługuje tę właściwość.

```cpp
// Attribute-injected version:
HRESULT OpenRowset(const CSession& session, LPCWSTR szCommand=NULL)
{

   DBPROPSET *pPropSet = NULL;
   CDBPropSet propset(DBPROPSET_ROWSET);
   __if_exists(HasBookmark)

   {
      propset.AddProperty(DBPROP_IRowsetLocate, true);
      pPropSet= &propset;
      }
...
}
```

## <a name="getrowsetproperties"></a>GetRowsetProperties

```cpp
void GetRowsetProperties(CDBPropSet* pPropSet);
```

Ta metoda pobiera wskaźnik do zestawu właściwości zestawu wierszy; Ten wskaźnik służy do ustawiania właściwości, takich jak `DBPROP_IRowsetChange` . `GetRowsetProperties` jest używany w klasie rekordu użytkownika w następujący sposób. Możesz zmodyfikować ten kod, aby ustawić dodatkowe właściwości zestawu wierszy:

```cpp
void GetRowsetProperties(CDBPropSet* pPropSet)
{
   pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
   pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
   pPropSet->AddProperty(DBPROP_IRowsetChange, true, DBPROPOPTIONS_OPTIONAL);
   pPropSet->AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE);
}
```

### <a name="remarks"></a>Uwagi

Nie należy definiować metody globalnej, `GetRowsetProperties` ponieważ może ona powodować konflikt z elementem zdefiniowanym przez kreatora. Jest to metoda wygenerowana przez kreatora, którą można uzyskać z szablonem i projektami z atrybutami. atrybuty nie wstrzyknąć tego kodu.

## <a name="opendatasource-and-closedatasource"></a>OpenDataSource i CloseDataSource

```cpp
HRESULT OpenDataSource();

void CloseDataSource();
```

### <a name="remarks"></a>Uwagi

Kreator definiuje metody `OpenDataSource` i `CloseDataSource` ; `OpenDataSource` wywołuje [CDataSource:: OpenFromInitializationString](./cdatasource-class.md#openfrominitializationstring).

::: moniker-end

## <a name="see-also"></a>Zobacz też

[Tworzenie konsumenta OLE DB przy użyciu kreatora](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)
