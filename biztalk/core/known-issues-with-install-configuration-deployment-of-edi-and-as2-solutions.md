---
title: インストール、構成、および EDI および AS2 ソリューションの展開に関する既知の問題 |Microsoft Docs
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
ms.openlocfilehash: c376709ab9abcd5859e122d9c70a413f4fc89054
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329131"
---
# <a name="known-issues-with-installation-configuration-and-deployment-of-edi-and-as2-solutions"></a><span data-ttu-id="fc0c4-102">EDI ソリューションおよび AS2 ソリューションのインストール、構成、および展開に関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="fc0c4-102">Known Issues with Installation, Configuration, and Deployment of EDI and AS2 Solutions</span></span>
<span data-ttu-id="fc0c4-103">このトピックでは、の展開と管理に関する既知の問題を説明します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI および AS2 ソリューション。</span><span class="sxs-lookup"><span data-stu-id="fc0c4-103">This topic describes known issues with deployment and management of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI and AS2 solutions.</span></span>  
  
## <a name="blank-strings-were-imported-for-party-properties"></a><span data-ttu-id="fc0c4-104">パーティのプロパティを空白の文字列がインポートされました</span><span class="sxs-lookup"><span data-stu-id="fc0c4-104">Blank Strings Were Imported for Party Properties</span></span>  
 <span data-ttu-id="fc0c4-105">**現象**</span><span class="sxs-lookup"><span data-stu-id="fc0c4-105">**Symptom**</span></span>  
  
 <span data-ttu-id="fc0c4-106">バインド ファイルから BizTalk アプリケーションに edi/as2 バインドをインポートするときに、パスワード、セキュリティ/認証情報など、機密性が高いパーティ プロパティはインポートされませんでした。</span><span class="sxs-lookup"><span data-stu-id="fc0c4-106">When you imported EDI/AS2 bindings from a binding file into a BizTalk application, sensitive party properties, such as passwords or security/authentication information, were not imported.</span></span> <span data-ttu-id="fc0c4-107">これらのプロパティは、空白の文字列に設定されました。</span><span class="sxs-lookup"><span data-stu-id="fc0c4-107">Those properties were set to blank strings.</span></span>  
  
 <span data-ttu-id="fc0c4-108">**考えられる原因**</span><span class="sxs-lookup"><span data-stu-id="fc0c4-108">**Possible Cause**</span></span>  
  
 <span data-ttu-id="fc0c4-109">BizTalk Server では、機密性の高いフィールドの設定はインポートされません。</span><span class="sxs-lookup"><span data-stu-id="fc0c4-109">BizTalk Server will not import the settings of sensitive fields.</span></span> <span data-ttu-id="fc0c4-110">これらの設定をインポートすると、セキュリティ上の問題を作成できます。</span><span class="sxs-lookup"><span data-stu-id="fc0c4-110">Importing those settings could create a security issue.</span></span>  
  
 <span data-ttu-id="fc0c4-111">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="fc0c4-111">**Resolution**</span></span>  
  
 <span data-ttu-id="fc0c4-112">別のコンピュータにバインドをインポートした後、EDI の機密フィールドの値を手動で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc0c4-112">You must manually set the values for EDI sensitive fields after importing the bindings onto another computer.</span></span>  
  
## <a name="ftp-adapter-is-not-supported-natively-in-64-bit-mode"></a><span data-ttu-id="fc0c4-113">FTP アダプターが 64 ビット モードでネイティブにサポートされていません</span><span class="sxs-lookup"><span data-stu-id="fc0c4-113">FTP Adapter Is Not Supported Natively in 64-bit Mode</span></span>  
 <span data-ttu-id="fc0c4-114">FTP アダプターは、ネイティブの 64 ビット モードで実行できません。</span><span class="sxs-lookup"><span data-stu-id="fc0c4-114">The FTP adapter cannot run in native 64-bit mode.</span></span> <span data-ttu-id="fc0c4-115">EDI ソリューションで FTP アダプターを使用するかどうかは[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、64 ビット Windows の WOW64 で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc0c4-115">If you use an FTP adapter in your EDI solution in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you will have to run it on WOW64 on 64-bit Windows.</span></span>  
  
## <a name="some-edias2-artifacts-are-still-active-after-unconfiguring"></a><span data-ttu-id="fc0c4-116">構成解除した後、一部の edi/as2 アイテムがまだアクティブ</span><span class="sxs-lookup"><span data-stu-id="fc0c4-116">Some EDI/AS2 Artifacts Are Still Active After Unconfiguring</span></span>  
 <span data-ttu-id="fc0c4-117">Microsoft edi/as2 機能を構成解除した後[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、EDI および AS2 処理に関連する一部の BizTalk Server アイテムを BizTalk グループの構成のコンテキストでアクティブにすることができます。</span><span class="sxs-lookup"><span data-stu-id="fc0c4-117">After you unconfigure the Microsoft EDI/AS2 feature of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], some BizTalk Server artifacts related to EDI and AS2 processing will still be active in the context of the BizTalk group configuration.</span></span> <span data-ttu-id="fc0c4-118">これらの成果物には、EDI および AS2 のパイプラインとバッチ処理オーケストレーションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fc0c4-118">These artifacts will include EDI and AS2 pipelines and the batching orchestration.</span></span> <span data-ttu-id="fc0c4-119">その結果、Microsoft edi/as2 機能を構成解除した後でも、基本的な EDI および AS2 処理を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="fc0c4-119">As a result, you will still be able to perform basic EDI and AS2 processing even after unconfiguring the Microsoft EDI/AS2 feature.</span></span> <span data-ttu-id="fc0c4-120">この機能を無効にするを無効にし、停止、または EDI および AS2 処理に関連付けられているポートを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc0c4-120">To disable this functionality, you should disable, stop, or delete the ports associated with EDI and AS2 processing.</span></span>  
  
## <a name="you-receive-the-error-failed-to-configure-edias2-status-reporting-functionalities"></a><span data-ttu-id="fc0c4-121">「EDI および AS2 状態レポート機能の構成に失敗しました」エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="fc0c4-121">You Receive the Error "Failed to Configure EDI/AS2 Status Reporting Functionalities"</span></span>  
 <span data-ttu-id="fc0c4-122">**現象**</span><span class="sxs-lookup"><span data-stu-id="fc0c4-122">**Symptom**</span></span>  
  
 <span data-ttu-id="fc0c4-123">Edi/as2 ランタイム状態レポートを構成するには、エラー「が失敗しました、edi/as2 状態レポート機能を構成」が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fc0c4-123">When configuring EDI/AS2 Runtime Status Reporting, you receive error "Failed to Configure EDI/AS2 Status Reporting Functionalities".</span></span>  
  
 <span data-ttu-id="fc0c4-124">**考えられる原因**</span><span class="sxs-lookup"><span data-stu-id="fc0c4-124">**Possible Cause**</span></span>  
  
 <span data-ttu-id="fc0c4-125">このエラーは、BAM ツールが以前に構成し、構成を解除しが発生することができます。</span><span class="sxs-lookup"><span data-stu-id="fc0c4-125">You can receive this error if BAM Tools was previously configured and then unconfigured.</span></span>  
  
 <span data-ttu-id="fc0c4-126">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="fc0c4-126">**Resolution**</span></span>  
  
 <span data-ttu-id="fc0c4-127">EDI または AS2 状態がレポートを構成する前に、BAM ツールを構成します。</span><span class="sxs-lookup"><span data-stu-id="fc0c4-127">Configure BAM Tools prior to configuring EDI and/or AS2 status reporting.</span></span>  
  
## <a name="recovering-a-deleted-artifact-from-the-biztalk-edi-application-requires-you-to-reconfigure-the-edias2-runtime"></a><span data-ttu-id="fc0c4-128">Edi/as2 ランタイムを再構成する BizTalk EDI アプリケーションから削除したアイテムを回復する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc0c4-128">Recovering a Deleted Artifact From the BizTalk EDI Application Requires You to Reconfigure the EDI/AS2 Runtime</span></span>  
 <span data-ttu-id="fc0c4-129">BizTalk EDI アプリケーションを使用して、独自のアーティファクトを避ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc0c4-129">You should avoid using the BizTalk EDI Application for your own artifacts.</span></span> <span data-ttu-id="fc0c4-130">このアプリケーションには、EDI および AS2 の構成時に展開される edi/as2 アイテムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fc0c4-130">This application contains the EDI/AS2 artifacts that are deployed during EDI/AS2 configuration.</span></span> <span data-ttu-id="fc0c4-131">別のアプリケーションを作成し、アプリケーションに BizTalk EDI アプリケーションへの参照を追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fc0c4-131">The recommended approach is to create a separate application and add a reference to BizTalk EDI Application to your application.</span></span> <span data-ttu-id="fc0c4-132">ただし、BizTalk EDI アプリケーションから EDI および AS2 のすべてのアイテムを削除した場合または回復できますその状態から、グループ内の各ランタイム コンピューターから BizTalk edi/as2 ランタイムを構成解除して (グループから edi/as2 ランタイムの構成を解除し、構成解除してEDI および AS2 ランタイム各到達可能なランタイム コンピューターで)。</span><span class="sxs-lookup"><span data-stu-id="fc0c4-132">However, if you delete any EDI/AS2 artifact from BizTalk EDI Application, you can recover from that state by unconfiguring the BizTalk EDI/AS2 runtime from each runtime computer in the group (or by unconfiguring the EDI/AS2 runtime from the group and unconfiguring the EDI/AS2 runtime on each of the reachable runtime computers).</span></span> <span data-ttu-id="fc0c4-133">データベースまたはデータ損失を防ぐため、edi/as2 BAM アクティビティを削除しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fc0c4-133">It is recommended that you do not delete your databases or the EDI/AS2 BAM activities to prevent data loss.</span></span> <span data-ttu-id="fc0c4-134">削除した edi/as2 アイテムを回復するには、グループのすべてのランタイム コンピューターで edi/as2 ランタイムを再構成できます。</span><span class="sxs-lookup"><span data-stu-id="fc0c4-134">You can then reconfigure the EDI/AS2 runtime on all the runtime computers in the group to recover the deleted EDI/AS2 artifacts.</span></span>  
  
## <a name="numeric-transaction-set-group-control-and-interchange-control-values-may-be-truncated"></a><span data-ttu-id="fc0c4-135">数値のトランザクション セット、グループ コントロール、およびインターチェンジ制御の値が切り捨てられる</span><span class="sxs-lookup"><span data-stu-id="fc0c4-135">Numeric Transaction Set, Group Control and Interchange Control Values May be Truncated</span></span>  
 <span data-ttu-id="fc0c4-136">インターチェンジ制御番号の値範囲フィールドでは、トランザクション セット参照番号、およびグループ制御番号を使用すると、最大許容値を超える値を入力します。</span><span class="sxs-lookup"><span data-stu-id="fc0c4-136">The value range fields for interchange control numbers, transaction set reference numbers, and group control numbers allow you to enter values that exceed the maximum allowed value.</span></span> <span data-ttu-id="fc0c4-137">構成を保存するときにこれらの値は最大値に切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="fc0c4-137">When you save the configuration, these values will be truncated to the maximum value.</span></span>  
  
 <span data-ttu-id="fc0c4-138">X12 の最大値プロパティ フィールドは 999999999 です。</span><span class="sxs-lookup"><span data-stu-id="fc0c4-138">The maximum value for X12 property fields is 999999999.</span></span>  
  
 <span data-ttu-id="fc0c4-139">EDIFACT プロパティ フィールドの最大値は、99999999999999 です。</span><span class="sxs-lookup"><span data-stu-id="fc0c4-139">The maximum value for EDIFACT property fields is 99999999999999.</span></span>  
  
## <a name="control-numbers-are-reset-to-1-after-upgrade"></a><span data-ttu-id="fc0c4-140">制御番号が 1 アップグレードの後にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="fc0c4-140">Control Numbers are Reset to 1 After Upgrade</span></span>  
 <span data-ttu-id="fc0c4-141">アップグレードした後、パーティの EDI のプロパティに表示されるすべての制御番号が 1 の既定の最小値にリセットされていて、999999999 (X12) または 99999999999999 (EDIFACT) の既定の最大値を表示お気付きです。</span><span class="sxs-lookup"><span data-stu-id="fc0c4-141">After upgrading, you may notice that all control numbers displayed in the EDI Properties of a party have been reset to the default minimum value of 1 and display a default maximum value of 999999999 (X12) or 99999999999999 (EDIFACT).</span></span> <span data-ttu-id="fc0c4-142">任意のプレフィックスまたはサフィックスの値では、アップグレード後も同じです。</span><span class="sxs-lookup"><span data-stu-id="fc0c4-142">Any prefix or suffix values will remain the same after upgrade.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="fc0c4-143">制御番号に使用する最小値と最大値を示します。</span><span class="sxs-lookup"><span data-stu-id="fc0c4-143">shows the minimum and maximum values to be used for the control number.</span></span> <span data-ttu-id="fc0c4-144">現在の制御番号はアップグレード中に保持されます。ただし、パーティの EDI プロパティには表示されません。</span><span class="sxs-lookup"><span data-stu-id="fc0c4-144">The current control number will be preserved during upgrade; however it is not displayed in the EDI Properties of the party.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc0c4-145">参照</span><span class="sxs-lookup"><span data-stu-id="fc0c4-145">See Also</span></span>  
 <span data-ttu-id="fc0c4-146">[EDI および AS2 ソリューションのトラブルシューティング](../core/troubleshooting-edi-and-as2-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="fc0c4-146">[Troubleshooting EDI and AS2 Solutions](../core/troubleshooting-edi-and-as2-solutions.md) </span></span>  
 <span data-ttu-id="fc0c4-147">[BizTalk Server 2013 および 2013 R2 のインストールの概要](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5) </span><span class="sxs-lookup"><span data-stu-id="fc0c4-147">[Installation Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5) </span></span>  
 <span data-ttu-id="fc0c4-148">[BizTalk Server 2013 および 2013 R2 の構成の概要](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72) </span><span class="sxs-lookup"><span data-stu-id="fc0c4-148">[Configuration Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72) </span></span>  
 [<span data-ttu-id="fc0c4-149">環境を最適化するための構成後の手順</span><span class="sxs-lookup"><span data-stu-id="fc0c4-149">Post-configuration steps to optimize your environment</span></span>](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md)