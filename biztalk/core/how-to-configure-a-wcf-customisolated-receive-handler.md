---
title: Wcf-customisolated 受信ハンドラーを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e90add2-1a5e-4509-a98c-b3c297b4213f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37c20d02f1051e8448eb50a7c60c57f93a524238
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022536"
---
# <a name="how-to-configure-a-wcf-customisolated-receive-handler"></a><span data-ttu-id="7e763-102">WCF-CustomIsolated 受信ハンドラーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="7e763-102">How to Configure a WCF-CustomIsolated Receive Handler</span></span>
<span data-ttu-id="7e763-103">WCF-CustomIsolated アダプターで machine.config 以外の場所からカスタム動作拡張機能を検索する場合は、受信ハンドラーのプロパティを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e763-103">You must configure the receive handler properties if you want the WCF-CustomIsolated adapter to lookup the custom behavior extension from locations other than machine.config.</span></span>  
  
## <a name="why-should-wcf-customisolated-adapter-look-up-custom-behavior-extensions-from-locations-other-than-machineconfig"></a><span data-ttu-id="7e763-104">Should WCF-CustomIsolated アダプターが machine.config 以外の場所からカスタム動作拡張機能を検索する理由</span><span class="sxs-lookup"><span data-stu-id="7e763-104">Why Should WCF-CustomIsolated Adapter Look up Custom Behavior Extensions from Locations Other than machine.config?</span></span>  
 <span data-ttu-id="7e763-105">使用されるカスタム動作拡張機能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]machine.config に登録されます。動作拡張機能を読み込む前に、Wcf-customisolated アダプターは、machine.config で動作拡張機能を検索します。ただし、machine.config は、特定のコンピューターで実行されているすべてのアプリケーションに必要な構成情報を格納する使用が理想的です。</span><span class="sxs-lookup"><span data-stu-id="7e763-105">Custom behavior extensions used by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] are registered in the machine.config. Before loading the behavior extensions, the WCF-CustomIsolated adapter looks for the behavior extensions in machine.config. However, machine.config is ideally used to store configuration information that is required across all applications running on a particular computer.</span></span> <span data-ttu-id="7e763-106">一方、WCF カスタム動作拡張機能はコンピューターで実行されているすべてのアプリケーションではなく、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でのみ要求されることがあります。</span><span class="sxs-lookup"><span data-stu-id="7e763-106">On the other hand, WCF custom behavior extensions may be required only by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and not by all the applications running on the computer.</span></span> <span data-ttu-id="7e763-107">したがって、machine.config にカスタム動作拡張機能を保存すれば目的にかないますが、ここは最適な場所ではありません。</span><span class="sxs-lookup"><span data-stu-id="7e763-107">So, while storing the custom behavior extensions in machine.config serves the purpose, it is not the most optimal location.</span></span>  
  
 <span data-ttu-id="7e763-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、WCF-CustomIsolated アダプターがカスタム動作拡張機能を参照するための追加の場所をアダプター ハンドラーのプロパティで指定します。</span><span class="sxs-lookup"><span data-stu-id="7e763-108">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the adapter handler properties provide an additional location from which the WCF-CustomIsolated adapter can look up the custom behavior extensions.</span></span> <span data-ttu-id="7e763-109">machine.config で既に利用可能な動作拡張機能を置き換えるものではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7e763-109">Note that this does not replace the behavior extensions already available in machine.config.</span></span>  
  
### <a name="additional-considerations"></a><span data-ttu-id="7e763-110">その他の注意点</span><span class="sxs-lookup"><span data-stu-id="7e763-110">Additional Considerations</span></span>  
 <span data-ttu-id="7e763-111">WCF-CustomIsolated 受信ハンドラーのプロパティを構成する際は、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="7e763-111">Keep the following points in mind while configuring the WCF-CustomIsolated receive handler properties:</span></span>  
  
-   <span data-ttu-id="7e763-112">カスタム動作拡張機能は machine.config かアダプター ハンドラーのプロパティのどちらか一方で利用可能にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e763-112">The custom behavior extensions must be available either in the machine.config or in the adapter handler properties.</span></span> <span data-ttu-id="7e763-113">カスタム動作拡張機能を両方の場所に重複して設定しないでください。</span><span class="sxs-lookup"><span data-stu-id="7e763-113">The custom behavior extensions must not be duplicated at both locations.</span></span>  
  
-   <span data-ttu-id="7e763-114">カスタム動作拡張機能が既に machine.config で利用できる場合、同じカスタム動作拡張機能をアダプター ハンドラーのプロパティに設定しようとすると、すぐにエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="7e763-114">If the custom behavior extension is already available in the machine.config and you try to set the same behavior extension for the adapter handler properties, you get an error as soon as you try to set the property.</span></span>  
  
-   <span data-ttu-id="7e763-115">カスタム動作拡張機能が既にアダプター ハンドラーのプロパティに設定されている場合、machine.config を同じカスタム動作拡張機能で更新すると、実行時エラーが発生し、イベント ログにも記録されます。</span><span class="sxs-lookup"><span data-stu-id="7e763-115">If the custom behavior extension is already set for the adapter handler properties and you then update the machine.config with the same behavior extension, you will get a runtime error and it is also logged in the event log.</span></span> <span data-ttu-id="7e763-116">受信場所も無効になります。</span><span class="sxs-lookup"><span data-stu-id="7e763-116">The receive location is also disabled.</span></span>  
  
-   <span data-ttu-id="7e763-117">アダプター ハンドラーのプロパティを設定する前に、カスタム動作拡張機能で参照されるアセンブリがグローバル アセンブリ キャッシュ (GAC) に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e763-117">The assemblies referred in the custom behavior extension must be present in the Global Assembly Cache (GAC) before you set the adapter handler properties.</span></span>  
  
## <a name="configuring-the-adapter-handler-properties"></a><span data-ttu-id="7e763-118">アダプター ハンドラーのプロパティの構成</span><span class="sxs-lookup"><span data-stu-id="7e763-118">Configuring the Adapter Handler Properties</span></span>  
 <span data-ttu-id="7e763-119">WCF-CustomIsolated 受信ハンドラーを構成するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="7e763-119">Use the following procedure to configure a WCF-CustomIsolated receive handler.</span></span>  
  
#### <a name="to-configure-the-adapter-handler-properties"></a><span data-ttu-id="7e763-120">アダプター ハンドラーのプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="7e763-120">To configure the adapter handler properties</span></span>  
  
1. <span data-ttu-id="7e763-121">BizTalk 管理コンソールで、 [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**を展開し**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="7e763-121">In the BizTalk Administration Console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2. <span data-ttu-id="7e763-122">展開したアダプターの一覧でクリックして**Wcf-customisolated**、右側のウィンドウで、構成する受信ハンドラーを右クリックし をクリック、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="7e763-122">In the expanded adapter list, click **WCF-CustomIsolated**, in the right pane, right-click the receive handler that you want to configure, and then click **Properties**.</span></span>  
  
3. <span data-ttu-id="7e763-123">**アダプター ハンドラーのプロパティ** ダイアログ ボックスの 、**全般** タブで、**ホスト名**一覧で、受信ハンドラーが関連付けられている場合、あるホストを選択し、クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="7e763-123">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the receive handler will be associated, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="7e763-124">**Wcf-customisolated トランスポートのプロパティ** ダイアログ ボックスの 、 **WCF 拡張機能** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7e763-124">In the **WCF-CustomIsolated Transport Properties** dialog box, on the **WCF Extensions** tab, do the following:</span></span>  
  
   |<span data-ttu-id="7e763-125">プロパティ</span><span class="sxs-lookup"><span data-stu-id="7e763-125">Use this</span></span>|<span data-ttu-id="7e763-126">目的</span><span class="sxs-lookup"><span data-stu-id="7e763-126">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="7e763-127">**[インポート]**</span><span class="sxs-lookup"><span data-stu-id="7e763-127">**Import**</span></span>|<span data-ttu-id="7e763-128">WCF カスタム動作拡張機能が登録されている WCF 構成ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="7e763-128">Imports a WCF configuration file with WCF custom behavior extensions.</span></span> <span data-ttu-id="7e763-129">このボタンをクリックすると、 **WCF 構成のインポート** ダイアログ ボックスを参照して、WCF 構成ファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="7e763-129">Clicking this button opens the **Import WCF configuration** dialog box to browse and locate a WCF configuration file.</span></span> <span data-ttu-id="7e763-130">有効な WCF 構成ファイルを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e763-130">Note that the file should be a valid WCF configuration file.</span></span> <span data-ttu-id="7e763-131">WCF 構成スキーマの詳細についてを参照してください「Windows Communication Foundation 構成スキーマ」 [ http://go.microsoft.com/fwlink/?LinkId=163953](http://go.microsoft.com/fwlink/?LinkId=163953)します。</span><span class="sxs-lookup"><span data-stu-id="7e763-131">For more information about WCF configuration schema, see “Windows Communication Foundation Configuration Schema” at [http://go.microsoft.com/fwlink/?LinkId=163953](http://go.microsoft.com/fwlink/?LinkId=163953).</span></span>|  
   |<span data-ttu-id="7e763-132">**[エクスポート]**</span><span class="sxs-lookup"><span data-stu-id="7e763-132">**Export**</span></span>|<span data-ttu-id="7e763-133">WCF カスタム動作拡張機能を WCF 構成ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="7e763-133">Exports the WCF custom behavior extension to a WCF configuration file.</span></span> <span data-ttu-id="7e763-134">このボタンをクリックすると、 **WCF 構成のエクスポート** ダイアログ ボックスを参照して、WCF 構成ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="7e763-134">Clicking this button opens the **Export WCF configuration** dialog box to browse and save the WCF configuration file.</span></span>|  
   |<span data-ttu-id="7e763-135">**Clear**</span><span class="sxs-lookup"><span data-stu-id="7e763-135">**Clear**</span></span>|<span data-ttu-id="7e763-136">既存の WCF カスタム動作拡張機能をアダプター ハンドラーのプロパティから消去します。</span><span class="sxs-lookup"><span data-stu-id="7e763-136">Clears the existing WCF custom behavior extension from the adapter handler properties.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7e763-137">参照</span><span class="sxs-lookup"><span data-stu-id="7e763-137">See Also</span></span>  
 [<span data-ttu-id="7e763-138">WCF-CustomIsolated アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="7e763-138">Configuring the WCF-CustomIsolated Adapter</span></span>](../core/configuring-the-wcf-customisolated-adapter.md)