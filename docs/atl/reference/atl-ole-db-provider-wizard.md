---
description: 'Dowiedz się więcej na temat: Kreator dostawcy OLE DB ATL'
title: Kreator dostawcy interfejsu OLE DB ATL
ms.date: 05/09/2019
helpviewer_keywords:
- ATL projects, adding ATL OLE DB providers
ms.assetid: cf91ba78-01d1-4d12-b673-e95d96bfbebe
ms.openlocfilehash: 068670205c45c559e8b312d633d715f51a78190d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165345"
---
# <a name="atl-ole-db-provider-wizard"></a>Kreator dostawcy interfejsu OLE DB ATL

::: moniker range="msvc-160"

Ten Kreator nie jest dostępny w programie Visual Studio 2019 i nowszych.

::: moniker-end

::: moniker range="<=msvc-150"

## <a name="remarks"></a>Uwagi

Począwszy od programu Visual Studio 2008 skrypt rejestracji utworzony przez tego kreatora spowoduje zarejestrowanie jego składników modelu COM w **HKEY_CURRENT_USER** , a nie **HKEY_LOCAL_MACHINE**. Aby zmienić to zachowanie, ustaw opcję **Zarejestruj składnik dla wszystkich użytkowników** w Kreatorze ATL.

W poniższej tabeli opisano opcje kreatora dostawcy OLE DB ATL:

- **Krótka nazwa**

   Wpisz krótką nazwę dostawcy, który ma zostać utworzony. Pozostałe pola edycji w kreatorze zostaną automatycznie wypełnione w oparciu o wpisany tutaj tekst. Jeśli chcesz, możesz edytować inne pola nazw.

- **Klasa coclass**

   Nazwa klasy coclass. Nazwa identyfikatora ProgID zmieni się w taki sposób, aby odpowiadała tej nazwie.

- **Przypisanych**

   Ta opcja określa, czy Kreator ma tworzyć klasy dostawców przy użyciu atrybutów lub deklaracji szablonu. Po wybraniu tej opcji Kreator używa atrybutów zamiast deklaracji szablonu (jest to opcja domyślna w przypadku utworzenia projektu z atrybutem). Po wyczyszczeniu tej opcji Kreator używa deklaracji szablonu zamiast atrybutów (jest to opcja domyślna, jeśli utworzono projekt bez atrybutu).

   W przypadku wybrania tej opcji podczas tworzenia projektu bez atrybutu zostanie wyświetlony komunikat z ostrzeżeniem, że projekt zostanie przekonwertowany na projekt z atrybutami i zostanie wyświetlony monit z pytaniem, czy kontynuować, czy nie.

- **ProgID**

   Identyfikator ProgID lub program programistyczny to ciąg tekstowy, który może być używany przez aplikację zamiast identyfikatora GUID. Nazwa ProgID ma postać *ProjectName. coclassname*.

- **Wersja**

   Numer wersji dostawcy. Wartość domyślna to 1.

- **DataSource — Klasa**

   Nazwa klasy źródła danych w postaci C *ShortName* source.

- **Plik DataSource. h**

   Plik nagłówkowy klasy źródła danych. Można edytować nazwę tego pliku lub wybrać istniejący plik nagłówkowy.

- **Klasa sesji**

   Nazwa klasy sesji w postaci C *ShortName* sesji.

- **Plik Session. h**

   Plik nagłówkowy klasy sesji. Można edytować nazwę tego pliku lub wybrać istniejący plik nagłówkowy.

- **Klasa polecenia**

   Nazwa klasy polecenia w postaci C *ShortName* polecenia.

- **Plik Command. h**

   Plik nagłówkowy klasy Command. Ta nazwa nie może być edytowana i zależy od nazwy pliku nagłówkowego zestawu wierszy.

- **Klasa zestawu wierszy**

   Nazwa klasy zestawu wierszy w postaci C *ShortName* zestawu wierszy.

- **Plik Rowset. h**

   Plik nagłówkowy klasy zestawu wierszy. Można edytować nazwę tego pliku lub wybrać istniejący plik nagłówkowy.

- **Plik. cpp zestawu wierszy**

   Plik implementacji dostawcy. Można edytować nazwę tego pliku lub wybrać istniejący plik implementacji.

::: moniker-end

## <a name="see-also"></a>Zobacz też

[Dostawca OLE DB ATL](../../atl/reference/adding-an-atl-ole-db-provider.md)
