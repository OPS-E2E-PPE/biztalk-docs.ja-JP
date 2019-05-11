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
ms.openlocfilehash: 682306dca7a0ae120b4a0ccc84a52733ce23b772
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331931"
---
# <a name="installing-the-bam-eventing-software"></a><span data-ttu-id="10f9c-102">BAM イベント ソフトウェアのインストール</span><span class="sxs-lookup"><span data-stu-id="10f9c-102">Installing the BAM-Eventing Software</span></span>
<span data-ttu-id="10f9c-103">BAM イベント Api を使用して BAM ソリューションの実装、または、Windows Workflow Foundation の BAM インターセプターを使用するアプリケーションの Windows Workflow Foundation または Windows Communication Foundation アプリケーションを構成を使用して BAM イベント ソフトウェアをインストールする必要があります。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]セットアップ プログラム。</span><span class="sxs-lookup"><span data-stu-id="10f9c-103">To implement BAM solutions using the BAM eventing APIs or configure your Windows Workflow Foundation or Windows Communication Foundation application to use the BAM interceptor for Windows Workflow Foundation, you must install the BAM-Eventing software by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Setup program.</span></span> <span data-ttu-id="10f9c-104">一部としてこのソフトウェアをインストールすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイムまたは BAM イベント サポート の下で追加のソフトウェアを選択して単独で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーションをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="10f9c-104">This software can be installed as part of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime or separately by selecting BAM Eventing Support under Additional Software in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] setup application.</span></span>  
  
### <a name="to-install-the-bam-eventing-software"></a><span data-ttu-id="10f9c-105">BAM イベント ソフトウェアをインストールするには</span><span class="sxs-lookup"><span data-stu-id="10f9c-105">To install the BAM-Eventing software</span></span>  
  
1. <span data-ttu-id="10f9c-106">管理者特権を持つアカウントを使用して、WF アプリケーションをホストするコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="10f9c-106">Log on to the computer that will host the WF application using an account that has Administrator privileges.</span></span>  
  
2. <span data-ttu-id="10f9c-107">セットアップ プログラムで実行、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストール CD。</span><span class="sxs-lookup"><span data-stu-id="10f9c-107">Run the Setup program on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Installation CD.</span></span>  
  
3. <span data-ttu-id="10f9c-108">選択したすべてのオプションをオフにします。</span><span class="sxs-lookup"><span data-stu-id="10f9c-108">Clear all selected options.</span></span> <span data-ttu-id="10f9c-109">この手順を実行しない場合は、必要としないソフトウェアをインストールする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="10f9c-109">If you do not perform this step, you may install software you do not need.</span></span>  
  
4. <span data-ttu-id="10f9c-110">展開**追加ソフトウェア**を選び、 **BAM イベント**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="10f9c-110">Expand **Additional Software**, and then select the **BAM-Eventing** check box.</span></span>  
  
5. <span data-ttu-id="10f9c-111">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="10f9c-111">Click **Next**.</span></span>  
  
6. <span data-ttu-id="10f9c-112">**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="10f9c-112">Click **Install**.</span></span>  
  
7. <span data-ttu-id="10f9c-113">インストール手順が完了したら、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="10f9c-113">When the installation procedure is complete, click **OK**.</span></span>  
  
    <span data-ttu-id="10f9c-114">BAM イベント ソフトウェアがインストールされているようになりました。</span><span class="sxs-lookup"><span data-stu-id="10f9c-114">The BAM-Eventing software is now installed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="10f9c-115">このメソッドを使用して、BAM インターセプター ライブラリをインストールしても、追加のライセンスの購入は不要です。</span><span class="sxs-lookup"><span data-stu-id="10f9c-115">Installing the BAM interceptor library using this method does not require the purchase of additional licenses.</span></span>  
  
 <span data-ttu-id="10f9c-116">BAM インターセプターのパフォーマンス カウンター データを監視する場合は、最初に InstallUtil.exe を使用して登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10f9c-116">If you are interested in monitoring performance counter data for the BAM interceptors, you must first register them by using InstallUtil.exe.</span></span>  
  
### <a name="to-register-bam-interceptor-performance-counters-by-using-installutilexe"></a><span data-ttu-id="10f9c-117">InstallUtil.exe を使用して BAM インターセプターのパフォーマンス カウンターを登録するには</span><span class="sxs-lookup"><span data-stu-id="10f9c-117">To register BAM interceptor performance counters by using InstallUtil.exe</span></span>  
  
1. <span data-ttu-id="10f9c-118">開始**[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプト**に管理者として。</span><span class="sxs-lookup"><span data-stu-id="10f9c-118">Start **[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Command Prompt** as an administrator.</span></span>  
  
2. <span data-ttu-id="10f9c-119">コマンド プロンプトで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="10f9c-119">At the command prompt, enter the following command:</span></span>  
  
    <span data-ttu-id="10f9c-120">InstallUtil [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\Microsoft.BizTalk.Bam.Interceptors.dll</span><span class="sxs-lookup"><span data-stu-id="10f9c-120">InstallUtil [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\Microsoft.BizTalk.Bam.Interceptors.dll</span></span>  
  
3. <span data-ttu-id="10f9c-121">型**終了**、し、enter キーを押してコマンド プロンプトを閉じます。</span><span class="sxs-lookup"><span data-stu-id="10f9c-121">Type **Exit**, and then press ENTER to close the command prompt.</span></span>  
  
    <span data-ttu-id="10f9c-122">BAM インターセプターのパフォーマンス カウンターは、使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="10f9c-122">The BAM interceptor performance counters are now available.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="10f9c-123">既定では、管理者と一部のシステム アカウントのみのパフォーマンス データを記録するためのアクセス許可があります。</span><span class="sxs-lookup"><span data-stu-id="10f9c-123">By default, only Administrators and some system accounts have permission to log performance data.</span></span> <span data-ttu-id="10f9c-124">アクセスを有効にする[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]、Performance Log Users グループにワークフロー アプリケーションの実行に使用するアカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="10f9c-124">To enable access on [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)], add the account used for running workflow applications to the Performance Log Users group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10f9c-125">参照</span><span class="sxs-lookup"><span data-stu-id="10f9c-125">See Also</span></span>  
 <span data-ttu-id="10f9c-126">[BAM ソリューションを実装します。](../core/implementing-bam-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="10f9c-126">[Implementing BAM Solutions](../core/implementing-bam-solutions.md) </span></span>  
 [<span data-ttu-id="10f9c-127">BizTalk Server 2013 および 2013 R2 のインストールの概要</span><span class="sxs-lookup"><span data-stu-id="10f9c-127">Installation Overview for BizTalk Server 2013 and 2013 R2</span></span>](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)