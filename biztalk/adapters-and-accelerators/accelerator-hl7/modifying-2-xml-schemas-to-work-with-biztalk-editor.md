---
title: BizTalk エディターで作業する 2. XML スキーマを変更する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- 2.XML schemas, modifying
- modifying, 2.XML schemas
ms.assetid: 07316826-84b6-494e-81b9-f64a3d46ffb0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf68f39e4e4c36587b889490b28541e5a690ed05
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206106"
---
# <a name="modifying-2xml-schemas-to-work-with-biztalk-editor"></a>BizTalk エディターを使用する 2. XML スキーマを変更します。
HL7 2. XML スキーマで適切に機能を変更する必要[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])。 次に、HL7 V2 を変更する方法について説明します。有効にして、BizTalk エディターを使用する XML スキーマです。  
  
> [!IMPORTANT]
>  Update2XMLSchema ツールでは、自動的にこれらの手順を実行します。 参照してください[Update2XMLSchema ツール](../../adapters-and-accelerators/accelerator-hl7/update2xmlschema-tool.md)詳細についてはします。  
  
> [!NOTE]
>  **Nillable**属性が要素上のスキーマで発生することができます。 場合設定**true**、親要素のインスタンスを持つことができることを示します、 **xsi:nil ="true"** 属性。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]コンパイル時と解析とシリアル化中には、この属性を無視します。  
  
### <a name="to-modify-2xml-schemas"></a>2. XML スキーマを変更するには  
  
1.  Fields.xsd ファイル内のインスタンスを削除する必要があります**インポート**に置き換え、**含める**です。 たとえば、次のテキストを fields.xsd ファイルを検索します。  
  
    ```  
    <xsd:import namespace="urn:hl7-org:v2xml" schemaLocation="datatypes.xsd"/>   
    ```  
  
     テキストを次に変更します。  
  
    ```  
    <xsd:include schemaLocation="datatypes.xsd"/>   
    ```  
  
2.  Segments.xsd ファイルでは、テキスト データを含む行のすべてのインスタンスを削除する必要があります [lax] = です。 たとえば、次のテキストを segments.xsd ファイルを検索します。  
  
    ```  
    <xsd:any processContents="lax" namespace="##any" minOccurs="0"/>   
    ```  
  
     And  
  
    ```  
    <xsd:any processContents="lax" namespace="##any"/>   
    ```  
  
     それらの行を削除します。  
  
3.  タグ xsd:schema 下のすべてのスキーマには、次の行を追加する必要があります。  
  
    > [!NOTE]
    >  使用してスキーマを追加している場合は、この行を追加しないでください[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ため[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]が代わりに自動的にします。  
  
    ```  
    xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
    ```  
  
     たとえば、ADT_A01.xsd ファイルで次のテキストを検索します。  
  
    ```  
    <xsd:schema  
     xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
     xmlns="urn:hl7-org:v2xml"   
     targetNamespace="urn:hl7-org:v2xml">   
    ```  
  
     テキストを次に変更します。  
  
    ```  
    <xsd:schema  
     xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
     xmlns="urn:hl7-org:v2xml"  
     targetNamespace="urn:hl7-org:v2xml"  
     xmlns:b="http://schemas.microsoft.com/BizTalk/2003">   
    ```  
  
4.  すべてのスキーマのルート参照を追加する必要があります。 たとえば、ADT_A01.xsd ファイルに次のテキストを検索します。  
  
    ```  
    <xsd:include schemaLocation="segments.xsd" />   
    ```  
  
     テキストを変更します。  
  
    ```  
    <xsd:include schemaLocation="segments.xsd" />  
    <xsd:annotation>   
      <xsd:appinfo>   
        <schemaInfo root_reference="ADT_A01"  
     xmlns="http://schemas.microsoft.com/BizTalk/2003" />   
      </xsd:appinfo>   
    </xsd:annotation>   
    ```  
  
    > [!NOTE]
    >  使用している場合[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、次の手順を使用してこの root_reference を追加することができます。  
  
### <a name="to-add-the-root-reference"></a>ルート参照を追加するには  
  
1.  ソリューション エクスプ ローラーで、編集するスキーマをダブルクリックします。  
  
2.  プロパティまで下にスクロール プロパティ ウィンドウで、 **root_reference**、し、ドロップダウン リストから、同じスキーマ名のプロパティをクリックします。  
  
3.  **[ファイル]** メニューの **[すべてを保存]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [HL7 2. XML スキーマを使用します。](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)