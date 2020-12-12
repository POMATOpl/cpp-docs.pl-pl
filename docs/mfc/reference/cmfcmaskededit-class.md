---
description: 'Dowiedz się więcej na temat: Klasa CMFCMaskedEdit'
title: Klasa CMFCMaskedEdit
ms.date: 11/04/2016
f1_keywords:
- CMFCMaskedEdit
- AFXMASKEDEDIT/CMFCMaskedEdit
- AFXMASKEDEDIT/CMFCMaskedEdit::DisableMask
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableGetMaskedCharsOnly
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableMask
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableSelectByGroup
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableSetMaskedCharsOnly
- AFXMASKEDEDIT/CMFCMaskedEdit::GetWindowText
- AFXMASKEDEDIT/CMFCMaskedEdit::SetValidChars
- AFXMASKEDEDIT/CMFCMaskedEdit::SetWindowText
- AFXMASKEDEDIT/CMFCMaskedEdit::IsMaskedChar
helpviewer_keywords:
- CMFCMaskedEdit [MFC], DisableMask
- CMFCMaskedEdit [MFC], EnableGetMaskedCharsOnly
- CMFCMaskedEdit [MFC], EnableMask
- CMFCMaskedEdit [MFC], EnableSelectByGroup
- CMFCMaskedEdit [MFC], EnableSetMaskedCharsOnly
- CMFCMaskedEdit [MFC], GetWindowText
- CMFCMaskedEdit [MFC], SetValidChars
- CMFCMaskedEdit [MFC], SetWindowText
- CMFCMaskedEdit [MFC], IsMaskedChar
ms.assetid: 13b1a645-2d5d-4c37-8599-16d5003f23a5
ms.openlocfilehash: 7ac61240e2941eafbbac3cbb03a4884e282cbca3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265158"
---
# <a name="cmfcmaskededit-class"></a>Klasa CMFCMaskedEdit

`CMFCMaskedEdit`Klasa obsługuje kontrolkę edycji zamaskowanej, która sprawdza poprawność danych wejściowych użytkownika względem maski i wyświetla sprawdzone wyniki zgodnie z szablonem.

## <a name="syntax"></a>Składnia

```
class CMFCMaskedEdit : public CEdit
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|`CMFCMaskedEdit::CMFCMaskedEdit`|Konstruktor domyślny.|
|`CMFCMaskedEdit::~CMFCMaskedEdit`|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCMaskedEdit::D isableMask](#disablemask)|Wyłącza sprawdzanie poprawności danych wejściowych użytkownika.|
|[CMFCMaskedEdit::EnableGetMaskedCharsOnly](#enablegetmaskedcharsonly)|Określa, czy `GetWindowText` Metoda pobiera tylko znaki maskowane.|
|[CMFCMaskedEdit::EnableMask](#enablemask)|Inicjuje formant zamaskowanej edycji.|
|[CMFCMaskedEdit::EnableSelectByGroup](#enableselectbygroup)|Określa, czy zamaskowane kontrolka edycji wybiera określone grupy danych wejściowych użytkownika lub wszystkie dane wejściowe użytkownika.|
|[CMFCMaskedEdit::EnableSetMaskedCharsOnly](#enablesetmaskedcharsonly)|Określa, czy tekst jest weryfikowany tylko w przypadku znaków zamaskowanych, czy też do całej maski.|
|`CMFCMaskedEdit::GetThisClass`|Używane przez platformę do uzyskania wskaźnika do obiektu [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) , który jest skojarzony z tym typem klasy.|
|[CMFCMaskedEdit::GetWindowText](#getwindowtext)|Pobiera zweryfikowany tekst z zamaskowanej kontrolki edycji.|
|[CMFCMaskedEdit::SetValidChars](#setvalidchars)|Określa ciąg prawidłowych znaków, które użytkownik może wprowadzić.|
|[CMFCMaskedEdit::SetWindowText](#setwindowtext)|Wyświetla monit w kontrolce zamaskowanej edycji.|

### <a name="protected-methods"></a>Metody chronione

|Nazwa|Opis|
|----------|-----------------|
|[CMFCMaskedEdit::IsMaskedChar](#ismaskedchar)|Wywoływane przez platformę, by sprawdzić poprawność określonego znaku względem odpowiedniego znaku maski.|

## <a name="remarks"></a>Uwagi

Wykonaj następujące kroki, aby użyć `CMFCMaskedEdit` kontrolki w aplikacji:

1. Osadź `CMFCMaskedEdit` obiekt w klasie okna.

2. Wywołaj metodę [CMFCMaskedEdit:: EnableMask](#enablemask) , aby określić maskę.

3. Wywołaj metodę [CMFCMaskedEdit:: SetValidChars](#setvalidchars) , aby określić listę prawidłowych znaków.

4. Wywołaj metodę [CMFCMaskedEdit:: SetWindowText](#setwindowtext) , aby określić domyślny tekst dla kontrolki edycji maskowanej.

5. Wywołaj metodę [CMFCMaskedEdit:: GetWindowText](#getwindowtext) w celu pobrania zweryfikowanego tekstu.

Jeśli nie wywołasz co najmniej jednej metody w celu zainicjowania maski, prawidłowych znaków i tekstu domyślnego, zamaskowane kontrolka edycji zachowuje się tak samo, jak zachowanie standardowej kontrolki edycji.

## <a name="example"></a>Przykład

W poniższym przykładzie pokazano, jak skonfigurować maskę (na przykład numer telefonu) przy użyciu `EnableMask` metody, aby utworzyć maskę dla formantu zamaskowanej edycji, `SetValidChars` metodę określającą ciąg prawidłowych znaków, które użytkownik może wprowadzić, oraz `SetWindowText` metodę wyświetlania monitu w kontrolce zamaskowanej edycji. Ten przykład jest częścią [nowych kontrolek](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#11](../../mfc/reference/codesnippet/cpp/cmfcmaskededit-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#12](../../mfc/reference/codesnippet/cpp/cmfcmaskededit-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

[CMFCMaskedEdit](../../mfc/reference/cmfcmaskededit-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxmaskededit. h

## <a name="cmfcmaskededitdisablemask"></a><a name="disablemask"></a> CMFCMaskedEdit::D isableMask

Wyłącza sprawdzanie poprawności danych wejściowych użytkownika.

```cpp
void DisableMask();
```

### <a name="remarks"></a>Uwagi

Jeśli sprawdzanie poprawności danych wejściowych użytkownika jest wyłączone, zamaskowane kontrolka edycji zachowuje się jak standardowa kontrolka edycji.

## <a name="cmfcmaskededitenablegetmaskedcharsonly"></a><a name="enablegetmaskedcharsonly"></a> CMFCMaskedEdit::EnableGetMaskedCharsOnly

Określa, czy `GetWindowText` Metoda pobiera tylko znaki maskowane.

```cpp
void EnableGetMaskedCharsOnly(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametry

*bEnable*<br/>
podczas Wartość TRUE, aby określić, że metoda [CMFCMaskedEdit:: GetWindowText](#getwindowtext) pobiera tylko znaki maskowane; Wartość FALSE, aby określić, że metoda pobiera cały tekst. Wartość domyślna to TRUE.

### <a name="remarks"></a>Uwagi

Użyj tej metody, aby włączyć pobieranie maskowanych znaków. Następnie utwórz kontrolkę z maską edycji, która odpowiada numerowi telefonu, na przykład (425) 555-0187. Wywołanie `GetWindowText` metody powoduje zwrócenie "4255550187". Jeśli wyłączysz opcję Pobieranie znaków maskowanych, `GetWindowText` Metoda zwróci tekst wyświetlany w kontrolce edycji, na przykład "(425) 555-0187".

## <a name="cmfcmaskededitenablemask"></a><a name="enablemask"></a> CMFCMaskedEdit::EnableMask

Inicjuje formant zamaskowanej edycji.

```cpp
void EnableMask(
    LPCTSTR lpszMask,
    LPCTSTR lpszInputTemplate,
    TCHAR chMaskInputTemplate=_T('_'),
    LPCTSTR lpszValid=NULL);
```

### <a name="parameters"></a>Parametry

*lpszMask*<br/>
podczas Ciąg maski, który określa typ znaku, który może być wyświetlany w każdej pozycji w danych wejściowych użytkownika. Długość ciągów parametrów *lpszInputTemplate* i *lpszMask* musi być taka sama. Zobacz sekcję Uwagi, aby uzyskać szczegółowe informacje o znakach maski.

*lpszInputTemplate*<br/>
podczas Ciąg szablonu maski, który określa znaki literału, które mogą być wyświetlane w każdej pozycji w danych wejściowych użytkownika. Użyj znaku podkreślenia ("_") jako symbolu zastępczego znaku. Długość ciągów parametrów *lpszInputTemplate* i *lpszMask* musi być taka sama.

*chMaskInputTemplate*<br/>
podczas Domyślny znak, który jest zastępowany przez środowisko dla każdego nieprawidłowego znaku w danych wejściowych użytkownika. Wartość domyślna tego parametru to podkreślenie ("_").

*lpszValid*<br/>
podczas Ciąg, który zawiera zestaw prawidłowych znaków. Wartość NULL wskazuje, że wszystkie znaki są prawidłowe. Wartość domyślna tego parametru ma wartość NULL.

### <a name="remarks"></a>Uwagi

Użyj tej metody, aby utworzyć maskę dla formantu zamaskowanej edycji. Utwórz klasę z `CMFCMaskedEdit` klasy i Zastąp metodę [CMFCMaskedEdit:: IsMaskedChar](#ismaskedchar) , aby użyć własnego kodu do niestandardowego przetwarzania maski.

W poniższej tabeli wymieniono domyślne znaki maski:

|Znak maski|Definicja|
|--------------------|----------------|
|D|Kontrol.|
|d|Cyfra lub spacja.|
|+|Znak plus ("+"), znak minus ("-") lub spacja.|
|C|Znak alfanumeryczny.|
|c|Znak alfabetyczny lub spacja.|
|A|Znak alfanumeryczny.|
|a|Znak alfanumeryczny lub spacja.|
|*|Znak drukowalny.|

## <a name="cmfcmaskededitenableselectbygroup"></a><a name="enableselectbygroup"></a> CMFCMaskedEdit::EnableSelectByGroup

Określa, czy zamaskowane kontrolka edycji zezwala użytkownikowi na wybór określonych grup lub wszystkich danych wejściowych.

```cpp
void EnableSelectByGroup(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametry

*bEnable*<br/>
podczas PRAWDA, aby wybrać tylko grupy; Wartość FALSE, aby zaznaczyć cały tekst. Wartość domyślna to TRUE.

### <a name="remarks"></a>Uwagi

Użyj tej funkcji, aby określić, czy kontrolka edycji zamaskowanej umożliwia użytkownikowi Zaznaczanie według grupy, czy całego tekstu.

Domyślnie Zaznaczanie według grupy jest włączone. W takim przypadku użytkownik może wybrać tylko ciągłe grupy prawidłowych znaków.

Na przykład można użyć poniższej kontrolki zamaskowanej edycji do zweryfikowania numeru telefonu:

```cpp
m_wndMaskEdit.EnableMask(
    _T(" ddd  ddd dddd"),  // Mask string
    _T("(___) ___-____"),  // Template string
    _T(' '));              // Default char

m_wndMaskEdit.SetValidChars(NULL); // All characters are valid.

m_wndMaskEdit.SetWindowText(_T("(425) 555-0187")); // Prompt
```

Jeśli włączono opcję Zaznacz według grupy, użytkownik może pobrać tylko grupy ciągów "425", "555" lub "0187". Jeśli wybór grupy jest wyłączony, użytkownik może pobrać cały tekst numeru telefonu: "(425) 555-0187".

## <a name="cmfcmaskededitenablesetmaskedcharsonly"></a><a name="enablesetmaskedcharsonly"></a> CMFCMaskedEdit::EnableSetMaskedCharsOnly

Określa, czy tekst jest weryfikowany tylko dla znaków maskowanych, czy też do całej maski.

```cpp
void EnableSetMaskedCharsOnly(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametry

*bEnable*<br/>
podczas TRUE, aby sprawdzić poprawność danych wejściowych użytkownika tylko do maskowanych znaków; Wartość FALSE, aby sprawdzić poprawność względem całej maski. Wartość domyślna to TRUE.

## <a name="cmfcmaskededitgetwindowtext"></a><a name="getwindowtext"></a> CMFCMaskedEdit::GetWindowText

Pobiera zweryfikowany tekst z zamaskowanej kontrolki edycji.

```
int GetWindowText(
    LPTSTR lpszStringBuf,
    int nMaxCount) const;

void GetWindowText(CString& rstrString) const;
```

### <a name="parameters"></a>Parametry

*lpszStringBuf*<br/>
określoną Wskaźnik do buforu, który odbiera tekst z kontrolki edycji.

*nMaxCount*<br/>
podczas Maksymalna liczba znaków do odebrania.

*rstrString*<br/>
określoną Odwołanie do obiektu String, który odbiera tekst z kontrolki edycji.

### <a name="return-value"></a>Wartość zwracana

Pierwsze Przeciążenie metody zwraca liczbę bajtów ciągu, który jest kopiowany do buforu parametru *lpszStringBuf* ; 0, jeśli zamaskowane kontrolka edycji nie ma tekstu.

### <a name="remarks"></a>Uwagi

Ta metoda kopiuje tekst z zamaskowanej kontrolki edycji do buforu *lpszStringBuf* lub *rstrString* .

Ta metoda ponownie definiuje [CWnd:: GetWindowText](../../mfc/reference/cwnd-class.md#getwindowtext).

## <a name="cmfcmaskededitismaskedchar"></a><a name="ismaskedchar"></a> CMFCMaskedEdit::IsMaskedChar

Wywoływane przez platformę, by sprawdzić poprawność określonego znaku względem odpowiedniego znaku maski.

```
virtual BOOL IsMaskedChar(
    TCHAR chChar,
    TCHAR chMaskChar) const;
```

### <a name="parameters"></a>Parametry

*chChar*<br/>
podczas Znak do zweryfikowania.

*chMaskChar*<br/>
podczas Odpowiedni znak z ciągu maski.

### <a name="return-value"></a>Wartość zwracana

TRUE, jeśli parametr *chChar* jest typem znaku dozwolonym przez parametr *chMaskChar* ; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Zastąp tę metodę, aby sprawdzić poprawność znaków wejściowych. Aby uzyskać więcej informacji na temat masek, zobacz metodę [CMFCMaskedEdit:: EnableMask](#enablemask) .

## <a name="cmfcmaskededitsetvalidchars"></a><a name="setvalidchars"></a> CMFCMaskedEdit::SetValidChars

Określa ciąg prawidłowych znaków, które użytkownik może wprowadzić.

```cpp
void SetValidChars(LPCTSTR lpszValid=NULL);
```

### <a name="parameters"></a>Parametry

*lpszValid*<br/>
podczas Ciąg, który zawiera zestaw prawidłowych znaków wejściowych. Wartość zerowa oznacza, że wszystkie znaki są prawidłowe. Wartość domyślna tego parametru ma wartość NULL.

### <a name="remarks"></a>Uwagi

Użyj tej metody, aby zdefiniować listę prawidłowych znaków. Jeśli na liście nie ma znaku wejściowego, zamaskowanie kontrolki edycji nie zostanie zaakceptowane.

Poniższy przykład kodu akceptuje tylko cyfry szesnastkowe.

```cpp
//Mask: 0xFFFF
m_wndMaskEdit.EnableMask(
    _T(" AAAA"),                // The mask string.
    _T("0x____"),               // The literal template string.
    _T('_'));                   // The default character that
                                // replaces the backspace character.
// Valid string characters
m_wndMaskEdit.SetValidChars(_T("1234567890ABCDEFabcdef"));m_wndMaskEdit.SetWindowText(_T("0x01AF"));
```

## <a name="cmfcmaskededitsetwindowtext"></a><a name="setwindowtext"></a> CMFCMaskedEdit::SetWindowText

Wyświetla monit w kontrolce zamaskowanej edycji.

```cpp
void SetWindowText(LPCTSTR lpszString);
```

### <a name="parameters"></a>Parametry

*lpszString*<br/>
podczas Wskazuje ciąg zakończony znakiem null, który będzie używany jako monit.

### <a name="remarks"></a>Uwagi

Ta metoda ustawia tekst kontrolki.

Ta metoda ponownie definiuje [CWnd:: SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext).

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CEdit](../../mfc/reference/cedit-class.md)
