---
description: 'Dowiedz się więcej na temat: Klasa CGopherFile'
title: Klasa CGopherFile
ms.date: 11/04/2016
f1_keywords:
- CGopherFile
- AFXINET/CGopherFile
- AFXINET/CGopherFile::CGopherFile
helpviewer_keywords:
- CGopherFile [MFC], CGopherFile
ms.assetid: 3ca9898f-8cdb-4495-bbde-46d40100feda
ms.openlocfilehash: 8f511bdaf3ae6417972ea19465c0392832a2b408
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184078"
---
# <a name="cgopherfile-class"></a>Klasa CGopherFile

Oferuje funkcje znajdowania i odczytywania plików na serwerze gopher.

> [!NOTE]
> Klasy `CGopherConnection` ,, `CGopherFile` `CGopherFileFind` `CGopherLocator` i ich elementy członkowskie są przestarzałe, ponieważ nie działają na platformie Windows XP, ale będą nadal działały na wcześniejszych platformach.

## <a name="syntax"></a>Składnia

```
class CGopherFile : public CInternetFile
```

## <a name="members"></a>Elementy członkowskie

### <a name="protected-constructors"></a>Konstruktory chronione

|Nazwa|Opis|
|----------|-----------------|
|[CGopherFile::CGopherFile](#cgopherfile)|Konstruuje `CGopherFile` obiekt.|

## <a name="remarks"></a>Uwagi

Usługa gopher nie zezwala użytkownikom na zapisywanie danych w pliku gopher, ponieważ ta usługa działa głównie jako interfejs oparty na menu do znajdowania informacji. `CGopherFile`Funkcje członkowskie `Write` , `WriteString` i `Flush` nie są zaimplementowane dla `CGopherFile` . Wywołanie tych funkcji w `CGopherFile` obiekcie, zwraca [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).

Aby dowiedzieć się więcej o `CGopherFile` tym, jak działa z innymi klasami internetowymi MFC, zobacz artykuł [programowanie internetowe za pomocą usługi WinInet](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CStdioFile](../../mfc/reference/cstdiofile-class.md)

[CInternetFile](../../mfc/reference/cinternetfile-class.md)

`CGopherFile`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxinet. h

## <a name="cgopherfilecgopherfile"></a><a name="cgopherfile"></a> CGopherFile::CGopherFile

Ta funkcja członkowska jest wywoływana w celu skonstruowania `CGopherFile` obiektu.

```
CGopherFile(
    HINTERNET hFile,
    CGopherLocator& refLocator,
    CGopherConnection* pConnection);

CGopherFile(
    HINTERNET hFile,
    HINTERNET hSession,
    LPCTSTR pstrLocator,
    DWORD dwLocLen,
    DWORD_PTR dwContext);
```

### <a name="parameters"></a>Parametry

*hFile*<br/>
Dojście do pliku HINTERNET.

*refLocator*<br/>
Odwołanie do obiektu [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) .

*pConnection*<br/>
Wskaźnik do obiektu [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) .

*hSession*<br/>
Dojście do bieżącej sesji internetowej.

*pstrLocator*<br/>
Wskaźnik do ciągu służącego do lokalizowania serwera gopher. Aby uzyskać więcej informacji na temat lokalizatorów gopher, zobacz [sesje](cgopherlocator-class.md) usługi gopher.

*dwLocLen*<br/>
Wartość typu DWORD zawierająca liczbę bajtów w *pstrLocator*.

*dwContext*<br/>
Wskaźnik do identyfikatora kontekstu otwieranego pliku.

### <a name="remarks"></a>Uwagi

Potrzebujesz `CGopherFile` obiektu do odczytu z pliku podczas sesji internetowej gopher.

Nie utworzysz `CGopherFile` bezpośrednio obiektu. Zamiast tego należy wywołać [CGopherConnection:: OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) , aby otworzyć plik na serwerze gopher.

## <a name="see-also"></a>Zobacz też

[Klasa CInternetFile](../../mfc/reference/cinternetfile-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa CInternetFile](../../mfc/reference/cinternetfile-class.md)<br/>
[Klasa CGopherLocator](../../mfc/reference/cgopherlocator-class.md)<br/>
[Klasa CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md)<br/>
[Klasa CGopherConnection](../../mfc/reference/cgopherconnection-class.md)
