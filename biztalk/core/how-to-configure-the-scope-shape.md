---
title: スコープ図形を構成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: ef17f5d1ab94875af118d17551da4334525535fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249450"
---
# <a name="how-to-configure-the-scope-shape"></a><span data-ttu-id="f88ed-102">スコープ図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="f88ed-102">How to Configure the Scope Shape</span></span>
<span data-ttu-id="f88ed-103">**スコープ**図形は、そのコンテンツの状況に応じたフレームワークを提供します。</span><span class="sxs-lookup"><span data-stu-id="f88ed-103">The **Scope** shape provides a contextual framework for its contents.</span></span> <span data-ttu-id="f88ed-104">最初のブロック、**スコープ**図形はコンテキスト ブロック、つまりボディ部をスコープの基本的なアクションが行わ以外の場合は、try/catch ステートメントの try ブロックと似ています。</span><span class="sxs-lookup"><span data-stu-id="f88ed-104">The first block of a **Scope** shape is the context block, or body, in which the basic actions of the scope take place; it is analogous to the try block in a try/catch statement.</span></span> <span data-ttu-id="f88ed-105">次の本文、**スコープ**図形には、1 つまたは複数の例外ハンドラー ブロックや補正ブロックもを含めることがあります。</span><span class="sxs-lookup"><span data-stu-id="f88ed-105">Following the body, the **Scope** shape may also include one or more exception-handler blocks and a compensation block.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f88ed-106">複数コンピューター環境で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]世界協定時刻 (UTC) が 2 つのコンピューターで異なる場合は、SQL Server を別のコンピューターに配置し、**タイムアウト**プロパティ、用に構成します。**スコープ**図形を UTC 時間であるために予想よりも前にトリガーを取得可能性があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SQL Server マシンが同期されていないとします。</span><span class="sxs-lookup"><span data-stu-id="f88ed-106">In a multiple machine environment where [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and SQL Server are located on different machines, if the Coordinated Universal Time (UTC) is different on the two machines then the **Timeout** property you configure for the **Scope** shape may get triggered earlier than expected because of the UTC time on [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and SQL Server machines is unsynchronized.</span></span> <span data-ttu-id="f88ed-107">これはタイム ゾーンの問題ではありません。なぜなら、協定世界時はタイム ゾーンに影響されないからです。</span><span class="sxs-lookup"><span data-stu-id="f88ed-107">Note that this is not a time zones issue as Coordinated Universal Time is unaffected by time zones.</span></span>  
  
### <a name="to-configure-a-scope-shape-as-a-transaction-boundary"></a><span data-ttu-id="f88ed-108">スコープ図形をトランザクション境界として構成するには</span><span class="sxs-lookup"><span data-stu-id="f88ed-108">To configure a Scope shape as a transaction boundary</span></span>  
  
1.  <span data-ttu-id="f88ed-109">[プロパティ] ウィンドウで、設定、**トランザクションの種類**プロパティを**Atomic**または**長時間**です。</span><span class="sxs-lookup"><span data-stu-id="f88ed-109">In the Properties window, set the **Transaction Type** property to **Atomic** or **Long Running**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f88ed-110">[トランザクションの種類] を [アトミック] または [長時間トランザクション] に設定するには、オーケストレーション自体が長時間トランザクションであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="f88ed-110">The orchestration must itself be a long-running transaction in order for you to set the Transaction Type to Atomic or Long Running.</span></span>  
  
2.  <span data-ttu-id="f88ed-111">場合、**トランザクションの種類**に設定されている**Atomic**、[プロパティ] ウィンドウで、次のプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="f88ed-111">If the **Transaction Type** is set to **Atomic**, then in the Properties window, specify the following properties:</span></span>  
  
    |<span data-ttu-id="f88ed-112">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f88ed-112">Property</span></span>|<span data-ttu-id="f88ed-113">Description</span><span class="sxs-lookup"><span data-stu-id="f88ed-113">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="f88ed-114">Batch</span><span class="sxs-lookup"><span data-stu-id="f88ed-114">Batch</span></span>|<span data-ttu-id="f88ed-115">このトランザクションと他のトランザクションをオーケストレーションの複数のインスタンスにまたがってバッチ処理できるかどうかを決定するブール値。</span><span class="sxs-lookup"><span data-stu-id="f88ed-115">Boolean value that determines if this transaction can be batched with other transactions across multiple instances of the orchestration.</span></span> <span data-ttu-id="f88ed-116">BizTalk Server では、オーケストレーションの複数のインスタンスにまたがるアトミック トランザクションのバッチ処理がサポートされません。したがって、BizTalk Server では、このプロパティは使用できません。</span><span class="sxs-lookup"><span data-stu-id="f88ed-116">This property is never used in BizTalk Server because BizTalk Server does not support batching atomic transactions across multiple instances of orchestrations.</span></span> <span data-ttu-id="f88ed-117">このプロパティは、将来のリリースで廃止される予定です。</span><span class="sxs-lookup"><span data-stu-id="f88ed-117">This property will be deprecated in the future release.</span></span>|  
    |<span data-ttu-id="f88ed-118">[分離レベル]</span><span class="sxs-lookup"><span data-stu-id="f88ed-118">Isolation Level</span></span>|<span data-ttu-id="f88ed-119">同時実行トランザクション間でアクセスできるデータのレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="f88ed-119">Determines the degree to which data is accessible among concurrent transactions:</span></span><br /><br /> <span data-ttu-id="f88ed-120">-Read Committed-選択したトランザクションがコミットされるまでの同時実行トランザクションで変更されたデータへのアクセスを防ぐためにします。</span><span class="sxs-lookup"><span data-stu-id="f88ed-120">-   Read Committed—To prevent the selected transaction from accessing data modifications in concurrent transactions until they are committed.</span></span> <span data-ttu-id="f88ed-121">このオプションは Microsoft SQL Server の既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="f88ed-121">This option is the Microsoft SQL Server default setting.</span></span><br /><span data-ttu-id="f88ed-122">-Repeatable Read-選択したトランザクションが完了するまで、読み取りロックを要求するようにします。</span><span class="sxs-lookup"><span data-stu-id="f88ed-122">-   Repeatable Read—To require read locks until the selected transaction is complete.</span></span><br /><span data-ttu-id="f88ed-123">化シリアルなど、同時実行トランザクションから選択したトランザクションが完了するまでデータを変更します。</span><span class="sxs-lookup"><span data-stu-id="f88ed-123">-   Serializable—To prevent concurrent transactions from making data modifications until the selected transaction is complete.</span></span> <span data-ttu-id="f88ed-124">このオプションは最も制限された分離レベルになります。</span><span class="sxs-lookup"><span data-stu-id="f88ed-124">This option is the most restrictive isolation level.</span></span>|  
    |<span data-ttu-id="f88ed-125">[再試行]</span><span class="sxs-lookup"><span data-stu-id="f88ed-125">Retry</span></span>|<span data-ttu-id="f88ed-126">エラーが発生したときに、このトランザクションを再試行するかどうかを決定するブール値。</span><span class="sxs-lookup"><span data-stu-id="f88ed-126">Boolean value that determines whether this transaction is retried when an error occurs.</span></span> <span data-ttu-id="f88ed-127">既定値は **True**です。</span><span class="sxs-lookup"><span data-stu-id="f88ed-127">The default value is **True**.</span></span> <span data-ttu-id="f88ed-128">**注:** Microsoft.XLANG.BaseTypes.RetryTransactionException をスローする場合、またはオーケストレーション エンジンがその状態を保管するため、トランザクションをコミットできない場合、アトミック トランザクションは再試行されます。</span><span class="sxs-lookup"><span data-stu-id="f88ed-128">**Note:**  An atomic transaction will be retried if you throw Microsoft.XLANG.BaseTypes.RetryTransactionException, or if the orchestration engine is unable to store its state or commit the transaction.</span></span>|  
    |<span data-ttu-id="f88ed-129">Timeout</span><span class="sxs-lookup"><span data-stu-id="f88ed-129">Timeout</span></span>|<span data-ttu-id="f88ed-130">トランザクションが非アクティブな場合にエラーを発生させるまでの時間を秒単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="f88ed-130">Determines the time in seconds until the transaction fails due to inactivity.</span></span> <span data-ttu-id="f88ed-131">タイムアウトを使用したくない場合は、このプロパティの値を 0 に設定します。</span><span class="sxs-lookup"><span data-stu-id="f88ed-131">If you do not want to use a timeout, set the value of this property to 0.</span></span> <span data-ttu-id="f88ed-132">**注:** この DTC タイムアウトでは、オーケストレーション エンジンでは適用されません。</span><span class="sxs-lookup"><span data-stu-id="f88ed-132">**Note:**  This is a DTC timeout, and is not enforced by the orchestration engine.</span></span> <span data-ttu-id="f88ed-133">アトミック トランザクションの場合のみ、エンジンはトランザクションを中断しません。</span><span class="sxs-lookup"><span data-stu-id="f88ed-133">For atomic transactions only, the engine will not interrupt the transaction.</span></span> <span data-ttu-id="f88ed-134">エンジンは、DTC トランザクション内のいずれかのオブジェクトを介して DTC トランザクションに参加している場合のみ、コミットまで通常どおり処理し、コミット時にエラーを発生させます。</span><span class="sxs-lookup"><span data-stu-id="f88ed-134">It proceeds normally until commitment, at which point it fails to commit only if participating in a DTC transaction through one of the objects inside it.</span></span>|  
  
3.  <span data-ttu-id="f88ed-135">場合、**トランザクションの種類**に設定されている**長時間**、[プロパティ] ウィンドウで、次のプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="f88ed-135">If the **Transaction Type** is set to **Long Running**, then in the Properties window, specify the following property:</span></span>  
  
    |<span data-ttu-id="f88ed-136">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f88ed-136">Property</span></span>|<span data-ttu-id="f88ed-137">Description</span><span class="sxs-lookup"><span data-stu-id="f88ed-137">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="f88ed-138">Timeout</span><span class="sxs-lookup"><span data-stu-id="f88ed-138">Timeout</span></span>|<span data-ttu-id="f88ed-139">トランザクションがタイムアウトし、失敗したトランザクションと見なされるまでの時間を秒単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="f88ed-139">Determines the time in seconds until the transaction times out and is considered a failed transaction.</span></span> <span data-ttu-id="f88ed-140">タイムアウトを使用したくない場合は、このプロパティの値を 0 に設定します。</span><span class="sxs-lookup"><span data-stu-id="f88ed-140">If you do not want to use a timeout, set the value of this property to 0.</span></span>|  
  
### <a name="to-configure-a-scope-shape-to-contain-local-variables"></a><span data-ttu-id="f88ed-141">ローカル変数を格納するスコープ図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="f88ed-141">To configure a Scope shape to contain local variables</span></span>  
  
1.  <span data-ttu-id="f88ed-142">オーケストレーションの種類 ウィンドウでスコープをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="f88ed-142">Double-click the scope in the Orchestration View window.</span></span>  
  
2.  <span data-ttu-id="f88ed-143">[スコープ]、[変数] フォルダーを右クリックし、をクリックして**新しい変数**です。</span><span class="sxs-lookup"><span data-stu-id="f88ed-143">Right-click the Variables folder under the scope and then click **New Variable**.</span></span>  
  
3.  <span data-ttu-id="f88ed-144">「変数を追加するには」で、手順 2. を進める[オーケストレーション変数の追加方法](../core/how-to-add-orchestration-variables.md)です。</span><span class="sxs-lookup"><span data-stu-id="f88ed-144">Proceed from step 2 in "To add a variable" in [How to Add Orchestration Variables](../core/how-to-add-orchestration-variables.md).</span></span>