---
title: 例外の原因 |Microsoft ドキュメント
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
ms.openlocfilehash: 9006234d71751078269e5a88559839fdadd91e91
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232466"
---
# <a name="causes-of-exceptions"></a><span data-ttu-id="d2807-102">例外の原因</span><span class="sxs-lookup"><span data-stu-id="d2807-102">Causes of Exceptions</span></span>
<span data-ttu-id="d2807-103">次のような場合、オーケストレーション内で例外が生成されることがあります。</span><span class="sxs-lookup"><span data-stu-id="d2807-103">Exceptions can be generated within an orchestration in the following ways:</span></span>  
  
-   <span data-ttu-id="d2807-104">によって、**例外のスロー**図形、直ちに無条件で例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="d2807-104">By a **Throw Exception** shape, which throws an exception immediately and unconditionally.</span></span> <span data-ttu-id="d2807-105">制御が渡される、**例外のスロー**適切な例外ハンドラーに直接図形です。</span><span class="sxs-lookup"><span data-stu-id="d2807-105">Control passes from the **Throw Exception** shape directly to the appropriate exception handler.</span></span>  
  
-   <span data-ttu-id="d2807-106">長時間トランザクションで、タイムアウトが超過した場合。</span><span class="sxs-lookup"><span data-stu-id="d2807-106">By a time-out expiring in a long-running transaction.</span></span> <span data-ttu-id="d2807-107">定義済みのシステム例外 —**Microsoft.XLANG.BaseTypes.TimeOutException**— この場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="d2807-107">A predefined system exception—**Microsoft.XLANG.BaseTypes.TimeOutException**—is thrown in this case.</span></span>  
  
-   <span data-ttu-id="d2807-108">その他のトランザクション エラーが発生した場合。</span><span class="sxs-lookup"><span data-stu-id="d2807-108">By some other transaction failure.</span></span> <span data-ttu-id="d2807-109">これらのエラーには、Microsoft.XLANG.BaseTypes.PersistenceException などのシステム定義のメッセージがランタイム エンジンによりスローされます。</span><span class="sxs-lookup"><span data-stu-id="d2807-109">The runtime engine throws a system-defined message such as Microsoft.XLANG.BaseTypes.PersistenceException for these failures.</span></span>  
  
-   <span data-ttu-id="d2807-110">ユーザー コードの例外が発生した場合。</span><span class="sxs-lookup"><span data-stu-id="d2807-110">By a user code exception.</span></span> <span data-ttu-id="d2807-111">オーケストレーション内で外部のユーザー コードを呼び出したとき、呼び出された共通言語ランタイム クラスが例外をスローすることがあります。</span><span class="sxs-lookup"><span data-stu-id="d2807-111">When calls to external user code are made within an orchestration, common language runtime classes that are called can throw exceptions.</span></span> <span data-ttu-id="d2807-112">こうした例外がユーザー コード内で処理されないと、最終的には、ユーザー コードを呼び出したスコープまで例外が反映されます。</span><span class="sxs-lookup"><span data-stu-id="d2807-112">If these exceptions are not handled in the user code, they eventually propagate up into the scope in which the call to the user code is made.</span></span>  
  
-   <span data-ttu-id="d2807-113">その他のシステム例外が発生した場合 (永続化エラー、型のローダーの例外などの .NET またはシステム例外、データ変換エラーなど)。</span><span class="sxs-lookup"><span data-stu-id="d2807-113">By some other system exception (for example, a persistence failure, another .NET or system exception such as type loader exception, or a data conversion error).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d2807-114">内に、例外型のローダーの例外がスローされると、キャッチされない場合があります、**例外のキャッチ**同じブロック**スコープ**図形です。</span><span class="sxs-lookup"><span data-stu-id="d2807-114">When a type loader exception is thrown, the exception may not be caught in the **Catch Exception** block in the same **Scope** shape.</span></span> <span data-ttu-id="d2807-115">これは、例外が、BizTalk オーケストレーション プロセスではなく型のローダーからスローされるためです。</span><span class="sxs-lookup"><span data-stu-id="d2807-115">This is because of that the exception is from the type loader, not from the BizTalk orchestration process.</span></span> <span data-ttu-id="d2807-116">よって、BizTalk の制御フローのルールが適用されません。</span><span class="sxs-lookup"><span data-stu-id="d2807-116">Therefore, it does not follow the BizTalk rules of control flow.</span></span>  
  
-   <span data-ttu-id="d2807-117">前後のスコープ内の兄弟分岐によって実行が停止された場合。</span><span class="sxs-lookup"><span data-stu-id="d2807-117">By a sibling branch in a surrounding scope halting execution.</span></span> <span data-ttu-id="d2807-118">この場合、各分岐に Microsoft.XLANG.BaseTypes.ForcedTerminationException がスローされるため、それぞれに例外ハンドラーを追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d2807-118">Microsoft.XLANG.BaseTypes.ForcedTerminationException is thrown to each branch in this case, and you might want to add an exception handler to each.</span></span> <span data-ttu-id="d2807-119">このような例外ハンドラーでは、その例外を再スローできません。また、他の種類の例外をスローしようとしないでください。</span><span class="sxs-lookup"><span data-stu-id="d2807-119">Such an exception handler cannot re-throw its exception, nor should it attempt to throw any other type of exception.</span></span>  
  
-   <span data-ttu-id="d2807-120">エラーを示す外部メッセージを受信した場合。</span><span class="sxs-lookup"><span data-stu-id="d2807-120">By receipt of an external message that indicates a fault.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2807-121">参照</span><span class="sxs-lookup"><span data-stu-id="d2807-121">See Also</span></span>  
 <span data-ttu-id="d2807-122">[エラー メッセージ](../core/fault-messages.md) </span><span class="sxs-lookup"><span data-stu-id="d2807-122">[Fault Messages](../core/fault-messages.md) </span></span>  
 [<span data-ttu-id="d2807-123">例外</span><span class="sxs-lookup"><span data-stu-id="d2807-123">Exceptions</span></span>](../core/exceptions.md)