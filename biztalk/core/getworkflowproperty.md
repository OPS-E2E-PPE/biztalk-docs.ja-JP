---
title: GetWorkflowProperty |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c9d3029e-3267-46bc-ba2e-1c6fa1f2e931
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53e31ea557508164bd5e434558ebdf6bb0689a7c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344906"
---
# <a name="getworkflowproperty"></a><span data-ttu-id="641f6-102">GetWorkflowProperty</span><span class="sxs-lookup"><span data-stu-id="641f6-102">GetWorkflowProperty</span></span>
<span data-ttu-id="641f6-103">スタックにワークフローのルート アクティビティから抽出されたプロパティをプッシュします。</span><span class="sxs-lookup"><span data-stu-id="641f6-103">Pushes the extracted property from the root activity of the workflow onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="641f6-104">構文</span><span class="sxs-lookup"><span data-stu-id="641f6-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetWorkflowProperty">  
      <wf:Argument>Arg1</wf:Argument>  
</wf:Operation>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="641f6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="641f6-105">Parameters</span></span>  
 <span data-ttu-id="641f6-106">プロパティの名前です。</span><span class="sxs-lookup"><span data-stu-id="641f6-106">Name of the property.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="641f6-107">プッシュされた値</span><span class="sxs-lookup"><span data-stu-id="641f6-107">Pushed Value</span></span>  
 <span data-ttu-id="641f6-108">プロパティの値を格納している文字列。</span><span class="sxs-lookup"><span data-stu-id="641f6-108">String containing the value of the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="641f6-109">コメント</span><span class="sxs-lookup"><span data-stu-id="641f6-109">Remarks</span></span>  
 <span data-ttu-id="641f6-110">この操作で、更新プログラムのみです。</span><span class="sxs-lookup"><span data-stu-id="641f6-110">This operation is only valid in Updates.</span></span>  
  
 <span data-ttu-id="641f6-111">取得するプロパティ名を修飾するために、ドット付き表記を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="641f6-111">You can use dotted-notation for qualifying the property name you want to retrieve.</span></span> <span data-ttu-id="641f6-112">これにより、プロパティを通じて公開される他のオブジェクト内のオブジェクトにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="641f6-112">This will provide you access to objects inside of other objects exposed through properties.</span></span> <span data-ttu-id="641f6-113">たとえば、注文書の Address インスタンスの City プロパティにアクセスするには、"purchaseOrder.Address.City" を使用します。</span><span class="sxs-lookup"><span data-stu-id="641f6-113">For example, to access the City property of an Address instance of a purchase order, use "purchaseOrder.Address.City".</span></span>  
  
 <span data-ttu-id="641f6-114">プロパティ名は、最初は大文字と小文字が区別され、その後は大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="641f6-114">Property names are case-sensitive first, and then case-insensitive.</span></span> <span data-ttu-id="641f6-115">これは、WF アプリケーションで、大文字と小文字の区別のみが異なる複数のアクティビティ プロパティを使用する場合に重要です。</span><span class="sxs-lookup"><span data-stu-id="641f6-115">This is important when you have two or more activity properties that vary only by case in your WF application.</span></span> <span data-ttu-id="641f6-116">たとえば、ワークフロー アプリケーションで "myWorkflow" プロパティと "MyWorkflow" プロパティを定義している場合に "MyWorkflow" を検索すると、大文字と小文字を区別する照合において "MyWorkflow" プロパティが検索されます。</span><span class="sxs-lookup"><span data-stu-id="641f6-116">For example, if your workflow application has the properties "myWorkflow" and "MyWorkflow" defined and you were looking for "MyWorkflow", it would match on the second property through a case-sensitive match.</span></span> <span data-ttu-id="641f6-117">"MYWORKFLOW"を指定すると、大文字と小文字の試行が失敗した後に"myWorkflow"で大文字と小文字が一致してしまいます。</span><span class="sxs-lookup"><span data-stu-id="641f6-117">If you specify "MYWORKFLOW", it would match "myWorkflow" through a case-sensitive match after a case-insensitive match attempt fails.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="641f6-118">NULL プロパティ値を使用すると、ワークフロー インスタンスに NullReferenceException がスローされます。</span><span class="sxs-lookup"><span data-stu-id="641f6-118">NULL property values will result in a NullReferenceException being thrown back to the workflow instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="641f6-119">例</span><span class="sxs-lookup"><span data-stu-id="641f6-119">Example</span></span>  
 <span data-ttu-id="641f6-120">Update 式を使用すると、注文書からワークフロー プロパティ"City"を使用して永続化では、次の例では、`GetWorkflowProperty`します。</span><span class="sxs-lookup"><span data-stu-id="641f6-120">In the following sample, an update expression is used to persist the workflow property "City" from a purchase order by using `GetWorkflowProperty`.</span></span>  
  
```  
<ic:Update DataItemName="City" Type="NVARCHAR">  
  <ic:Expression>  
    <wf:Operation Name="GetWorkflowProperty">  
      <wf:Argument>po.Info.City</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:Update>  
```