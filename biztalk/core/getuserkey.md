---
title: "GetUserKey |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9353a7f0-9bbd-4cfa-92e6-ed2b86e3a88e
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0701ff1df912cc113205bad573b6cebc0f02a13a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="getuserkey"></a><span data-ttu-id="7db74-102">GetUserKey</span><span class="sxs-lookup"><span data-stu-id="7db74-102">GetUserKey</span></span>
<span data-ttu-id="7db74-103">現在のユーザー キーをスタックにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="7db74-103">Pushes the current user key onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7db74-104">構文</span><span class="sxs-lookup"><span data-stu-id="7db74-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetUserKey" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7db74-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7db74-105">Parameters</span></span>  
 <span data-ttu-id="7db74-106">[なし] :</span><span class="sxs-lookup"><span data-stu-id="7db74-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="7db74-107">プッシュされた値</span><span class="sxs-lookup"><span data-stu-id="7db74-107">Pushed Value</span></span>  
 <span data-ttu-id="7db74-108">現在のユーザー キーが含まれた文字列です。</span><span class="sxs-lookup"><span data-stu-id="7db74-108">String containing the current user key.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7db74-109">解説</span><span class="sxs-lookup"><span data-stu-id="7db74-109">Remarks</span></span>  
 <span data-ttu-id="7db74-110">この操作は、ユーザー追跡ポイントでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="7db74-110">This operation is valid only in user track points.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7db74-111">例</span><span class="sxs-lookup"><span data-stu-id="7db74-111">Example</span></span>  
 <span data-ttu-id="7db74-112">次のサンプルには、ユーザー キーが "DocumentUrl" と等しいときに `true` と評価されるイベント フィルタ式が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7db74-112">The following sample contains an event filter expression that will evaluate to `true` when the user key is equal to "DocumentUrl".</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>DocumentUrl</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```