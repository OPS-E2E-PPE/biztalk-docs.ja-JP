---
title: Update2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 770c9ebb-df3a-428f-be18-b36535352f8d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c090d11686babacfcb854782484b689dff2102e0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398618"
---
# <a name="update"></a><span data-ttu-id="64df2-102">更新</span><span class="sxs-lookup"><span data-stu-id="64df2-102">Update</span></span>
<span data-ttu-id="64df2-103">`Update`要素を使用して、イベントからデータを抽出し、関連する BAM アクティビティにインポートします。</span><span class="sxs-lookup"><span data-stu-id="64df2-103">The `Update` element is used to extract data from an event and import it into the related BAM activity.</span></span>  
  
## <a name="format"></a><span data-ttu-id="64df2-104">形式</span><span class="sxs-lookup"><span data-stu-id="64df2-104">Format</span></span>  
 <span data-ttu-id="64df2-105">使用する、`Update`要素の場合、列名と型の両方を指定する必要があります、**式**要素の 1 つ以上含む**操作**1 つの文字列値に評価される要素。</span><span class="sxs-lookup"><span data-stu-id="64df2-105">To use the `Update` element, you must provide both a column name and type and an **Expression** element containing one or more **Operation** elements that evaluate to a single string value.</span></span>  
  
```  
<ic:Update DataItemName="Name" Type="Type">  
  <ic:Expression>  
    <!-- one or more Operation elements -->  
  </ic:Expression>  
</ic:Update>  
```  
  
### <a name="attributes"></a><span data-ttu-id="64df2-106">属性</span><span class="sxs-lookup"><span data-stu-id="64df2-106">Attributes</span></span>  
  
|<span data-ttu-id="64df2-107">属性名</span><span class="sxs-lookup"><span data-stu-id="64df2-107">Attribute name</span></span>|<span data-ttu-id="64df2-108">説明</span><span class="sxs-lookup"><span data-stu-id="64df2-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="64df2-109">[ColumnName]</span><span class="sxs-lookup"><span data-stu-id="64df2-109">ColumnName</span></span>|<span data-ttu-id="64df2-110">BAM のアクティビティ チェックポイントの名前。</span><span class="sxs-lookup"><span data-stu-id="64df2-110">BAM activity checkpoint name.</span></span> <span data-ttu-id="64df2-111">これは、抽出されたデータで更新されるチェックポイントです。</span><span class="sxs-lookup"><span data-stu-id="64df2-111">This is the checkpoint that will be updated with the extracted data.</span></span>|  
|<span data-ttu-id="64df2-112">型</span><span class="sxs-lookup"><span data-stu-id="64df2-112">Type</span></span>|<span data-ttu-id="64df2-113">のチェックポイントの BAM データ型次のいずれかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64df2-113">BAM data type of the checkpoint; must be one of the following:</span></span><br /><br /> <span data-ttu-id="64df2-114">-   NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="64df2-114">-   NVARCHAR</span></span><br /><span data-ttu-id="64df2-115">-DATETIME</span><span class="sxs-lookup"><span data-stu-id="64df2-115">-   DATETIME</span></span><br /><span data-ttu-id="64df2-116">-INT</span><span class="sxs-lookup"><span data-stu-id="64df2-116">-   INT</span></span><br /><span data-ttu-id="64df2-117">-FLOAT</span><span class="sxs-lookup"><span data-stu-id="64df2-117">-   FLOAT</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64df2-118">コメント</span><span class="sxs-lookup"><span data-stu-id="64df2-118">Remarks</span></span>  
 <span data-ttu-id="64df2-119">次の操作がサポートされていない、`Update`式。</span><span class="sxs-lookup"><span data-stu-id="64df2-119">The following operations are not supported in the `Update` expression:</span></span>  
  
-   <span data-ttu-id="64df2-120">And</span><span class="sxs-lookup"><span data-stu-id="64df2-120">And</span></span>  
  
-   <span data-ttu-id="64df2-121">[等しい]</span><span class="sxs-lookup"><span data-stu-id="64df2-121">Equals</span></span>  
  
## <a name="example"></a><span data-ttu-id="64df2-122">例</span><span class="sxs-lookup"><span data-stu-id="64df2-122">Example</span></span>  
 <span data-ttu-id="64df2-123">次の例では、 **GetContextProperty** WF の操作を使用して、取得、 **EventTime**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="64df2-123">In the following example, the **GetContextProperty** WF operation is used to retrieve the **EventTime** property.</span></span> <span data-ttu-id="64df2-124">としてこの値が格納される、 **DATETIME** BAM アクティビティの"StartOrderProcessing"データ項目の種類。</span><span class="sxs-lookup"><span data-stu-id="64df2-124">This value will be stored as a **DATETIME** type for the "StartOrderProcessing" data item for the BAM activity.</span></span>  
  
```  
<ic:Update DataItemName="StartOrderProcessing" Type="DATETIME">  
  <ic:Expression>  
    <wf:Operation Name="GetContextProperty">  
      <wf:Argument>EventTime</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:Update>  
```  
  
## <a name="see-also"></a><span data-ttu-id="64df2-125">参照</span><span class="sxs-lookup"><span data-stu-id="64df2-125">See Also</span></span>  
 [<span data-ttu-id="64df2-126">インターセプター OnEvent 要素</span><span class="sxs-lookup"><span data-stu-id="64df2-126">Interceptor OnEvent Element</span></span>](../core/interceptor-onevent-element.md)