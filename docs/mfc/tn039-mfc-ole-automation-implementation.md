---
description: 'Dowiedz się więcej o: TN039: implementacja automatyzacji MFC/OLE'
title: 'TN039: implementacja automatyzacji MFC-OLE'
ms.date: 06/28/2018
helpviewer_keywords:
- MFC, COM support
- IDispatch interface
- MFC, OLE DB and
- TN039
- Automation, MFC COM interface entry points
ms.assetid: 765fa3e9-dd54-4f08-9ad2-26e0546ff8b6
ms.openlocfilehash: caabd3719a467e534e47ca61ed8f9a9f1f0d2eb6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215420"
---
# <a name="tn039-mfcole-automation-implementation"></a>TN039: implementacja automatyzacji MFC/OLE

> [!NOTE]
> Następująca Uwaga techniczna nie została zaktualizowana, ponieważ została najpierw uwzględniona w dokumentacji online. W związku z tym niektóre procedury i tematy mogą być nieaktualne lub nieprawidłowe. Aby uzyskać najnowsze informacje, zalecamy wyszukiwanie tematu zainteresowania w indeksie dokumentacji online.

## <a name="overview-of-ole-idispatch-interface"></a>Omówienie interfejsu OLE IDispatch

`IDispatch`Interfejs to metoda, za pomocą której aplikacje uwidaczniają metody i właściwości w taki sposób, że inne aplikacje, takie jak Visual Basic lub inne języki, mogą korzystać z funkcji aplikacji. Najważniejszym elementem tego interfejsu jest `IDispatch::Invoke` Funkcja. Do wdrożenia MFC są stosowane "mapy wysyłania" `IDispatch::Invoke` . Mapa wysyłania zawiera informacje o implementacji MFC dotyczące układu lub "kształtu" `CCmdTarget` klas pochodnych, dzięki czemu mogą bezpośrednio manipulować właściwościami obiektu lub wywoływać funkcje składowe w obiekcie, aby spełnić `IDispatch::Invoke` żądania.

W większości ClassWizard i MFC współpracują w celu ukrycia większości szczegółów automatyzacji OLE z programisty aplikacji. Programista koncentruje się na rzeczywistej funkcji ujawnianej w aplikacji i nie musi martwić się o podstawowe instalacje.

Istnieją jednak przypadki, w których trzeba zrozumieć, co MFC działa w tle. Ta uwaga dotyczy sposobu, w jaki struktura przypisuje identyfikator **DISPID** s do funkcji składowych i właściwości. Znajomość algorytmów używanych przez MFC do przypisywania **DISPID** s jest konieczna tylko wtedy, gdy trzeba znać identyfikatory, takie jak podczas tworzenia "biblioteki typów" dla obiektów aplikacji.

## <a name="mfc-dispid-assignment"></a>Przypisanie MFC DISPID

Mimo że użytkownik końcowy automatyzacji (na przykład Visual Basic użytkownik) widzi rzeczywiste nazwy właściwości i metod z włączonym automatyzacją w ich kodzie (takich jak obj). Funkcja ShowWindow), implementacja programu `IDispatch::Invoke` nie otrzymuje rzeczywistych nazw. Ze względu na optymalizację otrzymujemy identyfikator **DISPID**, który jest 32-bitowy "Magic cookie" opisujący metodę lub właściwość, do której ma być uzyskiwany dostęp. Te wartości **DISPID** są zwracane z `IDispatch` implementacji przez inną metodę o nazwie `IDispatch::GetIDsOfNames` . Aplikacja kliencka usługi Automation będzie wywoływała się `GetIDsOfNames` jednokrotnie dla każdego elementu członkowskiego lub właściwości, do którego ma dostęp, i buforuje je w celu późniejszego wywołania do `IDispatch::Invoke` . W ten sposób kosztowne wyszukiwanie ciągów jest wykonywane tylko raz dla każdego obiektu, a nie raz na `IDispatch::Invoke` wywołanie.

MFC określa identyfikator **DISPID** s dla każdej metody i właściwości na podstawie dwóch elementów:

- Odległość od góry mapy wysyłania (1 względna)

- Odległość mapy wysyłania od najbardziej pochodnej klasy (0 względnych)

Identyfikator **DISPID** jest podzielony na dwie części. **LOWORD** identyfikatora **DISPID** zawiera pierwszy składnik, odległość od góry mapy wysyłania. **HIWORD** zawiera odległość od klasy najbardziej pochodnej. Na przykład:

```cpp
class CDispPoint : public CCmdTarget
{
public:
    short m_x, m_y;
    // ...
    DECLARE_DISPATCH_MAP()
    // ...
};

class CDisp3DPoint : public CDispPoint
{
public:
    short m_z;
    // ...
    DECLARE_DISPATCH_MAP()
    // ...
};

BEGIN_DISPATCH_MAP(CDispPoint, CCmdTarget)
    DISP_PROPERTY(CDispPoint, "x", m_x, VT_I2)
    DISP_PROPERTY(CDispPoint, "y", m_y, VT_I2)
END_DISPATCH_MAP()

BEGIN_DISPATCH_MAP(CDisp3DPoint, CDispPoint)
    DISP_PROPERTY(CDisp3DPoint, "z", m_z, VT_I2)
END_DISPATCH_MAP()
```

Jak widać, istnieją dwie klasy, z których każdy uwidacznia interfejsy automatyzacji OLE. Jedna z tych klas pochodzi od drugiej i w ten sposób wykorzystuje funkcje klasy bazowej, w tym część automatyzacji OLE (w tym przypadku właściwości "x" i "y").

MFC będzie generować identyfikator **DISPID** s dla klasy CDispPoint w następujący sposób:

```cpp
property X    (DISPID)0x00000001
property Y    (DISPID)0x00000002
```

Ponieważ właściwości nie znajdują się w klasie bazowej, **HIWORD** **DISPID** ma zawsze wartość zero (odległość od klasy pochodnej dla CDispPoint jest równa zero).

MFC będzie generować identyfikator **DISPID** s dla klasy CDisp3DPoint w następujący sposób:

```cpp
property Z    (DISPID)0x00000001
property X    (DISPID)0x00010001
property Y    (DISPID)0x00010002
```

Właściwość Z jest przyznany identyfikatorem **DISPID** z zerem **HIWORD** , ponieważ jest on zdefiniowany w klasie, która uwidacznia właściwości, CDisp3DPoint. Ponieważ właściwości X i Y są zdefiniowane w klasie bazowej, **HIWORD** **DISPID** ma wartość 1, ponieważ Klasa, w której są zdefiniowane te właściwości, jest na odległość jednego wyprowadzenia od klasy najbardziej pochodnej.

> [!NOTE]
> **LOWORD** jest zawsze określana na podstawie położenia na mapie, nawet jeśli istnieją wpisy na mapie z jawnym identyfikatorem **DISPID** (zobacz następną sekcję, aby uzyskać informacje na temat wersji **_id** `DISP_PROPERTY` `DISP_FUNCTION` makr i).

## <a name="advanced-mfc-dispatch-map-features"></a>Zaawansowane funkcje mapy wysyłania MFC

Istnieje szereg dodatkowych funkcji, które nie są obsługiwane przez program ClassWizard w tej wersji Visual C++. ClassWizard obsługuje `DISP_FUNCTION` , `DISP_PROPERTY` , i, `DISP_PROPERTY_EX` który definiuje metodę, właściwość elementu członkowskiego i Pobiera/ustawia właściwość funkcji członkowskiej odpowiednio. Te funkcje są zwykle wszystkie, co jest konieczne do utworzenia większości serwerów automatyzacji.

Następujące dodatkowe makra mogą być używane, gdy obsługiwane makra ClassWizard są nieodpowiednie: `DISP_PROPERTY_NOTIFY` , i `DISP_PROPERTY_PARAM` .

## <a name="disp_property_notify--macro-description"></a>DISP_PROPERTY_NOTIFY — opis makra

```cpp
DISP_PROPERTY_NOTIFY(
    theClass,
    pszName,
    memberName,
    pfnAfterSet,
    vtPropType)
```

### <a name="parameters"></a>Parametry

*theClass*<br/>
Nazwa klasy.

*pszName*<br/>
Zewnętrzna nazwa właściwości.

*memberName*<br/>
Nazwa zmiennej członkowskiej, w której jest przechowywana właściwość.

*pfnAfterSet*<br/>
Nazwa funkcji składowej do wywołania, gdy właściwość zostanie zmieniona.

*vtPropType*<br/>
Wartość określająca typ właściwości.

### <a name="remarks"></a>Uwagi

To makro jest podobne do DISP_PROPERTY, z tą różnicą, że akceptuje dodatkowy argument. Dodatkowy argument, *pfnAfterSet,* powinien być funkcją składową, która zwraca wartość Nothing i nie przyjmuje żadnych parametrów, "void OnPropertyNotify ()". Zostanie on wywołany **po** zmodyfikowaniu zmiennej składowej.

## <a name="disp_property_param--macro-description"></a>DISP_PROPERTY_PARAM — opis makra

```cpp
DISP_PROPERTY_PARAM(
    theClass,
    pszName,
    pfnGet,
    pfnSet,
    vtPropType,
    vtsParams)
```

### <a name="parameters"></a>Parametry

*theClass*<br/>
Nazwa klasy.

*pszName*<br/>
Zewnętrzna nazwa właściwości.

*memberGet*<br/>
Nazwa funkcji składowej używanej do pobierania właściwości.

*memberSet*<br/>
Nazwa funkcji składowej używanej do ustawiania właściwości.

*vtPropType*<br/>
Wartość określająca typ właściwości.

*vtsParams*<br/>
Ciąg oddzielony VTS_ miejsca dla każdego parametru.

### <a name="remarks"></a>Uwagi

Podobnie jak makro DISP_PROPERTY_EX, to makro definiuje właściwość, do której można uzyskać dostęp za pomocą osobnych funkcji pobierania i ustawiania elementów członkowskich. To makro umożliwia jednak określenie listy parametrów dla właściwości. Jest to przydatne w przypadku implementowania właściwości, które są indeksowane lub sparametryzowane w inny sposób. Parametry zostaną zawsze umieszczone jako pierwsze, a następnie nowa wartość właściwości. Na przykład:

```cpp
DISP_PROPERTY_PARAM(CMyObject, "item", GetItem, SetItem, VT_DISPATCH, VTS_I2 VTS_I2)
```

będzie odpowiadać za pobieranie i Ustawianie funkcji Członkowskich:

```cpp
LPDISPATCH CMyObject::GetItem(short row, short col)
void CMyObject::SetItem(short row, short col, LPDISPATCH newValue)
```

## <a name="disp_xxxx_id--macro-descriptions"></a>DISP_XXXX_ID — opisy makr

```cpp
DISP_FUNCTION_ID(
    theClass,
    pszName,
    dispid,
    pfnMember,
    vtRetVal,
    vtsParams)
DISP_PROPERTY_ID(
    theClass,
    pszName,
    dispid,
    memberName,
    vtPropType)
DISP_PROPERTY_NOTIFY_ID(
    theClass,
    pszName,
    dispid,
    memberName,
    pfnAfterSet,
    vtPropType)
DISP_PROPERTY_EX_ID(
    theClass,
    pszName,
    dispid,
    pfnGet,
    pfnSet,
    vtPropType)
DISP_PROPERTY_PARAM_ID(
    theClass,
    pszName,
    dispid,
    pfnGet,
    pfnSet,
    vtPropType,
    vtsParams)
```

### <a name="parameters"></a>Parametry

*theClass*<br/>
Nazwa klasy.

*pszName*<br/>
Zewnętrzna nazwa właściwości.

*DISPID*<br/>
Stały identyfikator DISPID dla właściwości lub metody.

*pfnGet*<br/>
Nazwa funkcji składowej używanej do pobierania właściwości.

*pfnSet*<br/>
Nazwa funkcji składowej używanej do ustawiania właściwości.

*memberName*<br/>
Nazwa zmiennej składowej, która ma zostać zamapowana na Właściwość

*vtPropType*<br/>
Wartość określająca typ właściwości.

*vtsParams*<br/>
Ciąg oddzielony VTS_ miejsca dla każdego parametru.

### <a name="remarks"></a>Uwagi

Te makra pozwalają określić identyfikator **DISPID** zamiast zezwalać na automatyczne przypisywanie MFC. Te zaawansowane makra mają takie same nazwy, z wyjątkiem tego, że identyfikator jest dołączany do nazwy makra (np. **DISP_PROPERTY_ID**), a identyfikator jest określany przez określony parametr zaraz po parametrze *pszName* . Zobacz AFXDISP. H Aby uzyskać więcej informacji na temat tych makr. Wpisy **_id** muszą być umieszczone na końcu mapy wysyłania. Wpłyną one na automatyczne generowanie identyfikatora **DISPID** w taki sam sposób jak w przypadku **nie_ID** wersji makra (identyfikator **DISPID** s jest określany przez pozycję). Na przykład:

```cpp
BEGIN_DISPATCH_MAP(CDisp3DPoint, CCmdTarget)
    DISP_PROPERTY(CDisp3DPoint, "y", m_y, VT_I2)
    DISP_PROPERTY(CDisp3DPoint, "z", m_z, VT_I2)
    DISP_PROPERTY_ID(CDisp3DPoint, "x", 0x00020003, m_x, VT_I2)
END_DISPATCH_MAP()
```

MFC będzie generować identyfikatory SPID dla klasy CDisp3DPoint w następujący sposób:

```cpp
property X    (DISPID)0x00020003
property Y    (DISPID)0x00000002
property Z    (DISPID)0x00000001
```

Określenie ustalonego identyfikatora **DISPID** jest przydatne w celu zachowania zgodności z poprzednimi wersjami z wcześniej istniejącym interfejsem wysyłania lub zaimplementowania określonych metod lub właściwości zdefiniowanych przez system (zwykle jest to spowodowane przez ujemną **DISPID**, na przykład kolekcję **DISPID_NEWENUM** ).

## <a name="retrieving-the-idispatch-interface-for-a-coleclientitem"></a>Pobieranie interfejsu IDispatch dla elementu COleClientItem

Wiele serwerów będzie obsługiwać automatyzację w obrębie obiektów dokumentów wraz z funkcjonalnością serwera OLE. Aby uzyskać dostęp do tego interfejsu automatyzacji, należy bezpośrednio uzyskać dostęp do `COleClientItem::m_lpObject` zmiennej składowej. Poniższy kod spowoduje pobranie `IDispatch` interfejsu dla obiektu pochodnego od `COleClientItem` . Możesz uwzględnić Poniższy kod w aplikacji, jeśli okaże się to konieczne:

```cpp
LPDISPATCH CMyClientItem::GetIDispatch()
{
    ASSERT_VALID(this);
    ASSERT(m_lpObject != NULL);

    LPUNKNOWN lpUnk = m_lpObject;

    Run();      // must be running

    LPOLELINK lpOleLink = NULL;
    if (m_lpObject->QueryInterface(IID_IOleLink,
        (LPVOID FAR*)&lpOleLink) == NOERROR)
    {
        ASSERT(lpOleLink != NULL);
        lpUnk = NULL;
        if (lpOleLink->GetBoundSource(&lpUnk) != NOERROR)
        {
            TRACE0("Warning: Link is not connected!\n");
            lpOleLink->Release();
            return NULL;
        }
        ASSERT(lpUnk != NULL);
    }

    LPDISPATCH lpDispatch = NULL;
    if (lpUnk->QueryInterface(IID_IDispatch, &lpDispatch) != NOERROR)
    {
        TRACE0("Warning: does not support IDispatch!\n");
        return NULL;
    }

    ASSERT(lpDispatch != NULL);
    return lpDispatch;
}
```

Interfejs wysyłania zwrócony z tej funkcji może zostać użyty bezpośrednio lub dołączony do `COleDispatchDriver` typu w celu bezpiecznego dostępu do typów. Jeśli używasz go bezpośrednio, upewnij się, że wywołujesz jego `Release` składową, gdy za pomocą wskaźnika ( `COleDispatchDriver` destruktor domyślnie robi to).

## <a name="see-also"></a>Zobacz też

[Uwagi techniczne według numeru](../mfc/technical-notes-by-number.md)<br/>
[Uwagi techniczne według kategorii](../mfc/technical-notes-by-category.md)
