---
title: 例外の原因 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, errors
- errors, orchestrations
- errors, causes
ms.assetid: b0422382-d034-4c58-87c6-fc269dbbfe43
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 71c6bf04421ca538400545239711637990e3adf5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357595"
---
# <a name="causes-of-exceptions"></a><span data-ttu-id="09735-102">例外の原因</span><span class="sxs-lookup"><span data-stu-id="09735-102">Causes of Exceptions</span></span>
<span data-ttu-id="09735-103">次の方法で、オーケストレーション内で例外を生成できます。</span><span class="sxs-lookup"><span data-stu-id="09735-103">Exceptions can be generated within an orchestration in the following ways:</span></span>  
  
-   <span data-ttu-id="09735-104">によって、**例外のスロー**図形で、すぐに、無条件で例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="09735-104">By a **Throw Exception** shape, which throws an exception immediately and unconditionally.</span></span> <span data-ttu-id="09735-105">制御が渡される、**例外のスロー**適切な例外ハンドラーに直接図形。</span><span class="sxs-lookup"><span data-stu-id="09735-105">Control passes from the **Throw Exception** shape directly to the appropriate exception handler.</span></span>  
  
-   <span data-ttu-id="09735-106">実行時間の長いトランザクションで期限切れにならない、タイムアウトします。</span><span class="sxs-lookup"><span data-stu-id="09735-106">By a time-out expiring in a long-running transaction.</span></span> <span data-ttu-id="09735-107">定義済みのシステム例外:**Microsoft.XLANG.BaseTypes.TimeOutException**: この場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="09735-107">A predefined system exception—**Microsoft.XLANG.BaseTypes.TimeOutException**—is thrown in this case.</span></span>  
  
-   <span data-ttu-id="09735-108">その他のトランザクション障害が発生しています。</span><span class="sxs-lookup"><span data-stu-id="09735-108">By some other transaction failure.</span></span> <span data-ttu-id="09735-109">ランタイム エンジンは、これらのエラー Microsoft.XLANG.BaseTypes.PersistenceException などのシステム定義メッセージをスローします。</span><span class="sxs-lookup"><span data-stu-id="09735-109">The runtime engine throws a system-defined message such as Microsoft.XLANG.BaseTypes.PersistenceException for these failures.</span></span>  
  
-   <span data-ttu-id="09735-110">ユーザー コードの例外。</span><span class="sxs-lookup"><span data-stu-id="09735-110">By a user code exception.</span></span> <span data-ttu-id="09735-111">オーケストレーション内では、外部のユーザー コードへの呼び出しが行われた、ときに呼び出される共通言語ランタイム クラスは例外をスローできます。</span><span class="sxs-lookup"><span data-stu-id="09735-111">When calls to external user code are made within an orchestration, common language runtime classes that are called can throw exceptions.</span></span> <span data-ttu-id="09735-112">これらの例外は、ユーザー コードで処理されない場合最終的に伝達されるをユーザー コードへの呼び出しが行われるスコープにします。</span><span class="sxs-lookup"><span data-stu-id="09735-112">If these exceptions are not handled in the user code, they eventually propagate up into the scope in which the call to the user code is made.</span></span>  
  
-   <span data-ttu-id="09735-113">いくつかその他のシステム例外によって (永続化エラー、型のローダーの例外などの別の .NET またはシステム例外またはデータ変換エラーなど)。</span><span class="sxs-lookup"><span data-stu-id="09735-113">By some other system exception (for example, a persistence failure, another .NET or system exception such as type loader exception, or a data conversion error).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="09735-114">内に、例外型のローダーの例外がスローされると、キャッチされない可能性があります、**例外のキャッチ**同じブロック**スコープ**図形。</span><span class="sxs-lookup"><span data-stu-id="09735-114">When a type loader exception is thrown, the exception may not be caught in the **Catch Exception** block in the same **Scope** shape.</span></span> <span data-ttu-id="09735-115">これは、ため、例外が、BizTalk オーケストレーション プロセスからではなく、型のローダーからがあります。</span><span class="sxs-lookup"><span data-stu-id="09735-115">This is because of that the exception is from the type loader, not from the BizTalk orchestration process.</span></span> <span data-ttu-id="09735-116">そのため、制御フローの BizTalk のルールに従っていません。</span><span class="sxs-lookup"><span data-stu-id="09735-116">Therefore, it does not follow the BizTalk rules of control flow.</span></span>  
  
-   <span data-ttu-id="09735-117">実行を停止する前後のスコープ内の兄弟分岐します。</span><span class="sxs-lookup"><span data-stu-id="09735-117">By a sibling branch in a surrounding scope halting execution.</span></span> <span data-ttu-id="09735-118">各分岐に Microsoft.XLANG.BaseTypes.ForcedTerminationException がここでは、スローされ、それぞれに例外ハンドラーを追加する場合があります。</span><span class="sxs-lookup"><span data-stu-id="09735-118">Microsoft.XLANG.BaseTypes.ForcedTerminationException is thrown to each branch in this case, and you might want to add an exception handler to each.</span></span> <span data-ttu-id="09735-119">このような例外ハンドラーからその例外を再スローすることはできません。 また他の種類の例外をスローしよう必要があります。</span><span class="sxs-lookup"><span data-stu-id="09735-119">Such an exception handler cannot re-throw its exception, nor should it attempt to throw any other type of exception.</span></span>  
  
-   <span data-ttu-id="09735-120">外部のメッセージの受信によっては、エラーを示すです。</span><span class="sxs-lookup"><span data-stu-id="09735-120">By receipt of an external message that indicates a fault.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09735-121">参照</span><span class="sxs-lookup"><span data-stu-id="09735-121">See Also</span></span>  
 <span data-ttu-id="09735-122">[エラー メッセージ](../core/fault-messages.md) </span><span class="sxs-lookup"><span data-stu-id="09735-122">[Fault Messages](../core/fault-messages.md) </span></span>  
 [<span data-ttu-id="09735-123">例外</span><span class="sxs-lookup"><span data-stu-id="09735-123">Exceptions</span></span>](../core/exceptions.md)