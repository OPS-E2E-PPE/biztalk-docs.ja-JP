---
title: BAM イベント ソフトウェアのインストール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a3638d34-f5a8-4ffd-99eb-d38aed4c0732
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca5d13e058799113d7847fe6377ce82c7e0a7ea5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000291"
---
# <a name="installing-the-bam-eventing-software"></a><span data-ttu-id="0b7af-102">BAM イベント ソフトウェアのインストール</span><span class="sxs-lookup"><span data-stu-id="0b7af-102">Installing the BAM-Eventing Software</span></span>
<span data-ttu-id="0b7af-103">BAM イベント API を使用する BAM ソリューションを実装するか、または Windows Workflow Foundation 用に BAM インターセプターを使用するように Windows Workflow Foundation または Windows Communication Foundation アプリケーションを構成するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] セットアップ プログラムを使って BAM イベント ソフトウェアをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b7af-103">To implement BAM solutions using the BAM eventing APIs or configure your Windows Workflow Foundation or Windows Communication Foundation application to use the BAM interceptor for Windows Workflow Foundation, you must install the BAM-Eventing software by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Setup program.</span></span> <span data-ttu-id="0b7af-104">このソフトウェアは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイムの一部としてインストールするか、または [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] セットアップ アプリケーションで [追加ソフトウェア] の [BAM イベント サポート] を選択して単独でインストールできます。</span><span class="sxs-lookup"><span data-stu-id="0b7af-104">This software can be installed as part of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime or separately by selecting BAM Eventing Support under Additional Software in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] setup application.</span></span>  
  
### <a name="to-install-the-bam-eventing-software"></a><span data-ttu-id="0b7af-105">BAM イベント ソフトウェアをインストールするには</span><span class="sxs-lookup"><span data-stu-id="0b7af-105">To install the BAM-Eventing software</span></span>  
  
1. <span data-ttu-id="0b7af-106">WF アプリケーションをホストするコンピューターに、管理者特権を持つアカウントでログオンします。</span><span class="sxs-lookup"><span data-stu-id="0b7af-106">Log on to the computer that will host the WF application using an account that has Administrator privileges.</span></span>  
  
2. <span data-ttu-id="0b7af-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] インストール CD からセットアップ プログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="0b7af-107">Run the Setup program on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Installation CD.</span></span>  
  
3. <span data-ttu-id="0b7af-108">選択されたオプションをすべてオフにします。</span><span class="sxs-lookup"><span data-stu-id="0b7af-108">Clear all selected options.</span></span> <span data-ttu-id="0b7af-109">この手順を実行しないと、不要なソフトウェアがインストールされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0b7af-109">If you do not perform this step, you may install software you do not need.</span></span>  
  
4. <span data-ttu-id="0b7af-110">展開**追加ソフトウェア**を選び、 **BAM イベント**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="0b7af-110">Expand **Additional Software**, and then select the **BAM-Eventing** check box.</span></span>  
  
5. <span data-ttu-id="0b7af-111">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0b7af-111">Click **Next**.</span></span>  
  
6. <span data-ttu-id="0b7af-112">**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0b7af-112">Click **Install**.</span></span>  
  
7. <span data-ttu-id="0b7af-113">インストール手順が完了したら、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="0b7af-113">When the installation procedure is complete, click **OK**.</span></span>  
  
    <span data-ttu-id="0b7af-114">これで BAM イベント ソフトウェアがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="0b7af-114">The BAM-Eventing software is now installed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0b7af-115">この方法で BAM インターセプター ライブラリをインストールする場合は、追加のライセンスを購入する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="0b7af-115">Installing the BAM interceptor library using this method does not require the purchase of additional licenses.</span></span>  
  
 <span data-ttu-id="0b7af-116">BAM インターセプターのパフォーマンス カウンター データを監視する場合は、まず InstallUtil.exe を使用してパフォーマンス カウンターを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b7af-116">If you are interested in monitoring performance counter data for the BAM interceptors, you must first register them by using InstallUtil.exe.</span></span>  
  
### <a name="to-register-bam-interceptor-performance-counters-by-using-installutilexe"></a><span data-ttu-id="0b7af-117">InstallUtil.exe を使用して BAM インターセプター パフォーマンス カウンターを登録するには</span><span class="sxs-lookup"><span data-stu-id="0b7af-117">To register BAM interceptor performance counters by using InstallUtil.exe</span></span>  
  
1. <span data-ttu-id="0b7af-118">開始**[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプト**に管理者として。</span><span class="sxs-lookup"><span data-stu-id="0b7af-118">Start **[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Command Prompt** as an administrator.</span></span>  
  
2. <span data-ttu-id="0b7af-119">コマンド プロンプトで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="0b7af-119">At the command prompt, enter the following command:</span></span>  
  
    <span data-ttu-id="0b7af-120">InstallUtil [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\Microsoft.BizTalk.Bam.Interceptors.dll</span><span class="sxs-lookup"><span data-stu-id="0b7af-120">InstallUtil [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\Microsoft.BizTalk.Bam.Interceptors.dll</span></span>  
  
3. <span data-ttu-id="0b7af-121">型**終了**、し、enter キーを押してコマンド プロンプトを閉じます。</span><span class="sxs-lookup"><span data-stu-id="0b7af-121">Type **Exit**, and then press ENTER to close the command prompt.</span></span>  
  
    <span data-ttu-id="0b7af-122">これで BAM インターセプター パフォーマンス カウンターが使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="0b7af-122">The BAM interceptor performance counters are now available.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0b7af-123">既定では、管理者アカウントと一部のシステム アカウントにのみ、パフォーマンス データをログに記録するアクセス許可が与えられます。</span><span class="sxs-lookup"><span data-stu-id="0b7af-123">By default, only Administrators and some system accounts have permission to log performance data.</span></span> <span data-ttu-id="0b7af-124">[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] でのアクセスを可能にするには、ワークフロー アプリケーションの実行に使用するアカウントを Performance Log Users グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="0b7af-124">To enable access on [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)], add the account used for running workflow applications to the Performance Log Users group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b7af-125">参照</span><span class="sxs-lookup"><span data-stu-id="0b7af-125">See Also</span></span>  
 <span data-ttu-id="0b7af-126">[BAM ソリューションを実装します。](../core/implementing-bam-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="0b7af-126">[Implementing BAM Solutions](../core/implementing-bam-solutions.md) </span></span>  
 [<span data-ttu-id="0b7af-127">BizTalk Server 2013 および 2013 R2 のインストール概要</span><span class="sxs-lookup"><span data-stu-id="0b7af-127">Installation Overview for BizTalk Server 2013 and 2013 R2</span></span>](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)