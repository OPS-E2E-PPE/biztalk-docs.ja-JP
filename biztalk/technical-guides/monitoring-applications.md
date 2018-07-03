---
title: アプリケーションの監視 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4be98ba2-6acd-4dee-b6ea-db71bbd368f0
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d1a7e4e0d4cb0f4e6899159da6c6c06a83e9165
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010299"
---
# <a name="monitoring-applications"></a><span data-ttu-id="c65e0-102">アプリケーションの監視</span><span class="sxs-lookup"><span data-stu-id="c65e0-102">Monitoring Applications</span></span>
<span data-ttu-id="c65e0-103">BizTalk を監視するための Microsoft System Center Operations Manager の設定アプリケーション通常できますに細分化プログレッシブ 4 段階のプロセスには、次のように。</span><span class="sxs-lookup"><span data-stu-id="c65e0-103">Setting up Microsoft System Center Operations Manager to monitor BizTalk applications typically can be broken down into a progressive four-step process as follows:</span></span>  
  
1. <span data-ttu-id="c65e0-104">**既存の規則またはカスタムの BizTalk アプリケーションを監視するカスタム管理パックにルールのコピーを変更します。**</span><span class="sxs-lookup"><span data-stu-id="c65e0-104">**Modify existing rules and/or copy rules to a custom management pack to monitor a custom BizTalk application**</span></span>  
  
    <span data-ttu-id="c65e0-105">これらのルールの多くに複数回をコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c65e0-105">You will need to copy many of these rules multiple times.</span></span> <span data-ttu-id="c65e0-106">これは、たとえば、ファイル共有数を監視している場合に大文字と小文字です。</span><span class="sxs-lookup"><span data-stu-id="c65e0-106">This is the case if you are monitoring a number of file shares, for example.</span></span> <span data-ttu-id="c65e0-107">説明 フィールドに追加され、ファイル共有のアドレスでファイル共有ごとに 1 回ベースのルールをコピーするこのシナリオで、**条件**の規則 タブ。</span><span class="sxs-lookup"><span data-stu-id="c65e0-107">In this scenario, you would copy the base rule once for each file share with the file share address added in the description field on the **Criteria** tab of the rule.</span></span> <span data-ttu-id="c65e0-108">アドレスを追加すると、Operations Manager に個々 のファイル共有ごとのアラートが発生します。</span><span class="sxs-lookup"><span data-stu-id="c65e0-108">By adding the address, Operations Manager will raise an alert for each individual file share.</span></span> <span data-ttu-id="c65e0-109">既存のルールをコピーする場合は、選択するようにして**を有効にする**ルールを無効には、この規則のオーバーライドまたは重複するアラートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c65e0-109">When you copy an existing rule, ensure that you select **Enable** rule-disable overrides for this rule or you will receive duplicate alerts.</span></span>  
  
    <span data-ttu-id="c65e0-110">他の項目を作成する各ルールに追加する必要がありますにはサポート技術情報、**技術**の規則のプロパティ タブ。</span><span class="sxs-lookup"><span data-stu-id="c65e0-110">Another item that you should add to each rule that you create is Knowledge information on the **Knowledge Base** tab of the rule property.</span></span> <span data-ttu-id="c65e0-111">このデータは、Operations Manager アラートを送信するときに発生する通知にアタッチされます。</span><span class="sxs-lookup"><span data-stu-id="c65e0-111">This data is attached to the notification that is raised when Operations Manager sends out an alert.</span></span> <span data-ttu-id="c65e0-112">エラーを解決するのに役立つ手順を含める場合、この機能の能力が明らかになります。</span><span class="sxs-lookup"><span data-stu-id="c65e0-112">The power of this feature becomes clear when you include steps that may help resolve the error.</span></span>  
  
2. <span data-ttu-id="c65e0-113">**定義された各ルールのアクションを作成します。**</span><span class="sxs-lookup"><span data-stu-id="c65e0-113">**Create actions for each defined rule**</span></span>  
  
    <span data-ttu-id="c65e0-114">作成またはルールのコピーは、プロセスの最初の手順では本当に。</span><span class="sxs-lookup"><span data-stu-id="c65e0-114">Creating or copying a rule is really the first step in the process.</span></span> <span data-ttu-id="c65e0-115">次の手順では、そのルールに基づくアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="c65e0-115">The next step is to take some action based on that rule.</span></span> <span data-ttu-id="c65e0-116">ある場合アクションに基づいてルールを本当にいてもイベントがこれまで監視されています。</span><span class="sxs-lookup"><span data-stu-id="c65e0-116">If there is no action based on a rule then it doesn’t really matter that the event was ever monitored.</span></span> <span data-ttu-id="c65e0-117">最も頻繁に実行されるアクションが、警告、オペレーターや管理者にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="c65e0-117">The action most frequently taken is to alert an operator or administrator that an error has occurred.</span></span> <span data-ttu-id="c65e0-118">Operations Manager には、さまざまなイベントがトリガーされたときに使用できるその他のアクションも提供します。</span><span class="sxs-lookup"><span data-stu-id="c65e0-118">Operations Manager also provides a number of other actions that can be used when an event is triggered.</span></span> <span data-ttu-id="c65e0-119">これらのアクションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c65e0-119">These actions include:</span></span>  
  
   -   <span data-ttu-id="c65e0-120">スクリプトの開始</span><span class="sxs-lookup"><span data-stu-id="c65e0-120">Starting a script</span></span>  
  
   -   <span data-ttu-id="c65e0-121">簡易ネットワーク管理プロトコル (SNMP) トラップを送信する (、SNMP のエージェントのアクティビティを監視、ネットワークとネットワーク コンソール ワークステーションにレポートをさまざまなデバイス)</span><span class="sxs-lookup"><span data-stu-id="c65e0-121">Sending a Simple Network Management Protocol (SNMP) trap (in SNMP, agents monitor the activity in the various devices on the network and report to the network console workstation)</span></span>  
  
   -   <span data-ttu-id="c65e0-122">通知グループへの通知の送信</span><span class="sxs-lookup"><span data-stu-id="c65e0-122">Sending a notification to a Notification group</span></span>  
  
   -   <span data-ttu-id="c65e0-123">コマンドまたはバッチ ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="c65e0-123">Executing a command or batch file</span></span>  
  
   -   <span data-ttu-id="c65e0-124">状態変数を更新しています</span><span class="sxs-lookup"><span data-stu-id="c65e0-124">Updating a state variable</span></span>  
  
   -   <span data-ttu-id="c65e0-125">ファイルを転送します。</span><span class="sxs-lookup"><span data-stu-id="c65e0-125">Transferring a file</span></span>  
  
   -   <span data-ttu-id="c65e0-126">マネージ コード アセンブリでメソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="c65e0-126">Calling a method on a managed code assembly</span></span>  
  
3. <span data-ttu-id="c65e0-127">**手動のタスクを自動化する、反復的なプロセスを作成します。**</span><span class="sxs-lookup"><span data-stu-id="c65e0-127">**Create iterative processes to automate manual tasks**</span></span>  
  
    <span data-ttu-id="c65e0-128">[次へ] の手順では、反復プロセスですし、基本的な警告メカニズムを超えた位置に移動します。</span><span class="sxs-lookup"><span data-stu-id="c65e0-128">The next step is an iterative process and moves beyond the basic alerting mechanism.</span></span> <span data-ttu-id="c65e0-129">Operations manager がスクリプトと .NET コードの両方を呼び出すことで発生したイベントに基づいて手動のタスクを自動化するプロセスは、強力かつ時間保存する機能です。</span><span class="sxs-lookup"><span data-stu-id="c65e0-129">With Operations Manager able to invoke both script and .NET code, the process of automating manual tasks based on raised events is a powerful and time saving feature.</span></span> <span data-ttu-id="c65e0-130">この例では、無効になっている/停止イベント メッセージが記録された場合、ポートを自動的に起動するスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="c65e0-130">An example of this is to run a script to automatically start a port if a disabled /stopped event message is logged.</span></span> <span data-ttu-id="c65e0-131">このプロセスは、多くのプロセスを自動化するために反復的なです。</span><span class="sxs-lookup"><span data-stu-id="c65e0-131">This process is iterative since many processes can be automated.</span></span>  
  
4. <span data-ttu-id="c65e0-132">**しきい値規則を使用して、手動のタスクを自動化するには**</span><span class="sxs-lookup"><span data-stu-id="c65e0-132">**Use threshold rules to automate manual tasks**</span></span>  
  
    <span data-ttu-id="c65e0-133">処理の次の手順では、事後対応型のアラートだけにとどまらないし、しきい値規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="c65e0-133">The next step in processing is to move beyond the reactive alerting and use threshold rules.</span></span> <span data-ttu-id="c65e0-134">BizTalk Server 管理パックでは、既定では、しきい値ルールは含まれません。</span><span class="sxs-lookup"><span data-stu-id="c65e0-134">The BizTalk Server Management Pack does not contain any threshold rules by default.</span></span> <span data-ttu-id="c65e0-135">このような規則は通常、カスタム アプリケーションに固有とすべてのアプリケーションで異なるためにです。</span><span class="sxs-lookup"><span data-stu-id="c65e0-135">This is because such rules are typically specific to the custom application and are different for every application.</span></span> <span data-ttu-id="c65e0-136">しきい値は、カスタムのアプリケーションに関するビジネス ルールを取り入れた、システムの監視の事前対応型の手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="c65e0-136">A threshold embodies a business rule regarding the custom application and provides a proactive means of monitoring a system.</span></span> <span data-ttu-id="c65e0-137">使用することができます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ルールを定義するパフォーマンスの分析ログ (PAL) のツールで提供されているしきい値テンプレート。</span><span class="sxs-lookup"><span data-stu-id="c65e0-137">You can use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] threshold templates provided with the Performance Analysis of Logs (PAL) tool to define rules.</span></span>  
  
    <span data-ttu-id="c65e0-138">このようなしきい値ルールの例では、サーバー上の Cpu が一貫して特定の期間の 75% を超えた実行時に測定します。</span><span class="sxs-lookup"><span data-stu-id="c65e0-138">An example of such a threshold rule is to measure when the CPUs on a server consistently run above 75 percent for a specific time period.</span></span> <span data-ttu-id="c65e0-139">システムのスケール アウトする必要がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c65e0-139">This could indicate that you need to scale out the system.</span></span> <span data-ttu-id="c65e0-140">まだ別の例では、一意な一連のカウンターを監視するしきい値ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="c65e0-140">Yet another example is where you create a threshold rule that monitors a unique set of counters.</span></span> <span data-ttu-id="c65e0-141">このルールでは、高い需要の期間中に以前に構成されたバックアップ サーバー上の BizTalk ホスト インスタンスを初期化するコードを呼び出すことができます、します。</span><span class="sxs-lookup"><span data-stu-id="c65e0-141">This rule could then invoke code to initialize BizTalk host instances on a previously configured backup server during periods of high demand.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c65e0-142">参照</span><span class="sxs-lookup"><span data-stu-id="c65e0-142">See Also</span></span>  
 [<span data-ttu-id="c65e0-143">System Center Operations Manager 2007 による BizTalk Server の監視</span><span class="sxs-lookup"><span data-stu-id="c65e0-143">Monitoring BizTalk Server with System Center Operations Manager 2007</span></span>](../technical-guides/monitoring-biztalk-server-with-system-center-operations-manager-2007.md)