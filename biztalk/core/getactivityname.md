---
title: GetActivityName |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 479552fa-1535-4f3d-90ff-4615f14c88b1
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 597b08fc9ea9f19b6c3d7f7e3488ae7f77b2c62f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387739"
---
# <a name="getactivityname"></a><span data-ttu-id="0c159-102">GetActivityName</span><span class="sxs-lookup"><span data-stu-id="0c159-102">GetActivityName</span></span>
<span data-ttu-id="0c159-103">現在のアクティビティの名前をスタックにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="0c159-103">Pushes the name of the current activity onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c159-104">構文</span><span class="sxs-lookup"><span data-stu-id="0c159-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetActivityName"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0c159-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0c159-105">Parameters</span></span>  
 <span data-ttu-id="0c159-106">[なし] :</span><span class="sxs-lookup"><span data-stu-id="0c159-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="0c159-107">プッシュされた値</span><span class="sxs-lookup"><span data-stu-id="0c159-107">Pushed Value</span></span>  
 <span data-ttu-id="0c159-108">現在のアクティビティの名前を表す文字列。</span><span class="sxs-lookup"><span data-stu-id="0c159-108">String containing the current activity name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c159-109">コメント</span><span class="sxs-lookup"><span data-stu-id="0c159-109">Remarks</span></span>  
 <span data-ttu-id="0c159-110">Windows Workflow Foundation では、開発者によって構成された一連のアクティビティとして処理が実行されます。</span><span class="sxs-lookup"><span data-stu-id="0c159-110">Windows Workflow Foundation performs its work as a series of activities configured by the developer.</span></span> <span data-ttu-id="0c159-111">これらのアクティビティにはそれぞれワークフロー内で一意の名前が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="0c159-111">Each of these activities is assigned a unique name within the workflow.</span></span> <span data-ttu-id="0c159-112">アクティビティの一意の名前に基づいてフィルタ処理を行うことにより、特定のアクティビティのデータを傍受できます。</span><span class="sxs-lookup"><span data-stu-id="0c159-112">You can intercept data for a specific activity by filtering based on its unique name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c159-113">例</span><span class="sxs-lookup"><span data-stu-id="0c159-113">Example</span></span>  
 <span data-ttu-id="0c159-114">次のサンプルには、Closed ワークフロー内の FoodAndDrinksPolicy という特定のアクティビティを検出するように構成されたイベント フィルタ式が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0c159-114">The following sample contains an event filter expression configured to find a specific activity—FoodAndDrinksPolicy—in a Closed workflow.</span></span> <span data-ttu-id="0c159-115">この処理は、`GetActivityName`、`GetActivityEvent`、論理演算などの演算の組み合わせを使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="0c159-115">This is done by using a combination of operations including `GetActivityName`, `GetActivityEvent`, and logical operations.</span></span>  
  
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
  
 <span data-ttu-id="0c159-116">このフィルタ パターンは、Windows Workflow Foundation インターセプタ構成ファイルで共通です。</span><span class="sxs-lookup"><span data-stu-id="0c159-116">This filter pattern is common with Windows Workflow Foundation interceptor configuration files.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c159-117">引用符を含む文字列を明示的に照合する場合を除いて、引数に引用符は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="0c159-117">Arguments do not require quotation marks unless you are explicitly trying to match a string that contains quotation marks.</span></span>