---
title: "Update2 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 770c9ebb-df3a-428f-be18-b36535352f8d
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4376cae94e91f462974c626a57170b80b0117ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="update"></a><span data-ttu-id="33f63-102">Update</span><span class="sxs-lookup"><span data-stu-id="33f63-102">Update</span></span>
<span data-ttu-id="33f63-103">`Update` 要素は、イベントからデータを抽出して、関連する BAM アクティビティにインポートするために使用します。</span><span class="sxs-lookup"><span data-stu-id="33f63-103">The `Update` element is used to extract data from an event and import it into the related BAM activity.</span></span>  
  
## <a name="format"></a><span data-ttu-id="33f63-104">Format</span><span class="sxs-lookup"><span data-stu-id="33f63-104">Format</span></span>  
 <span data-ttu-id="33f63-105">使用する、`Update`要素、列名と型の両方を指定する必要があります、**式**要素が 1 つ以上含む**操作**要素 1 つの文字列値に評価されます。</span><span class="sxs-lookup"><span data-stu-id="33f63-105">To use the `Update` element, you must provide both a column name and type and an **Expression** element containing one or more **Operation** elements that evaluate to a single string value.</span></span>  
  
```  
<ic:Update DataItemName="Name" Type="Type">  
  <ic:Expression>  
    <!-- one or more Operation elements -->  
  </ic:Expression>  
</ic:Update>  
```  
  
### <a name="attributes"></a><span data-ttu-id="33f63-106">属性</span><span class="sxs-lookup"><span data-stu-id="33f63-106">Attributes</span></span>  
  
|<span data-ttu-id="33f63-107">属性名</span><span class="sxs-lookup"><span data-stu-id="33f63-107">Attribute name</span></span>|<span data-ttu-id="33f63-108">Description</span><span class="sxs-lookup"><span data-stu-id="33f63-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="33f63-109">[ColumnName]</span><span class="sxs-lookup"><span data-stu-id="33f63-109">ColumnName</span></span>|<span data-ttu-id="33f63-110">BAM アクティビティのチェックポイント名です。</span><span class="sxs-lookup"><span data-stu-id="33f63-110">BAM activity checkpoint name.</span></span> <span data-ttu-id="33f63-111">これは、抽出されたデータで更新されるチェックポイントです。</span><span class="sxs-lookup"><span data-stu-id="33f63-111">This is the checkpoint that will be updated with the extracted data.</span></span>|  
|<span data-ttu-id="33f63-112">型</span><span class="sxs-lookup"><span data-stu-id="33f63-112">Type</span></span>|<span data-ttu-id="33f63-113">チェックポイントの BAM データ型です。次のいずれかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33f63-113">BAM data type of the checkpoint; must be one of the following:</span></span><br /><br /> <span data-ttu-id="33f63-114">-NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="33f63-114">-   NVARCHAR</span></span><br /><span data-ttu-id="33f63-115">-DATETIME</span><span class="sxs-lookup"><span data-stu-id="33f63-115">-   DATETIME</span></span><br /><span data-ttu-id="33f63-116">-INT</span><span class="sxs-lookup"><span data-stu-id="33f63-116">-   INT</span></span><br /><span data-ttu-id="33f63-117">FLOAT</span><span class="sxs-lookup"><span data-stu-id="33f63-117">-   FLOAT</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33f63-118">解説</span><span class="sxs-lookup"><span data-stu-id="33f63-118">Remarks</span></span>  
 <span data-ttu-id="33f63-119">次の演算は、`Update` 式ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="33f63-119">The following operations are not supported in the `Update` expression:</span></span>  
  
-   <span data-ttu-id="33f63-120">And</span><span class="sxs-lookup"><span data-stu-id="33f63-120">And</span></span>  
  
-   <span data-ttu-id="33f63-121">[等しい]</span><span class="sxs-lookup"><span data-stu-id="33f63-121">Equals</span></span>  
  
## <a name="example"></a><span data-ttu-id="33f63-122">例</span><span class="sxs-lookup"><span data-stu-id="33f63-122">Example</span></span>  
 <span data-ttu-id="33f63-123">次の例で、 **GetContextProperty** WF 操作は、取得に使用される、 **EventTime**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="33f63-123">In the following example, the **GetContextProperty** WF operation is used to retrieve the **EventTime** property.</span></span> <span data-ttu-id="33f63-124">この値として保存されます、 **DATETIME** BAM アクティビティの"StartOrderProcessing"データ項目の種類。</span><span class="sxs-lookup"><span data-stu-id="33f63-124">This value will be stored as a **DATETIME** type for the "StartOrderProcessing" data item for the BAM activity.</span></span>  
  
```  
<ic:Update DataItemName="StartOrderProcessing" Type="DATETIME">  
  <ic:Expression>  
    <wf:Operation Name="GetContextProperty">  
      <wf:Argument>EventTime</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:Update>  
```  
  
## <a name="see-also"></a><span data-ttu-id="33f63-125">参照</span><span class="sxs-lookup"><span data-stu-id="33f63-125">See Also</span></span>  
 [<span data-ttu-id="33f63-126">インターセプタ OnEvent 要素</span><span class="sxs-lookup"><span data-stu-id="33f63-126">Interceptor OnEvent Element</span></span>](../core/interceptor-onevent-element.md)