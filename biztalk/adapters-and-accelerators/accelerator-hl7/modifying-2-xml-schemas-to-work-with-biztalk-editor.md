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
# <a name="modifying-2xml-schemas-to-work-with-biztalk-editor"></a><span data-ttu-id="f3588-102">BizTalk エディターを使用する 2.xml スキーマの変更</span><span class="sxs-lookup"><span data-stu-id="f3588-102">Modifying 2.XML Schemas to Work with BizTalk Editor</span></span>
<span data-ttu-id="f3588-103">HL7 2. XML スキーマが正しく連動させる Microsoft BizTalk Accelerator for HL7 の変更が必要です ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="f3588-103">HL7 2.XML schemas require modification to work properly with Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]).</span></span> <span data-ttu-id="f3588-104">次に、HL7 V2 を変更する方法について説明します。BizTalk エディターを使用して使用することを有効にする XML スキーマです。</span><span class="sxs-lookup"><span data-stu-id="f3588-104">The following describes how to modify HL7 V2.XML schemas to enable you to use them with BizTalk Editor.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f3588-105">Update2XMLSchema ツールでは、次の手順が自動的に実行します。</span><span class="sxs-lookup"><span data-stu-id="f3588-105">The Update2XMLSchema tool performs these steps automatically.</span></span> <span data-ttu-id="f3588-106">参照してください[Update2XMLSchema ツール](../../adapters-and-accelerators/accelerator-hl7/update2xmlschema-tool.md)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="f3588-106">See [Update2XMLSchema Tool](../../adapters-and-accelerators/accelerator-hl7/update2xmlschema-tool.md) for more information.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="f3588-107">**Nillable**属性が要素上のスキーマで発生することができます。</span><span class="sxs-lookup"><span data-stu-id="f3588-107">The **nillable** attribute can occur in a schema on an element.</span></span> <span data-ttu-id="f3588-108">場合に設定**true**、親要素のインスタンスを持つことができることを示します、 **xsi:nil ="true"** 属性。</span><span class="sxs-lookup"><span data-stu-id="f3588-108">If set to **true**, it indicates that the instance of the parent element can have an **xsi:nil="true"** attribute.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="f3588-109"> 解析とシリアル化中に、コンパイル中に、この属性は無視されます。</span><span class="sxs-lookup"><span data-stu-id="f3588-109"> ignores this attribute during compilation and during parsing/serialization.</span></span>  
  
### <a name="to-modify-2xml-schemas"></a><span data-ttu-id="f3588-110">2. XML スキーマを変更するには</span><span class="sxs-lookup"><span data-stu-id="f3588-110">To modify 2.XML schemas</span></span>  
  
1. <span data-ttu-id="f3588-111">Fields.xsd ファイル内のインスタンスを削除する必要があります**インポート**に置き換えます**含める**します。</span><span class="sxs-lookup"><span data-stu-id="f3588-111">In the fields.xsd file, you must remove instances of **import** and replace them with **include**.</span></span> <span data-ttu-id="f3588-112">たとえば、次のテキストを fields.xsd ファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="f3588-112">For example, search the fields.xsd file for the following text:</span></span>  
  
   ```  
   <xsd:import namespace="urn:hl7-org:v2xml" schemaLocation="datatypes.xsd"/>   
   ```  
  
    <span data-ttu-id="f3588-113">次のテキストを変更します。</span><span class="sxs-lookup"><span data-stu-id="f3588-113">And change the text to the following:</span></span>  
  
   ```  
   <xsd:include schemaLocation="datatypes.xsd"/>   
   ```  
  
2. <span data-ttu-id="f3588-114">Segments.xsd ファイルでは、テキスト データが含まれている行のすべてのインスタンスを削除する必要があります [lax] =。</span><span class="sxs-lookup"><span data-stu-id="f3588-114">In the segments.xsd file, you must remove all instances of the lines that contain the text processContents="lax".</span></span> <span data-ttu-id="f3588-115">たとえば、次のテキストを segments.xsd ファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="f3588-115">For example, search the segments.xsd file for the following text:</span></span>  
  
   ```  
   <xsd:any processContents="lax" namespace="##any" minOccurs="0"/>   
   ```  
  
    <span data-ttu-id="f3588-116">And</span><span class="sxs-lookup"><span data-stu-id="f3588-116">And</span></span>  
  
   ```  
   <xsd:any processContents="lax" namespace="##any"/>   
   ```  
  
    <span data-ttu-id="f3588-117">これらの行を削除します。</span><span class="sxs-lookup"><span data-stu-id="f3588-117">And remove those lines.</span></span>  
  
3. <span data-ttu-id="f3588-118">タグ xsd:schema、下のすべてのスキーマには、次の行を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3588-118">For all schemas, under the tag xsd:schema, you must add the following line:</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="f3588-119">Microsoft を使用してスキーマを追加した場合、この行を入れないでください[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ため[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]が自動的にします。</span><span class="sxs-lookup"><span data-stu-id="f3588-119">Do not add this line if you have added the schema using Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] because [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] does this for you automatically.</span></span>  
  
   ```  
   xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
   ```  
  
    <span data-ttu-id="f3588-120">たとえば、ADT_A01.xsd ファイルで、次のテキストの検索します。</span><span class="sxs-lookup"><span data-stu-id="f3588-120">For example, in the file ADT_A01.xsd, search for the following text:</span></span>  
  
   ```  
   <xsd:schema  
    xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
    xmlns="urn:hl7-org:v2xml"   
    targetNamespace="urn:hl7-org:v2xml">   
   ```  
  
    <span data-ttu-id="f3588-121">次のテキストを変更します。</span><span class="sxs-lookup"><span data-stu-id="f3588-121">And change the text to the following:</span></span>  
  
   ```  
   <xsd:schema  
    xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
    xmlns="urn:hl7-org:v2xml"  
    targetNamespace="urn:hl7-org:v2xml"  
    xmlns:b="http://schemas.microsoft.com/BizTalk/2003">   
   ```  
  
4. <span data-ttu-id="f3588-122">すべてのスキーマのルートの参照を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3588-122">For all schemas, you must add a root reference.</span></span> <span data-ttu-id="f3588-123">たとえば、ADT_A01.xsd ファイルで次のテキストを検索します。</span><span class="sxs-lookup"><span data-stu-id="f3588-123">For example, in the ADT_A01.xsd file, search for the following text:</span></span>  
  
   ```  
   <xsd:include schemaLocation="segments.xsd" />   
   ```  
  
    <span data-ttu-id="f3588-124">テキストを変更します。</span><span class="sxs-lookup"><span data-stu-id="f3588-124">And change the text to:</span></span>  
  
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
   >  <span data-ttu-id="f3588-125">使用する場合[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、次の手順を使用してこの root_reference を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="f3588-125">If you are using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], you can add this root_reference by using the following procedure.</span></span>  
  
### <a name="to-add-the-root-reference"></a><span data-ttu-id="f3588-126">ルートの参照を追加するには</span><span class="sxs-lookup"><span data-stu-id="f3588-126">To add the root reference</span></span>  
  
1.  <span data-ttu-id="f3588-127">ソリューション エクスプ ローラーで、編集するスキーマをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="f3588-127">In Solution Explorer, double-click the schema you want to edit.</span></span>  
  
2.  <span data-ttu-id="f3588-128">プロパティまで下にスクロールのプロパティ ウィンドウで**root_reference**、ドロップダウン リストから、同じスキーマ名のプロパティをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f3588-128">In the Properties pane, scroll down to the property **root_reference**, and from the drop-down list, click the property with the same schema name.</span></span>  
  
3.  <span data-ttu-id="f3588-129">**[ファイル]** メニューの **[すべてを保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f3588-129">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3588-130">参照</span><span class="sxs-lookup"><span data-stu-id="f3588-130">See Also</span></span>  
 [<span data-ttu-id="f3588-131">HL7 2. XML スキーマの使用</span><span class="sxs-lookup"><span data-stu-id="f3588-131">Using HL7 2.XML Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)