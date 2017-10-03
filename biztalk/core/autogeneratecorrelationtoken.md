---
title: "AutoGenerateCorrelationToken |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a24357c9-34e5-4caa-b41c-19551cfe81f9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e396fd0b2c6153a5252d336b9af9c22bf9421fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="autogeneratecorrelationtoken"></a><span data-ttu-id="048b1-102">AutoGenerateCorrelationToken</span><span class="sxs-lookup"><span data-stu-id="048b1-102">AutoGenerateCorrelationToken</span></span>
<span data-ttu-id="048b1-103">自動的に関連付けトークンを生成して、スタック上に配置します。</span><span class="sxs-lookup"><span data-stu-id="048b1-103">Automatically generates a correlation token and places it onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="048b1-104">構文</span><span class="sxs-lookup"><span data-stu-id="048b1-104">Syntax</span></span>  
  
```  
  
<wcf:Operation Name="AutoGenerateCorrelationToken" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="048b1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="048b1-105">Parameters</span></span>  
 <span data-ttu-id="048b1-106">[なし] :</span><span class="sxs-lookup"><span data-stu-id="048b1-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="048b1-107">プッシュされた値</span><span class="sxs-lookup"><span data-stu-id="048b1-107">Pushed Value</span></span>  
 <span data-ttu-id="048b1-108">関連付けトークンが含まれた文字列です。</span><span class="sxs-lookup"><span data-stu-id="048b1-108">String containing the correlation token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="048b1-109">解説</span><span class="sxs-lookup"><span data-stu-id="048b1-109">Remarks</span></span>  
 <span data-ttu-id="048b1-110">この操作は、メッセージ内に関連付けトークンがないが、要求と応答からの情報を関連付ける必要がある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="048b1-110">This operation can be used when there is no correlation token present in the message but you still want to correlate the information from a request and a reply.</span></span> <span data-ttu-id="048b1-111">この操作を行うと、クライアント側またはサービス側で特定の要求/応答を関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="048b1-111">It can be used to correlate a particular request/reply on either the client or the service side.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="048b1-112">クライアントとサービスの両方で要求と応答によって生成されるデータを関連付けるには (継続)、メッセージのデータ要素を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="048b1-112">If you want to correlate the data gathered by the request and the reply for both the client and the service (a continuation), you will need to use a data element or elements from your message.</span></span>  
  
## <a name="example"></a><span data-ttu-id="048b1-113">例</span><span class="sxs-lookup"><span data-stu-id="048b1-113">Example</span></span>  
 <span data-ttu-id="048b1-114">次に示す関連付けの式の例は、`AutoGenerateCorrelationToken` によって関連付けトークンが生成されることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="048b1-114">The following example correlation expression relies on the `AutoGenerateCorrelationToken` to generate a correlation token.</span></span>  
  
```  
<ic:CorrelationID>  
  <ic:Expression>            
    <wcf:Operation Name="AutoGenerateCorrelationToken"/>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
## <a name="see-also"></a><span data-ttu-id="048b1-115">参照</span><span class="sxs-lookup"><span data-stu-id="048b1-115">See Also</span></span>  
 [<span data-ttu-id="048b1-116">Windows Communication Foundation での操作</span><span class="sxs-lookup"><span data-stu-id="048b1-116">Operations in Windows Communication Foundation</span></span>](../core/operations-in-windows-communication-foundation.md)