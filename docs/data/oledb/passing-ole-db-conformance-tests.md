---
description: 'Dowiedz się więcej o: przekazywanie testów zgodności OLE DB'
title: Przechodzenie testów zgodności z OLE DB
ms.date: 11/04/2016
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- conformance testing
- conformance testing [OLE DB]
- OLE DB providers, testing
ms.assetid: d1a4f147-2edd-476c-b452-0e6a0ac09891
ms.openlocfilehash: d2a5b788b3a118293800b02a9383fbde9845cfa5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286726"
---
# <a name="passing-ole-db-conformance-tests"></a>Przechodzenie testów zgodności z OLE DB

Aby zapewnić bardziej spójność dostawców, zestaw SDK dostępu do danych zawiera zestaw OLE DB testów zgodności. Testy sprawdzają wszystkie aspekty dostawcy i zapewniają gwarancję, że dostawca działa zgodnie z oczekiwaniami. Testy zgodności OLE DB można znaleźć w zestawie SDK dostępu do danych firmy Microsoft. Ta sekcja koncentruje się na czynnościach, które należy wykonać, aby przekazać testy zgodności. Aby uzyskać informacje o uruchamianiu testów zgodności OLE DB, zobacz zestaw SDK.

## <a name="running-the-conformance-tests"></a>Uruchamianie testów zgodności

W Visual C++ 6,0 szablony dostawcy OLE DB dodaliśmy wiele funkcji podłączania, aby umożliwić sprawdzanie wartości i właściwości. Większość z tych funkcji została dodana w odpowiedzi na testy zgodności.

> [!NOTE]
> Należy dodać kilka funkcji walidacji dla dostawcy, aby przekazać OLE DB testy zgodności.

Ten dostawca wymaga dwóch procedur walidacji. Pierwsza procedura, `CRowsetImpl::ValidateCommandID` , jest częścią klasy zestawu wierszy. Jest on wywoływany podczas tworzenia zestawu wierszy przez szablony dostawców. Przykład korzysta z tej procedury, aby poinformować odbiorców, że nie obsługuje indeksów. Pierwsze wywołanie to `CRowsetImpl::ValidateCommandID` (należy zwrócić uwagę na to, że Dostawca używa `_RowsetBaseClass` elementu typedef dodanego w mapie interfejsu dla programu `CCustomRowset` w ramach [pomocy technicznej dla zakładek](../../data/oledb/provider-support-for-bookmarks.md), więc nie trzeba pisać tego długiej linii argumentów szablonu). Następnie Zwróć DB_E_NOINDEX, jeśli parametr index nie ma wartości NULL (oznacza to, że odbiorca chce użyć indeksu w Stanach Zjednoczonych). Aby uzyskać więcej informacji o identyfikatorach poleceń, zobacz specyfikację OLE DB i Wyszukaj `IOpenRowset::OpenRowset` .

Następujący kod jest `ValidateCommandID` procedurą walidacji:

```cpp
/////////////////////////////////////////////////////////////////////
// CustomRS.H
// Class: CCustomRowset

HRESULT ValidateCommandID(DBID* pTableID, DBID* pIndexID)
{
   HRESULT hr = _RowsetBaseClass::ValidateCommandID(pTableID, pIndexID);
   if (hr != S_OK)
      return hr;

   if (pIndexID != NULL)
      return DB_E_NOINDEX;    // Doesn't support indexes

   return S_OK;
}
```

Szablony dostawcy wywołują `OnPropertyChanged` metodę, gdy ktoś zmieni właściwość w grupie DBPROPSET_ROWSET. Aby obsłużyć właściwości innych grup, należy dodać je do odpowiedniego obiektu (to jest, DBPROPSET_SESSION sprawdzenia w `CCustomSession` klasie).

Kod najpierw sprawdza, czy właściwość jest połączona z inną. Jeśli właściwość jest łańcucha, ustawia właściwość DBPROP_BOOKMARKS na `True` . Dodatek C specyfikacji OLE DB zawiera informacje na temat właściwości. Informacje te informują również o tym, czy właściwość jest łańcuchem do innej.

Możesz również dodać `IsValidValue` procedurę do kodu. `IsValidValue`Podczas próby ustawienia właściwości wywołanie szablonów. Tę metodę należy zastąpić, jeśli wymagane jest dodatkowe przetwarzanie podczas ustawiania wartości właściwości. Dla każdego zestawu właściwości można mieć jedną z tych metod.

## <a name="see-also"></a>Zobacz też

[Zaawansowane techniki dostawcy](../../data/oledb/advanced-provider-techniques.md)
