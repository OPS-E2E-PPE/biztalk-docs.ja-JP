---
title: スコープ図形を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scope shape [Orchestration Designer], about Scope shape
- Scope shape [Orchestration Designer], configuring
- Scope shape [Orchestration Designer], variables
- Scope shape [Orchestration Designer]
- configuring [Orchestration Designer], Scope shape
- Scope shape [Orchestration Designer], transactions
ms.assetid: 3c518db0-d68c-4f72-9d5c-48540811e289
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5627f3463b1d2797abe742462cf60e948e8bbb37
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340415"
---
# <a name="how-to-configure-the-scope-shape"></a><span data-ttu-id="61cb8-102">スコープ図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="61cb8-102">How to Configure the Scope Shape</span></span>
<span data-ttu-id="61cb8-103">**スコープ**図形は、その内容に状況に応じたフレームワークを提供します。</span><span class="sxs-lookup"><span data-stu-id="61cb8-103">The **Scope** shape provides a contextual framework for its contents.</span></span> <span data-ttu-id="61cb8-104">最初のブロックを**スコープ**図形はコンテキスト ブロック、つまりボディ、これで、スコープの基本的な操作が行わ; try/catch ステートメントの try ブロックと似ています。</span><span class="sxs-lookup"><span data-stu-id="61cb8-104">The first block of a **Scope** shape is the context block, or body, in which the basic actions of the scope take place; it is analogous to the try block in a try/catch statement.</span></span> <span data-ttu-id="61cb8-105">、ボディ部に続いて、**スコープ**図形が 1 つまたは複数の例外ハンドラー ブロックや補正ブロックに含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="61cb8-105">Following the body, the **Scope** shape may also include one or more exception-handler blocks and a compensation block.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61cb8-106">複数マシン環境で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]世界協定時刻 (UTC) が 2 台のコンピューターと異なる場合、SQL Server が別のコンピューターに存在し、**タイムアウト**プロパティ、用に構成します。**スコープ**図形で UTC 時間であるために予想よりも早くトリガーが[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と SQL Server マシンは同期されていません。</span><span class="sxs-lookup"><span data-stu-id="61cb8-106">In a multiple machine environment where [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and SQL Server are located on different machines, if the Coordinated Universal Time (UTC) is different on the two machines then the **Timeout** property you configure for the **Scope** shape may get triggered earlier than expected because of the UTC time on [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and SQL Server machines is unsynchronized.</span></span> <span data-ttu-id="61cb8-107">ないタイム ゾーンの問題を世界協定時刻が影響を受けることは、タイム ゾーンではないために注意してください。</span><span class="sxs-lookup"><span data-stu-id="61cb8-107">Note that this is not a time zones issue as Coordinated Universal Time is unaffected by time zones.</span></span>  
  
### <a name="to-configure-a-scope-shape-as-a-transaction-boundary"></a><span data-ttu-id="61cb8-108">スコープ図形をトランザクション境界として構成するには</span><span class="sxs-lookup"><span data-stu-id="61cb8-108">To configure a Scope shape as a transaction boundary</span></span>  
  
1.  <span data-ttu-id="61cb8-109">[プロパティ] ウィンドウで次のように設定します。、**トランザクションの種類**プロパティを**アトミック**または**長時間**します。</span><span class="sxs-lookup"><span data-stu-id="61cb8-109">In the Properties window, set the **Transaction Type** property to **Atomic** or **Long Running**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="61cb8-110">オーケストレーション自体もをアトミックまたは長時間トランザクションの種類を設定するために、実行時間の長いトランザクション。</span><span class="sxs-lookup"><span data-stu-id="61cb8-110">The orchestration must itself be a long-running transaction in order for you to set the Transaction Type to Atomic or Long Running.</span></span>  
  
2.  <span data-ttu-id="61cb8-111">場合、**トランザクションの種類**に設定されている**アトミック**、し、[プロパティ] ウィンドウで、次のプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="61cb8-111">If the **Transaction Type** is set to **Atomic**, then in the Properties window, specify the following properties:</span></span>  
  
    |<span data-ttu-id="61cb8-112">プロパティ</span><span class="sxs-lookup"><span data-stu-id="61cb8-112">Property</span></span>|<span data-ttu-id="61cb8-113">説明</span><span class="sxs-lookup"><span data-stu-id="61cb8-113">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="61cb8-114">Batch (バッチ)</span><span class="sxs-lookup"><span data-stu-id="61cb8-114">Batch</span></span>|<span data-ttu-id="61cb8-115">このトランザクションをオーケストレーションの複数のインスタンスの他のトランザクションとバッチことができるかどうかを決定するブール値。</span><span class="sxs-lookup"><span data-stu-id="61cb8-115">Boolean value that determines if this transaction can be batched with other transactions across multiple instances of the orchestration.</span></span> <span data-ttu-id="61cb8-116">BizTalk Server は、アトミック トランザクションをバッチ処理オーケストレーションの複数のインスタンスをサポートしていないために、このプロパティは BizTalk Server で使用されません。</span><span class="sxs-lookup"><span data-stu-id="61cb8-116">This property is never used in BizTalk Server because BizTalk Server does not support batching atomic transactions across multiple instances of orchestrations.</span></span> <span data-ttu-id="61cb8-117">このプロパティは、将来のリリースで非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="61cb8-117">This property will be deprecated in the future release.</span></span>|  
    |<span data-ttu-id="61cb8-118">[分離レベル]</span><span class="sxs-lookup"><span data-stu-id="61cb8-118">Isolation Level</span></span>|<span data-ttu-id="61cb8-119">データの同時実行トランザクション間でアクセスできる程度を決定します。</span><span class="sxs-lookup"><span data-stu-id="61cb8-119">Determines the degree to which data is accessible among concurrent transactions:</span></span><br /><br /> <span data-ttu-id="61cb8-120">-Read Committed などを選択したトランザクションがコミットされるまでの同時実行トランザクションで変更されたデータへのアクセスを防ぐためにします。</span><span class="sxs-lookup"><span data-stu-id="61cb8-120">-   Read Committed—To prevent the selected transaction from accessing data modifications in concurrent transactions until they are committed.</span></span> <span data-ttu-id="61cb8-121">このオプションは、Microsoft SQL Server の既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="61cb8-121">This option is the Microsoft SQL Server default setting.</span></span><br /><span data-ttu-id="61cb8-122">不能反復読み取り、選択したトランザクションが完了するまで、読み取りロックを要求するようにします。</span><span class="sxs-lookup"><span data-stu-id="61cb8-122">-   Repeatable Read—To require read locks until the selected transaction is complete.</span></span><br /><span data-ttu-id="61cb8-123">シリアル化できる、同時実行トランザクションから、選択したトランザクションが完了するまでデータを変更します。</span><span class="sxs-lookup"><span data-stu-id="61cb8-123">-   Serializable—To prevent concurrent transactions from making data modifications until the selected transaction is complete.</span></span> <span data-ttu-id="61cb8-124">このオプションは、最も制限の厳しい分離レベルです。</span><span class="sxs-lookup"><span data-stu-id="61cb8-124">This option is the most restrictive isolation level.</span></span>|  
    |<span data-ttu-id="61cb8-125">[再試行]</span><span class="sxs-lookup"><span data-stu-id="61cb8-125">Retry</span></span>|<span data-ttu-id="61cb8-126">エラーが発生したときに、このトランザクションを再試行するかどうかを決定するブール値。</span><span class="sxs-lookup"><span data-stu-id="61cb8-126">Boolean value that determines whether this transaction is retried when an error occurs.</span></span> <span data-ttu-id="61cb8-127">既定値は **True**です。</span><span class="sxs-lookup"><span data-stu-id="61cb8-127">The default value is **True**.</span></span> <span data-ttu-id="61cb8-128">**注:** Microsoft.XLANG.BaseTypes.RetryTransactionException をスローする場合、またはオーケストレーション エンジンがその状態を保管するため、トランザクションをコミットできない場合は、アトミックのトランザクションが再試行されます。</span><span class="sxs-lookup"><span data-stu-id="61cb8-128">**Note:**  An atomic transaction will be retried if you throw Microsoft.XLANG.BaseTypes.RetryTransactionException, or if the orchestration engine is unable to store its state or commit the transaction.</span></span>|  
    |<span data-ttu-id="61cb8-129">Timeout</span><span class="sxs-lookup"><span data-stu-id="61cb8-129">Timeout</span></span>|<span data-ttu-id="61cb8-130">非アクティブなトランザクションが失敗するまでの秒単位の時間を決定します。</span><span class="sxs-lookup"><span data-stu-id="61cb8-130">Determines the time in seconds until the transaction fails due to inactivity.</span></span> <span data-ttu-id="61cb8-131">タイムアウトを使用しない場合は、このプロパティの値を 0 に設定します。</span><span class="sxs-lookup"><span data-stu-id="61cb8-131">If you do not want to use a timeout, set the value of this property to 0.</span></span> <span data-ttu-id="61cb8-132">**注:** これは、DTC タイムアウトであり、オーケストレーション エンジンによっては適用されません。</span><span class="sxs-lookup"><span data-stu-id="61cb8-132">**Note:**  This is a DTC timeout, and is not enforced by the orchestration engine.</span></span> <span data-ttu-id="61cb8-133">アトミック トランザクションのみの場合、エンジンは、トランザクションを中断しません。</span><span class="sxs-lookup"><span data-stu-id="61cb8-133">For atomic transactions only, the engine will not interrupt the transaction.</span></span> <span data-ttu-id="61cb8-134">通常、内のオブジェクトのいずれかで DTC トランザクションに参加している場合にのみコミットに失敗した時点で、コミットされるまで進行します。</span><span class="sxs-lookup"><span data-stu-id="61cb8-134">It proceeds normally until commitment, at which point it fails to commit only if participating in a DTC transaction through one of the objects inside it.</span></span>|  
  
3.  <span data-ttu-id="61cb8-135">場合、**トランザクションの種類**に設定されている**長時間**、[プロパティ] ウィンドウで、次のプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="61cb8-135">If the **Transaction Type** is set to **Long Running**, then in the Properties window, specify the following property:</span></span>  
  
    |<span data-ttu-id="61cb8-136">プロパティ</span><span class="sxs-lookup"><span data-stu-id="61cb8-136">Property</span></span>|<span data-ttu-id="61cb8-137">説明</span><span class="sxs-lookup"><span data-stu-id="61cb8-137">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="61cb8-138">Timeout</span><span class="sxs-lookup"><span data-stu-id="61cb8-138">Timeout</span></span>|<span data-ttu-id="61cb8-139">トランザクションがタイムアウトになると、失敗したトランザクションと見なされますまでの秒単位の時間を決定します。</span><span class="sxs-lookup"><span data-stu-id="61cb8-139">Determines the time in seconds until the transaction times out and is considered a failed transaction.</span></span> <span data-ttu-id="61cb8-140">タイムアウトを使用しない場合は、このプロパティの値を 0 に設定します。</span><span class="sxs-lookup"><span data-stu-id="61cb8-140">If you do not want to use a timeout, set the value of this property to 0.</span></span>|  
  
### <a name="to-configure-a-scope-shape-to-contain-local-variables"></a><span data-ttu-id="61cb8-141">ローカル変数を格納するスコープ図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="61cb8-141">To configure a Scope shape to contain local variables</span></span>  
  
1.  <span data-ttu-id="61cb8-142">オーケストレーションの種類 ウィンドウでスコープをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="61cb8-142">Double-click the scope in the Orchestration View window.</span></span>  
  
2.  <span data-ttu-id="61cb8-143">[スコープ]、[変数] フォルダーを右クリックし、をクリックし、**新しい変数**します。</span><span class="sxs-lookup"><span data-stu-id="61cb8-143">Right-click the Variables folder under the scope and then click **New Variable**.</span></span>  
  
3.  <span data-ttu-id="61cb8-144">手順 2.「変数を追加するには」に進める[オーケストレーション変数の追加方法](../core/how-to-add-orchestration-variables.md)します。</span><span class="sxs-lookup"><span data-stu-id="61cb8-144">Proceed from step 2 in "To add a variable" in [How to Add Orchestration Variables](../core/how-to-add-orchestration-variables.md).</span></span>