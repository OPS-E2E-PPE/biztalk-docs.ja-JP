---
title: 参照 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b916c55a-c84c-4008-8927-f8e584c36fe9
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 820e4f77da27a1dd934c1a1b842615c9b60158ad
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398014"
---
# <a name="reference"></a><span data-ttu-id="e28f9-102">リファレンス</span><span class="sxs-lookup"><span data-stu-id="e28f9-102">Reference</span></span>
<span data-ttu-id="e28f9-103">**参照**要素を使用して、BAM アクティビティに 1 つまたは複数のリレーションシップを追加します。</span><span class="sxs-lookup"><span data-stu-id="e28f9-103">The **Reference** element can be used to add one or more relationships to a BAM activity.</span></span> <span data-ttu-id="e28f9-104">これは、主キー、ID、または URL のようなポインターを関連するメッセージに添付する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="e28f9-104">This is useful when you want to attach a pointer like a primary key, ID, or URL to a related message.</span></span> <span data-ttu-id="e28f9-105">たとえば、発注アクティビティで出荷バッチへの参照を格納する場合があります。</span><span class="sxs-lookup"><span data-stu-id="e28f9-105">For example, you might store a reference to a Shipment Batch in a Purchase Order activity.</span></span>  
  
## <a name="format"></a><span data-ttu-id="e28f9-106">形式</span><span class="sxs-lookup"><span data-stu-id="e28f9-106">Format</span></span>  
 <span data-ttu-id="e28f9-107">`Reference`要素は、両方をサポート、**データ**と**LongData** BAM アクティビティにアタッチするデータを指定する式を含む子要素。</span><span class="sxs-lookup"><span data-stu-id="e28f9-107">The `Reference` element supports both the **Data** and **LongData** child elements that contain an expression specifying the data to attach to the BAM activity.</span></span> <span data-ttu-id="e28f9-108">任意の組み合わせを使用する**データ**と**LongData**追跡要件を満たすためにします。</span><span class="sxs-lookup"><span data-stu-id="e28f9-108">You can use any combination of **Data** and **LongData** to meet your tracking requirements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e28f9-109">属性</span><span class="sxs-lookup"><span data-stu-id="e28f9-109">Attributes</span></span>  
  
|<span data-ttu-id="e28f9-110">属性名</span><span class="sxs-lookup"><span data-stu-id="e28f9-110">Attribute name</span></span>|<span data-ttu-id="e28f9-111">説明</span><span class="sxs-lookup"><span data-stu-id="e28f9-111">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="e28f9-112">名前</span><span class="sxs-lookup"><span data-stu-id="e28f9-112">Name</span></span>|<span data-ttu-id="e28f9-113">BAM アクティビティに追加されるリレーションシップの名前。</span><span class="sxs-lookup"><span data-stu-id="e28f9-113">Name of the relationship that will be attached to the BAM activity.</span></span>|  
|<span data-ttu-id="e28f9-114">型</span><span class="sxs-lookup"><span data-stu-id="e28f9-114">Type</span></span>|<span data-ttu-id="e28f9-115">BAM アクティビティに追加されるリレーションシップの種類を指定する任意の文字列。</span><span class="sxs-lookup"><span data-stu-id="e28f9-115">Arbitrary string specifying the type of relationship that will be attached to the BAM activity.</span></span> <span data-ttu-id="e28f9-116">任意の文字列と次のような BAM の定義済みの種類の両方がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e28f9-116">Both arbitrary strings and the following predefined BAM types are supported:</span></span><br /><br /> <span data-ttu-id="e28f9-117">-BizTalkService</span><span class="sxs-lookup"><span data-stu-id="e28f9-117">-   BizTalkService</span></span><br /><span data-ttu-id="e28f9-118">-MessageID</span><span class="sxs-lookup"><span data-stu-id="e28f9-118">-   MessageID</span></span><br /><span data-ttu-id="e28f9-119">-アクティビティ</span><span class="sxs-lookup"><span data-stu-id="e28f9-119">-   Activity</span></span><br /><span data-ttu-id="e28f9-120">-   DocumentUrl</span><span class="sxs-lookup"><span data-stu-id="e28f9-120">-   DocumentUrl</span></span><br /><span data-ttu-id="e28f9-121">-InstanceID</span><span class="sxs-lookup"><span data-stu-id="e28f9-121">-   InstanceID</span></span><br /><br /> <span data-ttu-id="e28f9-122">定義済みの BAM 参照型の詳細については、次を参照してください。[参照プロパティ](http://go.microsoft.com/fwlink/?LinkId=119601)します。</span><span class="sxs-lookup"><span data-stu-id="e28f9-122">For more information on predefined BAM reference types, see [Reference Properties](http://go.microsoft.com/fwlink/?LinkId=119601).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e28f9-123">子要素</span><span class="sxs-lookup"><span data-stu-id="e28f9-123">Child Elements</span></span>  
  
|<span data-ttu-id="e28f9-124">実行状態</span><span class="sxs-lookup"><span data-stu-id="e28f9-124">Execution status</span></span>|<span data-ttu-id="e28f9-125">説明</span><span class="sxs-lookup"><span data-stu-id="e28f9-125">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="e28f9-126">data</span><span class="sxs-lookup"><span data-stu-id="e28f9-126">Data</span></span>|<span data-ttu-id="e28f9-127">BAM アクティビティに追加される最大 128 文字の文字列データを抽出する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="e28f9-127">Specifies how to extract string data up to 128 characters that will be attached to the BAM activity.</span></span>|  
|<span data-ttu-id="e28f9-128">LongData</span><span class="sxs-lookup"><span data-stu-id="e28f9-128">LongData</span></span>|<span data-ttu-id="e28f9-129">BAM アクティビティに追加される任意の長さの文字列データを抽出する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="e28f9-129">Specifies how to extract arbitrarily long string data that will be attached to the BAM activity.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="e28f9-130">A`Reference`要素は、1 つまたは複数を組み合わせることができます**データ**と**LongData**に応じて子要素。</span><span class="sxs-lookup"><span data-stu-id="e28f9-130">A `Reference` element can combine one or more **Data** and **LongData** child elements as needed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e28f9-131">コメント</span><span class="sxs-lookup"><span data-stu-id="e28f9-131">Remarks</span></span>  
 <span data-ttu-id="e28f9-132">次の一般的な操作は、Reference 式では使用できません。</span><span class="sxs-lookup"><span data-stu-id="e28f9-132">The following common operations are not allowed in Reference expressions:</span></span>  
  
-   <span data-ttu-id="e28f9-133">And</span><span class="sxs-lookup"><span data-stu-id="e28f9-133">And</span></span>  
  
-   <span data-ttu-id="e28f9-134">[等しい]</span><span class="sxs-lookup"><span data-stu-id="e28f9-134">Equals</span></span>  
  
## <a name="example"></a><span data-ttu-id="e28f9-135">例</span><span class="sxs-lookup"><span data-stu-id="e28f9-135">Example</span></span>  
 <span data-ttu-id="e28f9-136">使用して次のサンプルでは、種類が"DocumentUrl"の"Related Document"をという名前の参照が作成されます`GetUserData`ワークフロー。</span><span class="sxs-lookup"><span data-stu-id="e28f9-136">In the following sample, a reference named "Related Document" of type "DocumentUrl" is created using `GetUserData` for a workflow.</span></span> <span data-ttu-id="e28f9-137">ユーザー データが予想されるより少ない 1024 文字の長さにするため、`Data`を格納する要素が使用される、`Expression`要素。</span><span class="sxs-lookup"><span data-stu-id="e28f9-137">Because the user data is expected to be fewer than 1024 characters in length, the `Data` element is used to contain the `Expression` element.</span></span>  
  
```  
<ic:Reference Name="Related Document" Type="DocumentUrl">  
  <ic:Data>  
    <ic:Expression>  
      <wf:Operation Name="GetUserData" />  
    </ic:Expression>  
  </ic:Data>  
</ic:Reference>  
```  
  
 <span data-ttu-id="e28f9-138">**参照**要素の組み合わせをサポートして`Data`と`LongData`要素。</span><span class="sxs-lookup"><span data-stu-id="e28f9-138">The **Reference** element supports a mix of `Data` and `LongData` elements.</span></span> <span data-ttu-id="e28f9-139">次の例で、注文書の国の名前とメモのフィールドが WCF サービスから取得され、種類が"MyType"リレーションシップの"Long and Short Data"に書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="e28f9-139">In the following sample, the country name and note fields from a purchase order are retrieved from a WCF service and written to the relationship "Long and Short Data" as type "MyType".</span></span> <span data-ttu-id="e28f9-140">式を囲む [メモ] フィールドでは、1,024 個を超える文字をサポートするため、`LongData`要素。</span><span class="sxs-lookup"><span data-stu-id="e28f9-140">Because the note field supports more than 1024 characters, the expression is enclosed in a `LongData` element.</span></span>  
  
```  
<ic:Reference Name="Long and Short Data" Type="MyType">  
  <ic:Data>  
    <ic:Expression>  
      <ic:Operation Name="Constant">  
        <ic:Argument>Country: </ic:Argument>  
      </ic:Operation>  
      <wcf:Operation Name="XPath">  
        <wcf:Argument>//s:Body//po:Country</wcf:Argument>  
      </wcf:Operation>  
       <ic:Operation Name="Concatenate" />  
    </ic:Expression>  
  </ic:Data>  
  <ic:LongData>  
    <ic:Expression>  
      <ic:Operation Name="Constant">  
        <ic:Argument>Note: </ic:Argument>  
      </ic:Operation>  
      <wcf:Operation Name="XPath">  
        <wcf:Argument>//s:Body//po:Note</wcf:Argument>  
      </wcf:Operation>  
      <ic:Operation Name="Concatenate" />  
    </ic:Expression>  
  </ic:LongData>  
</ic:Reference>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e28f9-141">参照</span><span class="sxs-lookup"><span data-stu-id="e28f9-141">See Also</span></span>  
 <span data-ttu-id="e28f9-142">[インターセプター OnEvent 要素](../core/interceptor-onevent-element.md) </span><span class="sxs-lookup"><span data-stu-id="e28f9-142">[Interceptor OnEvent Element](../core/interceptor-onevent-element.md) </span></span>  
 [<span data-ttu-id="e28f9-143">EventStream.AddRelatedActivity メソッド</span><span class="sxs-lookup"><span data-stu-id="e28f9-143">EventStream.AddRelatedActivity Method</span></span>](http://go.microsoft.com/fwlink/?LinkId=119602)