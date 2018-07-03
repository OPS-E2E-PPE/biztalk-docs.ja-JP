---
title: BizTalk エディターで作業する 2.xml スキーマの変更 |Microsoft Docs
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
ms.openlocfilehash: 96dd1c4cd8909564ff39c78b5b1a9e4fc248d93f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972859"
---
# <a name="modifying-2xml-schemas-to-work-with-biztalk-editor"></a>BizTalk エディターを使用する 2.xml スキーマの変更
HL7 2. XML スキーマが正しく連動させる Microsoft BizTalk Accelerator for HL7 の変更が必要です ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])。 次に、HL7 V2 を変更する方法について説明します。BizTalk エディターを使用して使用することを有効にする XML スキーマです。  
  
> [!IMPORTANT]
>  Update2XMLSchema ツールでは、次の手順が自動的に実行します。 参照してください[Update2XMLSchema ツール](../../adapters-and-accelerators/accelerator-hl7/update2xmlschema-tool.md)詳細についてはします。  
> 
> [!NOTE]
>  **Nillable**属性が要素上のスキーマで発生することができます。 場合に設定**true**、親要素のインスタンスを持つことができることを示します、 **xsi:nil ="true"** 属性。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 解析とシリアル化中に、コンパイル中に、この属性は無視されます。  
  
### <a name="to-modify-2xml-schemas"></a>2. XML スキーマを変更するには  
  
1. Fields.xsd ファイル内のインスタンスを削除する必要があります**インポート**に置き換えます**含める**します。 たとえば、次のテキストを fields.xsd ファイルを検索します。  
  
   ```  
   <xsd:import namespace="urn:hl7-org:v2xml" schemaLocation="datatypes.xsd"/>   
   ```  
  
    次のテキストを変更します。  
  
   ```  
   <xsd:include schemaLocation="datatypes.xsd"/>   
   ```  
  
2. Segments.xsd ファイルでは、テキスト データが含まれている行のすべてのインスタンスを削除する必要があります [lax] =。 たとえば、次のテキストを segments.xsd ファイルを検索します。  
  
   ```  
   <xsd:any processContents="lax" namespace="##any" minOccurs="0"/>   
   ```  
  
    And  
  
   ```  
   <xsd:any processContents="lax" namespace="##any"/>   
   ```  
  
    これらの行を削除します。  
  
3. タグ xsd:schema、下のすべてのスキーマには、次の行を追加する必要があります。  
  
   > [!NOTE]
   >  Microsoft を使用してスキーマを追加した場合、この行を入れないでください[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ため[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]が自動的にします。  
  
   ```  
   xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
   ```  
  
    たとえば、ADT_A01.xsd ファイルで、次のテキストの検索します。  
  
   ```  
   <xsd:schema  
    xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
    xmlns="urn:hl7-org:v2xml"   
    targetNamespace="urn:hl7-org:v2xml">   
   ```  
  
    次のテキストを変更します。  
  
   ```  
   <xsd:schema  
    xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
    xmlns="urn:hl7-org:v2xml"  
    targetNamespace="urn:hl7-org:v2xml"  
    xmlns:b="http://schemas.microsoft.com/BizTalk/2003">   
   ```  
  
4. すべてのスキーマのルートの参照を追加する必要があります。 たとえば、ADT_A01.xsd ファイルで次のテキストを検索します。  
  
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
   >  使用する場合[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、次の手順を使用してこの root_reference を追加することができます。  
  
### <a name="to-add-the-root-reference"></a>ルートの参照を追加するには  
  
1.  ソリューション エクスプ ローラーで、編集するスキーマをダブルクリックします。  
  
2.  プロパティまで下にスクロールのプロパティ ウィンドウで**root_reference**、ドロップダウン リストから、同じスキーマ名のプロパティをクリックします。  
  
3.  **[ファイル]** メニューの **[すべてを保存]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [HL7 2. XML スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)