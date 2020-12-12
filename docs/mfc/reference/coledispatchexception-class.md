---
description: 'Dowiedz się więcej na temat: Klasa COleDispatchException'
title: Klasa COleDispatchException
ms.date: 11/04/2016
f1_keywords:
- COleDispatchException
- AFXDISP/COleDispatchException
- AFXDISP/COleDispatchException::m_dwHelpContext
- AFXDISP/COleDispatchException::m_strDescription
- AFXDISP/COleDispatchException::m_strHelpFile
- AFXDISP/COleDispatchException::m_strSource
- AFXDISP/COleDispatchException::m_wCode
helpviewer_keywords:
- COleDispatchException [MFC], m_dwHelpContext
- COleDispatchException [MFC], m_strDescription
- COleDispatchException [MFC], m_strHelpFile
- COleDispatchException [MFC], m_strSource
- COleDispatchException [MFC], m_wCode
ms.assetid: 0e95c8be-e21a-490c-99ec-181c6a9a26d0
ms.openlocfilehash: 39d8c4652f49b721e5f94c05319e5c1adad07269
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227211"
---
# <a name="coledispatchexception-class"></a>Klasa COleDispatchException

Obsługuje wyjątki specyficzne dla interfejsu OLE `IDispatch` , który jest kluczowym elementem automatyzacji OLE.

## <a name="syntax"></a>Składnia

```
class COleDispatchException : public CException
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[COleDispatchException:: m_dwHelpContext](#m_dwhelpcontext)|Kontekst pomocy dla błędu.|
|[COleDispatchException:: m_strDescription](#m_strdescription)|Opis werbalny błędu.|
|[COleDispatchException:: m_strHelpFile](#m_strhelpfile)|Plik pomocy do użycia z programem `m_dwHelpContext` .|
|[COleDispatchException:: m_strSource](#m_strsource)|Aplikacja, która wygenerowała wyjątek.|
|[COleDispatchException:: m_wCode](#m_wcode)|`IDispatch`— konkretny kod błędu.|

## <a name="remarks"></a>Uwagi

Podobnie jak w przypadku innych klas wyjątków pochodnych od `CException` klasy bazowej, `COleDispatchException` można użyć makr THROW, THROW_LAST, try, CATCH, AND_CATCH i END_CATCH.

Ogólnie rzecz biorąc, należy wywołać [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) , aby utworzyć i zgłosić `COleDispatchException` obiekt.

Aby uzyskać więcej informacji o wyjątkach, zobacz [Obsługa wyjątków artykułów (MFC)](../../mfc/exception-handling-in-mfc.md) i [wyjątki: wyjątki OLE](../../mfc/exceptions-ole-exceptions.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`COleDispatchException`

## <a name="requirements"></a>Wymagania

**Nagłówek:** AFXDISP. h

## <a name="coledispatchexceptionm_dwhelpcontext"></a><a name="m_dwhelpcontext"></a> COleDispatchException:: m_dwHelpContext

Identyfikuje kontekst pomocy w pomocy aplikacji (. HLP).

```
DWORD m_dwHelpContext;
```

### <a name="remarks"></a>Uwagi

Ten element członkowski jest ustawiany przez funkcję [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) , gdy zostanie zgłoszony wyjątek.

### <a name="example"></a>Przykład

  Zobacz przykład dla [COleDispatchDriver::](../../mfc/reference/coledispatchdriver-class.md#createdispatch)...

## <a name="coledispatchexceptionm_strdescription"></a><a name="m_strdescription"></a> COleDispatchException:: m_strDescription

Zawiera werbalny opis błędu, taki jak "dysk zapełniony".

```
CString m_strDescription;
```

### <a name="remarks"></a>Uwagi

Ten element członkowski jest ustawiany przez funkcję [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) , gdy zostanie zgłoszony wyjątek.

### <a name="example"></a>Przykład

  Zobacz przykład dla [COleDispatchDriver::](../../mfc/reference/coledispatchdriver-class.md#createdispatch)...

## <a name="coledispatchexceptionm_strhelpfile"></a><a name="m_strhelpfile"></a> COleDispatchException:: m_strHelpFile

Struktura wypełnia ten ciąg nazwą pliku pomocy aplikacji.

```
CString m_strHelpFile;
```

## <a name="coledispatchexceptionm_strsource"></a><a name="m_strsource"></a> COleDispatchException:: m_strSource

Struktura wypełnia ten ciąg nazwą aplikacji, która wygenerowała wyjątek.

```
CString m_strSource;
```

### <a name="example"></a>Przykład

  Zobacz przykład dla [COleDispatchDriver::](../../mfc/reference/coledispatchdriver-class.md#createdispatch)...

## <a name="coledispatchexceptionm_wcode"></a><a name="m_wcode"></a> COleDispatchException:: m_wCode

Zawiera kod błędu specyficzny dla Twojej aplikacji.

```
WORD m_wCode;
```

### <a name="remarks"></a>Uwagi

Ten element członkowski jest ustawiany przez funkcję [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) , gdy zostanie zgłoszony wyjątek.

## <a name="see-also"></a>Zobacz też

[Przykład CALCDRIV MFC](../../overview/visual-cpp-samples.md)<br/>
[Klasa CException](../../mfc/reference/cexception-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa COleDispatchDriver](../../mfc/reference/coledispatchdriver-class.md)<br/>
[Klasa COleException](../../mfc/reference/coleexception-class.md)
