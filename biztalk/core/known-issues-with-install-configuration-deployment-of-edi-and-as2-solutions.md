---
title: インストール、構成、および EDI および AS2 ソリューションの配置に関する既知の問題 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2dee03f0-2447-4cc2-90f4-e9b73caa0f39
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 406e69cafd4822a0f8f436b471d53c4e815dce32
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262802"
---
# <a name="known-issues-with-installation-configuration-and-deployment-of-edi-and-as2-solutions"></a><span data-ttu-id="2be98-102">EDI ソリューションおよび AS2 ソリューションのインストール、構成、および展開に関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="2be98-102">Known Issues with Installation, Configuration, and Deployment of EDI and AS2 Solutions</span></span>
<span data-ttu-id="2be98-103">このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI ソリューションおよび AS2 ソリューションの展開および管理に関する既知の問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="2be98-103">This topic describes known issues with deployment and management of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI and AS2 solutions.</span></span>  
  
## <a name="blank-strings-were-imported-for-party-properties"></a><span data-ttu-id="2be98-104">パーティのプロパティに空白の文字列がインポートされる</span><span class="sxs-lookup"><span data-stu-id="2be98-104">Blank Strings Were Imported for Party Properties</span></span>  
 <span data-ttu-id="2be98-105">**現象**</span><span class="sxs-lookup"><span data-stu-id="2be98-105">**Symptom**</span></span>  
  
 <span data-ttu-id="2be98-106">バインド ファイルから BizTalk アプリケーションに EDI/AS2 バインドをインポートすると、パスワード、セキュリティ情報、認証情報など、機密性が高いパーティ プロパティがインポートされない。</span><span class="sxs-lookup"><span data-stu-id="2be98-106">When you imported EDI/AS2 bindings from a binding file into a BizTalk application, sensitive party properties, such as passwords or security/authentication information, were not imported.</span></span> <span data-ttu-id="2be98-107">これらのプロパティは空白の文字列に設定される。</span><span class="sxs-lookup"><span data-stu-id="2be98-107">Those properties were set to blank strings.</span></span>  
  
 <span data-ttu-id="2be98-108">**考えられる原因**</span><span class="sxs-lookup"><span data-stu-id="2be98-108">**Possible Cause**</span></span>  
  
 <span data-ttu-id="2be98-109">BizTalk Server では、機密性の高いフィールドの設定はインポートされません。</span><span class="sxs-lookup"><span data-stu-id="2be98-109">BizTalk Server will not import the settings of sensitive fields.</span></span> <span data-ttu-id="2be98-110">これらの設定をインポートすると、セキュリティ上の問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2be98-110">Importing those settings could create a security issue.</span></span>  
  
 <span data-ttu-id="2be98-111">**解決策**</span><span class="sxs-lookup"><span data-stu-id="2be98-111">**Resolution**</span></span>  
  
 <span data-ttu-id="2be98-112">バインドを別のコンピューターにインポートした後、EDI の機密性の高いフィールドに値を手動で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2be98-112">You must manually set the values for EDI sensitive fields after importing the bindings onto another computer.</span></span>  
  
## <a name="ftp-adapter-is-not-supported-natively-in-64-bit-mode"></a><span data-ttu-id="2be98-113">FTP アダプターがネイティブの 64 ビット モードで使用できない</span><span class="sxs-lookup"><span data-stu-id="2be98-113">FTP Adapter Is Not Supported Natively in 64-bit Mode</span></span>  
 <span data-ttu-id="2be98-114">FTP アダプターは、ネイティブの 64 ビット モードでは実行できません。</span><span class="sxs-lookup"><span data-stu-id="2be98-114">The FTP adapter cannot run in native 64-bit mode.</span></span> <span data-ttu-id="2be98-115">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の EDI ソリューションで FTP アダプターを使用する場合、64 ビット Windows の WOW64 で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2be98-115">If you use an FTP adapter in your EDI solution in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you will have to run it on WOW64 on 64-bit Windows.</span></span>  
  
## <a name="some-edias2-artifacts-are-still-active-after-unconfiguring"></a><span data-ttu-id="2be98-116">一部の EDI/AS2 アイテムが構成解除した後もアクティブになっている</span><span class="sxs-lookup"><span data-stu-id="2be98-116">Some EDI/AS2 Artifacts Are Still Active After Unconfiguring</span></span>  
 <span data-ttu-id="2be98-117">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の Microsoft EDI/AS2 機能を構成解除した後、EDI 処理および AS2 処理に関連する一部の BizTalk Server アイテムが、BizTalk グループ構成のコンテキストにおいてアクティブのままとなります。</span><span class="sxs-lookup"><span data-stu-id="2be98-117">After you unconfigure the Microsoft EDI/AS2 feature of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], some BizTalk Server artifacts related to EDI and AS2 processing will still be active in the context of the BizTalk group configuration.</span></span> <span data-ttu-id="2be98-118">これらのアイテムには、EDI パイプライン、AS2 パイプライン、バッチ処理オーケストレーションなどがあります。</span><span class="sxs-lookup"><span data-stu-id="2be98-118">These artifacts will include EDI and AS2 pipelines and the batching orchestration.</span></span> <span data-ttu-id="2be98-119">このため、Microsoft EDI/AS2 機能を構成解除した後でも、基本的な EDI 処理および AS2 処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="2be98-119">As a result, you will still be able to perform basic EDI and AS2 processing even after unconfiguring the Microsoft EDI/AS2 feature.</span></span> <span data-ttu-id="2be98-120">この機能を無効にするには、EDI 処理および AS2 処理に関連付けられているポートを無効化、停止、または削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2be98-120">To disable this functionality, you should disable, stop, or delete the ports associated with EDI and AS2 processing.</span></span>  
  
## <a name="you-receive-the-error-failed-to-configure-edias2-status-reporting-functionalities"></a><span data-ttu-id="2be98-121">「EDI および AS2 状態レポート機能を構成できませんでした」エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="2be98-121">You Receive the Error "Failed to Configure EDI/AS2 Status Reporting Functionalities"</span></span>  
 <span data-ttu-id="2be98-122">**現象**</span><span class="sxs-lookup"><span data-stu-id="2be98-122">**Symptom**</span></span>  
  
 <span data-ttu-id="2be98-123">EDI/AS2 ランタイム状態レポートを構成すると、"EDI/AS2 の状態レポート機能を構成できませんでした。" というエラーを受け取る</span><span class="sxs-lookup"><span data-stu-id="2be98-123">When configuring EDI/AS2 Runtime Status Reporting, you receive error "Failed to Configure EDI/AS2 Status Reporting Functionalities".</span></span>  
  
 <span data-ttu-id="2be98-124">**考えられる原因**</span><span class="sxs-lookup"><span data-stu-id="2be98-124">**Possible Cause**</span></span>  
  
 <span data-ttu-id="2be98-125">BAM ツールを以前に構成し、その後構成解除した場合、このエラーを受け取る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2be98-125">You can receive this error if BAM Tools was previously configured and then unconfigured.</span></span>  
  
 <span data-ttu-id="2be98-126">**解決策**</span><span class="sxs-lookup"><span data-stu-id="2be98-126">**Resolution**</span></span>  
  
 <span data-ttu-id="2be98-127">EDI 状態レポートと AS2 状態レポートのうちの一方または両方を構成する前に、BAM ツールを構成します。</span><span class="sxs-lookup"><span data-stu-id="2be98-127">Configure BAM Tools prior to configuring EDI and/or AS2 status reporting.</span></span>  
  
## <a name="recovering-a-deleted-artifact-from-the-biztalk-edi-application-requires-you-to-reconfigure-the-edias2-runtime"></a><span data-ttu-id="2be98-128">BizTalk EDI アプリケーションから削除したアイテムを復旧するには EDI/AS2 ランタイムを再構成する必要がある</span><span class="sxs-lookup"><span data-stu-id="2be98-128">Recovering a Deleted Artifact From the BizTalk EDI Application Requires You to Reconfigure the EDI/AS2 Runtime</span></span>  
 <span data-ttu-id="2be98-129">独自のアイテムに対して BizTalk EDI アプリケーションを使用することは避ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="2be98-129">You should avoid using the BizTalk EDI Application for your own artifacts.</span></span> <span data-ttu-id="2be98-130">このアプリケーションには、EDI/AS2 の構成時に展開される EDI/AS2 アイテムが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2be98-130">This application contains the EDI/AS2 artifacts that are deployed during EDI/AS2 configuration.</span></span> <span data-ttu-id="2be98-131">個別のアプリケーションを作成し、BizTalk EDI アプリケーションへの参照をそのアプリケーションに追加する、という方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2be98-131">The recommended approach is to create a separate application and add a reference to BizTalk EDI Application to your application.</span></span> <span data-ttu-id="2be98-132">ただし、BizTalk EDI アプリケーションから EDI/AS2 アイテムを削除する場合、グループ内の各ランタイム コンピューターから BizTalk EDI/AS2 ランタイムを構成解除することで (または、グループから EDI/AS2 ランタイムを構成解除し、アクセス可能な各ランタイム コンピューターで EDI/AS2 を構成解除することで)、その状態から復旧できます。</span><span class="sxs-lookup"><span data-stu-id="2be98-132">However, if you delete any EDI/AS2 artifact from BizTalk EDI Application, you can recover from that state by unconfiguring the BizTalk EDI/AS2 runtime from each runtime computer in the group (or by unconfiguring the EDI/AS2 runtime from the group and unconfiguring the EDI/AS2 runtime on each of the reachable runtime computers).</span></span> <span data-ttu-id="2be98-133">データが損失するのを防ぐために、データベースまたは EDI/AS2 BAM アイテムを削除しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2be98-133">It is recommended that you do not delete your databases or the EDI/AS2 BAM activities to prevent data loss.</span></span> <span data-ttu-id="2be98-134">その後、グループ内のすべてのランタイム コンピューターで EDI/AS2 ランタイムを再構成し、削除した EDI/AS2 アイテムを復旧できます。</span><span class="sxs-lookup"><span data-stu-id="2be98-134">You can then reconfigure the EDI/AS2 runtime on all the runtime computers in the group to recover the deleted EDI/AS2 artifacts.</span></span>  
  
## <a name="numeric-transaction-set-group-control-and-interchange-control-values-may-be-truncated"></a><span data-ttu-id="2be98-135">数値のトランザクション セット、グループ制御、およびインターチェンジ制御の値が切り捨てられる場合がある</span><span class="sxs-lookup"><span data-stu-id="2be98-135">Numeric Transaction Set, Group Control and Interchange Control Values May be Truncated</span></span>  
 <span data-ttu-id="2be98-136">インターチェンジ制御番号、トランザクション セット参照番号、およびグループ制御番号の値範囲フィールドでは、許容される最大値を超える値を入力できます。</span><span class="sxs-lookup"><span data-stu-id="2be98-136">The value range fields for interchange control numbers, transaction set reference numbers, and group control numbers allow you to enter values that exceed the maximum allowed value.</span></span> <span data-ttu-id="2be98-137">構成を保存すると、これらの値は最大値に切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="2be98-137">When you save the configuration, these values will be truncated to the maximum value.</span></span>  
  
 <span data-ttu-id="2be98-138">X12 プロパティ フィールドの最大値は 999999999 です。</span><span class="sxs-lookup"><span data-stu-id="2be98-138">The maximum value for X12 property fields is 999999999.</span></span>  
  
 <span data-ttu-id="2be98-139">EDIFACT プロパティ フィールドの最大値は 99999999999999 です。</span><span class="sxs-lookup"><span data-stu-id="2be98-139">The maximum value for EDIFACT property fields is 99999999999999.</span></span>  
  
## <a name="control-numbers-are-reset-to-1-after-upgrade"></a><span data-ttu-id="2be98-140">アップグレードの後で制御番号が 1 にリセットされる</span><span class="sxs-lookup"><span data-stu-id="2be98-140">Control Numbers are Reset to 1 After Upgrade</span></span>  
 <span data-ttu-id="2be98-141">アップグレードした後、パーティの EDI のプロパティに表示されるすべての制御番号が 1 の既定の最小値にリセットされていて、999999999 (X12) または 99999999999999 (EDIFACT) の既定の最大値の表示に注意してください可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2be98-141">After upgrading, you may notice that all control numbers displayed in the EDI Properties of a party have been reset to the default minimum value of 1 and display a default maximum value of 999999999 (X12) or 99999999999999 (EDIFACT).</span></span> <span data-ttu-id="2be98-142">すべてのプレフィックス値またはサフィックス値は、アップグレードの後でも同じままです。</span><span class="sxs-lookup"><span data-stu-id="2be98-142">Any prefix or suffix values will remain the same after upgrade.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="2be98-143">制御番号に使用される最小値と最大値を示します。</span><span class="sxs-lookup"><span data-stu-id="2be98-143"> shows the minimum and maximum values to be used for the control number.</span></span> <span data-ttu-id="2be98-144">現在の制御番号は; のアップグレード中に保持されます。ただし、パーティの EDI プロパティには表示されません。</span><span class="sxs-lookup"><span data-stu-id="2be98-144">The current control number will be preserved during upgrade; however it is not displayed in the EDI Properties of the party.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2be98-145">参照</span><span class="sxs-lookup"><span data-stu-id="2be98-145">See Also</span></span>  
 <span data-ttu-id="2be98-146">[EDI および AS2 ソリューションのトラブルシューティング](../core/troubleshooting-edi-and-as2-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="2be98-146">[Troubleshooting EDI and AS2 Solutions](../core/troubleshooting-edi-and-as2-solutions.md) </span></span>  
 <span data-ttu-id="2be98-147">[BizTalk Server 2013 および 2013 R2 のインストール概要](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5) </span><span class="sxs-lookup"><span data-stu-id="2be98-147">[Installation Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5) </span></span>  
 <span data-ttu-id="2be98-148">[BizTalk Server 2013 および 2013 R2 の構成の概要](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72) </span><span class="sxs-lookup"><span data-stu-id="2be98-148">[Configuration Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72) </span></span>  
 [<span data-ttu-id="2be98-149">環境を最適化するための構成後の手順</span><span class="sxs-lookup"><span data-stu-id="2be98-149">Post-configuration steps to optimize your environment</span></span>](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md)