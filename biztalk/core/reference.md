---
title: リファレンス |Microsoft ドキュメント
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
ms.openlocfilehash: f3e32145e2340a4d86a6893db3e9209b79c2b5e7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268602"
---
# <a name="reference"></a><span data-ttu-id="34cdd-102">リファレンス</span><span class="sxs-lookup"><span data-stu-id="34cdd-102">Reference</span></span>
<span data-ttu-id="34cdd-103">**参照**BAM アクティビティを 1 つまたは複数のリレーションシップを追加する要素を使用できます。</span><span class="sxs-lookup"><span data-stu-id="34cdd-103">The **Reference** element can be used to add one or more relationships to a BAM activity.</span></span> <span data-ttu-id="34cdd-104">この機能は、主キー、ID、URL などのポインタを関連するメッセージに追加する必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="34cdd-104">This is useful when you want to attach a pointer like a primary key, ID, or URL to a related message.</span></span> <span data-ttu-id="34cdd-105">たとえば、出荷バッチへの参照を発注アクティビティに保存できます。</span><span class="sxs-lookup"><span data-stu-id="34cdd-105">For example, you might store a reference to a Shipment Batch in a Purchase Order activity.</span></span>  
  
## <a name="format"></a><span data-ttu-id="34cdd-106">Format</span><span class="sxs-lookup"><span data-stu-id="34cdd-106">Format</span></span>  
 <span data-ttu-id="34cdd-107">`Reference`要素では、両方がサポートする、**データ**と**LongData**を BAM アクティビティにアタッチするデータを指定する式を含む子要素です。</span><span class="sxs-lookup"><span data-stu-id="34cdd-107">The `Reference` element supports both the **Data** and **LongData** child elements that contain an expression specifying the data to attach to the BAM activity.</span></span> <span data-ttu-id="34cdd-108">任意の組み合わせを使用する**データ**と**LongData**を追跡要件を満たすようにします。</span><span class="sxs-lookup"><span data-stu-id="34cdd-108">You can use any combination of **Data** and **LongData** to meet your tracking requirements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34cdd-109">属性</span><span class="sxs-lookup"><span data-stu-id="34cdd-109">Attributes</span></span>  
  
|<span data-ttu-id="34cdd-110">属性名</span><span class="sxs-lookup"><span data-stu-id="34cdd-110">Attribute name</span></span>|<span data-ttu-id="34cdd-111">Description</span><span class="sxs-lookup"><span data-stu-id="34cdd-111">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="34cdd-112">名前</span><span class="sxs-lookup"><span data-stu-id="34cdd-112">Name</span></span>|<span data-ttu-id="34cdd-113">BAM アクティビティに追加されるリレーションシップの名前です。</span><span class="sxs-lookup"><span data-stu-id="34cdd-113">Name of the relationship that will be attached to the BAM activity.</span></span>|  
|<span data-ttu-id="34cdd-114">型</span><span class="sxs-lookup"><span data-stu-id="34cdd-114">Type</span></span>|<span data-ttu-id="34cdd-115">BAM アクティビティに追加されるリレーションシップの種類を指定する任意の文字列です。</span><span class="sxs-lookup"><span data-stu-id="34cdd-115">Arbitrary string specifying the type of relationship that will be attached to the BAM activity.</span></span> <span data-ttu-id="34cdd-116">任意の文字列だけでなく、以下の定義済みの BAM の種類もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="34cdd-116">Both arbitrary strings and the following predefined BAM types are supported:</span></span><br /><br /> <span data-ttu-id="34cdd-117">-BizTalkService</span><span class="sxs-lookup"><span data-stu-id="34cdd-117">-   BizTalkService</span></span><br /><span data-ttu-id="34cdd-118">-MessageID</span><span class="sxs-lookup"><span data-stu-id="34cdd-118">-   MessageID</span></span><br /><span data-ttu-id="34cdd-119">-アクティビティ</span><span class="sxs-lookup"><span data-stu-id="34cdd-119">-   Activity</span></span><br /><span data-ttu-id="34cdd-120">-DocumentUrl</span><span class="sxs-lookup"><span data-stu-id="34cdd-120">-   DocumentUrl</span></span><br /><span data-ttu-id="34cdd-121">-InstanceID</span><span class="sxs-lookup"><span data-stu-id="34cdd-121">-   InstanceID</span></span><br /><br /> <span data-ttu-id="34cdd-122">定義済みの BAM 参照型の詳細については、次を参照してください。[参照プロパティ](http://go.microsoft.com/fwlink/?LinkId=119601)です。</span><span class="sxs-lookup"><span data-stu-id="34cdd-122">For more information on predefined BAM reference types, see [Reference Properties](http://go.microsoft.com/fwlink/?LinkId=119601).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="34cdd-123">子要素</span><span class="sxs-lookup"><span data-stu-id="34cdd-123">Child Elements</span></span>  
  
|<span data-ttu-id="34cdd-124">実行状態</span><span class="sxs-lookup"><span data-stu-id="34cdd-124">Execution status</span></span>|<span data-ttu-id="34cdd-125">Description</span><span class="sxs-lookup"><span data-stu-id="34cdd-125">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="34cdd-126">data</span><span class="sxs-lookup"><span data-stu-id="34cdd-126">Data</span></span>|<span data-ttu-id="34cdd-127">BAM アクティビティに追加される最大 128 文字の文字列データを抽出する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="34cdd-127">Specifies how to extract string data up to 128 characters that will be attached to the BAM activity.</span></span>|  
|<span data-ttu-id="34cdd-128">LongData</span><span class="sxs-lookup"><span data-stu-id="34cdd-128">LongData</span></span>|<span data-ttu-id="34cdd-129">BAM アクティビティに追加される任意の長さの文字列データを抽出する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="34cdd-129">Specifies how to extract arbitrarily long string data that will be attached to the BAM activity.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="34cdd-130">A`Reference`要素は、1 つまたは複数を組み合わせることができます**データ**と**LongData**必要に応じて、子要素です。</span><span class="sxs-lookup"><span data-stu-id="34cdd-130">A `Reference` element can combine one or more **Data** and **LongData** child elements as needed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34cdd-131">解説</span><span class="sxs-lookup"><span data-stu-id="34cdd-131">Remarks</span></span>  
 <span data-ttu-id="34cdd-132">次の一般的な演算は、Reference 式では許可されていません。</span><span class="sxs-lookup"><span data-stu-id="34cdd-132">The following common operations are not allowed in Reference expressions:</span></span>  
  
-   <span data-ttu-id="34cdd-133">And</span><span class="sxs-lookup"><span data-stu-id="34cdd-133">And</span></span>  
  
-   <span data-ttu-id="34cdd-134">[等しい]</span><span class="sxs-lookup"><span data-stu-id="34cdd-134">Equals</span></span>  
  
## <a name="example"></a><span data-ttu-id="34cdd-135">例</span><span class="sxs-lookup"><span data-stu-id="34cdd-135">Example</span></span>  
 <span data-ttu-id="34cdd-136">次のサンプルでは、ワークフローに対して `GetUserData` を使用して、種類が "DocumentUrl" の "Related Document" という参照が作成されます。</span><span class="sxs-lookup"><span data-stu-id="34cdd-136">In the following sample, a reference named "Related Document" of type "DocumentUrl" is created using `GetUserData` for a workflow.</span></span> <span data-ttu-id="34cdd-137">ユーザー データの長さは 1,024 文字未満であることが予想されるため、`Data` 要素を格納するために `Expression` 要素が使用されます。</span><span class="sxs-lookup"><span data-stu-id="34cdd-137">Because the user data is expected to be fewer than 1024 characters in length, the `Data` element is used to contain the `Expression` element.</span></span>  
  
```  
<ic:Reference Name="Related Document" Type="DocumentUrl">  
  <ic:Data>  
    <ic:Expression>  
      <wf:Operation Name="GetUserData" />  
    </ic:Expression>  
  </ic:Data>  
</ic:Reference>  
```  
  
 <span data-ttu-id="34cdd-138">**参照**要素の組み合わせをサポートしている`Data`と`LongData`要素。</span><span class="sxs-lookup"><span data-stu-id="34cdd-138">The **Reference** element supports a mix of `Data` and `LongData` elements.</span></span> <span data-ttu-id="34cdd-139">次のサンプルでは、注文書の国名フィールドとメモ フィールドが WCF サービスから取得され、種類が "MyType" の "Long and Short Data" というリレーションシップに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="34cdd-139">In the following sample, the country name and note fields from a purchase order are retrieved from a WCF service and written to the relationship "Long and Short Data" as type "MyType".</span></span> <span data-ttu-id="34cdd-140">メモ フィールドには 1,024 文字より長い文字列を入力できるので、式は `LongData` 要素で囲まれています。</span><span class="sxs-lookup"><span data-stu-id="34cdd-140">Because the note field supports more than 1024 characters, the expression is enclosed in a `LongData` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="34cdd-141">参照</span><span class="sxs-lookup"><span data-stu-id="34cdd-141">See Also</span></span>  
 <span data-ttu-id="34cdd-142">[インターセプタ OnEvent 要素](../core/interceptor-onevent-element.md) </span><span class="sxs-lookup"><span data-stu-id="34cdd-142">[Interceptor OnEvent Element](../core/interceptor-onevent-element.md) </span></span>  
 [<span data-ttu-id="34cdd-143">EventStream.AddRelatedActivity メソッド</span><span class="sxs-lookup"><span data-stu-id="34cdd-143">EventStream.AddRelatedActivity Method</span></span>](http://go.microsoft.com/fwlink/?LinkId=119602)