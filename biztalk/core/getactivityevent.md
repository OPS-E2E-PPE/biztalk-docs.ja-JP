---
title: GetActivityEvent |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6fe824c9-4cea-44da-b830-5520d67988e0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fb039c0e9946091214a52fbb605753a212c233c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246250"
---
# <a name="getactivityevent"></a><span data-ttu-id="b9b59-102">GetActivityEvent</span><span class="sxs-lookup"><span data-stu-id="b9b59-102">GetActivityEvent</span></span>
<span data-ttu-id="b9b59-103">現在のアクティビティ イベントの名前をスタックにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="b9b59-103">Pushes the name of the current activity event onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9b59-104">構文</span><span class="sxs-lookup"><span data-stu-id="b9b59-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetActivityEvent"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9b59-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b9b59-105">Parameters</span></span>  
 <span data-ttu-id="b9b59-106">[なし] :</span><span class="sxs-lookup"><span data-stu-id="b9b59-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="b9b59-107">プッシュされた値</span><span class="sxs-lookup"><span data-stu-id="b9b59-107">Pushed Value</span></span>  
 <span data-ttu-id="b9b59-108">現在のアクティビティ イベントを表す文字列です。</span><span class="sxs-lookup"><span data-stu-id="b9b59-108">String containing the current activity event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9b59-109">解説</span><span class="sxs-lookup"><span data-stu-id="b9b59-109">Remarks</span></span>  
 <span data-ttu-id="b9b59-110">ワークフロー アクティビティは、ワークフローの有効期間中にいくつかの状態の段階を経る場合があります。</span><span class="sxs-lookup"><span data-stu-id="b9b59-110">A workflow activity can pass through several states during the lifetime of the workflow.</span></span> <span data-ttu-id="b9b59-111">Windows Workflow Foundation BAM インターセプタは、`System.Workflow.ComponentModel.ActivityExecutionStatus` 列挙体に定義された、次の表に示すような大部分の実行状態の値をサポートします。</span><span class="sxs-lookup"><span data-stu-id="b9b59-111">The Windows Workflow Foundation BAM interceptor supports most of the execution status values defined by the `System.Workflow.ComponentModel.ActivityExecutionStatus` enumeration, as shown in the following table.</span></span>  
  
|<span data-ttu-id="b9b59-112">実行状態</span><span class="sxs-lookup"><span data-stu-id="b9b59-112">Execution status</span></span>|<span data-ttu-id="b9b59-113">Description</span><span class="sxs-lookup"><span data-stu-id="b9b59-113">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="b9b59-114">Canceling</span><span class="sxs-lookup"><span data-stu-id="b9b59-114">Canceling</span></span>|<span data-ttu-id="b9b59-115">アクティビティが取り消されているときの状態を表します。</span><span class="sxs-lookup"><span data-stu-id="b9b59-115">Represents the status when an activity is in the process of being canceled.</span></span>|  
|<span data-ttu-id="b9b59-116">Closed</span><span class="sxs-lookup"><span data-stu-id="b9b59-116">Closed</span></span>|<span data-ttu-id="b9b59-117">アクティビティが終了したときの状態を表します。</span><span class="sxs-lookup"><span data-stu-id="b9b59-117">Represents the status when an activity is closed.</span></span>|  
|<span data-ttu-id="b9b59-118">Compensating</span><span class="sxs-lookup"><span data-stu-id="b9b59-118">Compensating</span></span>|<span data-ttu-id="b9b59-119">アクティビティを補正しているときの状態を表します。</span><span class="sxs-lookup"><span data-stu-id="b9b59-119">Represents the status when an activity is compensating.</span></span>|  
|<span data-ttu-id="b9b59-120">Executing</span><span class="sxs-lookup"><span data-stu-id="b9b59-120">Executing</span></span>|<span data-ttu-id="b9b59-121">アクティビティを実行しているときの状態を表します。</span><span class="sxs-lookup"><span data-stu-id="b9b59-121">Represents the status when an activity is executing.</span></span>|  
|<span data-ttu-id="b9b59-122">Faulting</span><span class="sxs-lookup"><span data-stu-id="b9b59-122">Faulting</span></span>|<span data-ttu-id="b9b59-123">アクティビティでエラーが発生しているときの状態を表します。</span><span class="sxs-lookup"><span data-stu-id="b9b59-123">Represents the status when an activity is faulting.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="b9b59-124">同じ OnEvent 要素で `GetActivityEvent` と `GetWorkflowEvent` の両方を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="b9b59-124">You cannot use both `GetActivityEvent` and `GetWorkflowEvent` in the same OnEvent element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9b59-125">例</span><span class="sxs-lookup"><span data-stu-id="b9b59-125">Example</span></span>  
 <span data-ttu-id="b9b59-126">次のサンプルには、Closed ワークフロー内の FoodAndDringPolicy という特定のアクティビティを検出するように構成されたイベント フィルタ式が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b9b59-126">The following sample contains an event filter expression configured to find a specific activity—FoodAndDringPolicy—in a Closed workflow.</span></span> <span data-ttu-id="b9b59-127">この処理は、`GetActivityEvent`、`GetActivityName`、論理演算などの演算の組み合わせを使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="b9b59-127">This is done by using a combination of operations including `GetActivityEvent`, `GetActivityName`, and logical operations.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>FoodAndDrinksPolicy</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <wf:Operation Name="GetActivityEvent"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <ic:Operation Name="And"/>  
  </ic:Expression>  
</ic:Filter>  
```  
  
 <span data-ttu-id="b9b59-128">このフィルタ パターンは、Windows Workflow Foundation インターセプタ構成ファイルで共通です。</span><span class="sxs-lookup"><span data-stu-id="b9b59-128">This filter pattern is common with Windows Workflow Foundation interceptor configuration files.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b9b59-129">引用符を含む文字列を明示的に照合する場合を除いて、引数に引用符は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="b9b59-129">Arguments do not require quotation marks unless you are explicitly trying to match a string that contains quotation marks.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9b59-130">参照</span><span class="sxs-lookup"><span data-stu-id="b9b59-130">See Also</span></span>  
 [<span data-ttu-id="b9b59-131">System.Workflow.ComponentModel.ActivityExecutionStatus 列挙体</span><span class="sxs-lookup"><span data-stu-id="b9b59-131">System.Workflow.ComponentModel.ActivityExecutionStatus enumeration</span></span>](http://go.microsoft.com/fwlink/?LinkId=119570)