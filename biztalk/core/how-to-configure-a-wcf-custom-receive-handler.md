---
title: Wcf-custom 受信ハンドラーを構成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0208a7aa-6e42-43b7-a934-27ef4409b4ec
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 130e4fbffd9069c8326d0197216791cf2ace3785
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248290"
---
# <a name="how-to-configure-a-wcf-custom-receive-handler"></a><span data-ttu-id="2e0e7-102">WCF-Custom 受信ハンドラーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="2e0e7-102">How to Configure a WCF-Custom Receive Handler</span></span>
<span data-ttu-id="2e0e7-103">[!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)] で、machine.config 以外の場所からカスタム動作拡張機能を検索する場合は、受信ハンドラーのプロパティを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e0e7-103">You must configure the receive handler properties if you want the [!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)] to look up the custom behavior extensions from locations other than machine.config.</span></span>  
  
## <a name="why-should-wcf-custom-adapter-lookup-custom-behavior-extensions-from-locations-other-than-machineconfig"></a><span data-ttu-id="2e0e7-104">なぜ machine.config 以外の場所から WCF カスタム アダプター ルックアップ カスタム動作拡張機能しますか。</span><span class="sxs-lookup"><span data-stu-id="2e0e7-104">Why Should WCF-Custom Adapter Lookup Custom Behavior Extensions from Locations Other than machine.config?</span></span>  
 <span data-ttu-id="2e0e7-105">によって使用されるカスタム動作拡張機能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]machine.config に登録されます。[!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)] は、動作拡張機能を読み込む前に、machine.config で動作拡張機能を検索します。ただし、machine.config は、理想的には、特定のコンピューターで実行されているすべてのアプリケーションに必要な構成情報を格納する使用されます。</span><span class="sxs-lookup"><span data-stu-id="2e0e7-105">Custom behavior extensions used by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] are registered in the machine.config. Before loading the behavior extensions, the [!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)] looks for the behavior extensions in machine.config. However, machine.config is ideally used to store configuration information that is required across all applications running on a particular computer.</span></span> <span data-ttu-id="2e0e7-106">一方、WCF カスタム動作拡張機能はコンピューターで実行されているすべてのアプリケーションではなく、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でのみ要求されることがあります。</span><span class="sxs-lookup"><span data-stu-id="2e0e7-106">On the other hand, WCF custom behavior extensions may be required only by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and not by all the applications running on the computer.</span></span> <span data-ttu-id="2e0e7-107">したがって、machine.config にカスタム動作拡張機能を保存すれば目的にかないますが、ここは最適な場所ではありません。</span><span class="sxs-lookup"><span data-stu-id="2e0e7-107">So, while storing the custom behavior extensions in machine.config serves the purpose, it is not the most optimal location.</span></span>  
  
 <span data-ttu-id="2e0e7-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、[!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)] がカスタム動作拡張機能を参照するための追加の場所をアダプター ハンドラーのプロパティで指定します。</span><span class="sxs-lookup"><span data-stu-id="2e0e7-108">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the adapter handler properties provide an additional location from which the [!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)] can look up the custom behavior extensions.</span></span> <span data-ttu-id="2e0e7-109">machine.config で既に利用可能な動作拡張機能を置き換えるものではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2e0e7-109">Note that this does not replace the behavior extensions already available in machine.config.</span></span>  
  
### <a name="additional-considerations"></a><span data-ttu-id="2e0e7-110">その他の注意点</span><span class="sxs-lookup"><span data-stu-id="2e0e7-110">Additional Considerations</span></span>  
 <span data-ttu-id="2e0e7-111">WCF-Custom 受信ハンドラーのプロパティを構成する際は、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="2e0e7-111">Keep the following points in mind while configuring the WCF-Custom receive handler properties:</span></span>  
  
-   <span data-ttu-id="2e0e7-112">カスタム動作拡張機能は machine.config かアダプター ハンドラーのプロパティのどちらか一方で利用可能にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e0e7-112">The custom behavior extensions must be available either in the machine.config or in the adapter handler properties.</span></span> <span data-ttu-id="2e0e7-113">カスタム動作拡張機能を両方の場所に重複して設定しないでください。</span><span class="sxs-lookup"><span data-stu-id="2e0e7-113">The custom behavior extensions must not be duplicated at both locations.</span></span>  
  
-   <span data-ttu-id="2e0e7-114">カスタム動作拡張機能が既に machine.config で利用できる場合、同じカスタム動作拡張機能をアダプター ハンドラーのプロパティに設定しようとすると、すぐにエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="2e0e7-114">If the custom behavior extension is already available in the machine.config and you try to set the same behavior extension for the adapter handler properties, you get an error as soon as you try to set the property.</span></span>  
  
-   <span data-ttu-id="2e0e7-115">カスタム動作拡張機能が既にアダプター ハンドラーのプロパティに設定されている場合、machine.config を同じカスタム動作拡張機能で更新すると、実行時エラーが発生し、イベント ログにも記録されます。</span><span class="sxs-lookup"><span data-stu-id="2e0e7-115">If the custom behavior extension is already set for the adapter handler properties and you then update the machine.config with the same behavior extension, you will get a runtime error and it is also logged in the event log.</span></span> <span data-ttu-id="2e0e7-116">受信場所も無効になります。</span><span class="sxs-lookup"><span data-stu-id="2e0e7-116">The receive location is also disabled.</span></span>  
  
-   <span data-ttu-id="2e0e7-117">アダプター ハンドラーのプロパティを設定する前に、カスタム動作拡張機能で参照されるアセンブリがグローバル アセンブリ キャッシュ (GAC) に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e0e7-117">The assemblies referred in the custom behavior extension must be present in the Global Assembly Cache (GAC) before you set the adapter handler properties.</span></span>  
  
## <a name="configuring-the-adapter-handler-properties"></a><span data-ttu-id="2e0e7-118">アダプター ハンドラーのプロパティの構成</span><span class="sxs-lookup"><span data-stu-id="2e0e7-118">Configuring the Adapter Handler Properties</span></span>  
 <span data-ttu-id="2e0e7-119">WCF-Custom 受信ハンドラーを構成するには、このトピックの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2e0e7-119">Use the procedure in this topic to configure a WCF-Custom receive handler.</span></span>  
  
#### <a name="to-configure-the-adapter-handler-properties"></a><span data-ttu-id="2e0e7-120">アダプター ハンドラーのプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="2e0e7-120">To configure the adapter handler properties</span></span>  
  
1.  <span data-ttu-id="2e0e7-121">BizTalk 管理コンソールで  [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**の順に展開および**アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="2e0e7-121">In the BizTalk Administration Console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="2e0e7-122">展開したアダプターの一覧でクリックして**Wcf-custom**、右側のペインで、構成する受信ハンドラを右クリックしをクリック**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="2e0e7-122">In the expanded adapter list, click **WCF-Custom**, in the right pane, right-click the receive handler that you want to configure, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="2e0e7-123">**アダプター ハンドラーのプロパティ** ダイアログ ボックスで、**全般** タブの 、**ホスト名**一覧で、受信ハンドラーが関連付けられているホストを選択し、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="2e0e7-123">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the receive handler will be associated, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="2e0e7-124">**Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、 **WCF 拡張機能** タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="2e0e7-124">In the **WCF-Custom Transport Properties** dialog box, on the **WCF Extensions** tab, do the following:</span></span>  
  
    |<span data-ttu-id="2e0e7-125">プロパティ</span><span class="sxs-lookup"><span data-stu-id="2e0e7-125">Use this</span></span>|<span data-ttu-id="2e0e7-126">目的</span><span class="sxs-lookup"><span data-stu-id="2e0e7-126">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="2e0e7-127">**[インポート]**</span><span class="sxs-lookup"><span data-stu-id="2e0e7-127">**Import**</span></span>|<span data-ttu-id="2e0e7-128">WCF カスタム動作拡張機能が登録されている WCF 構成ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="2e0e7-128">Imports a WCF configuration file with WCF custom behavior extensions.</span></span> <span data-ttu-id="2e0e7-129">このボタンをクリックすると開きます、 **WCF 構成のインポート** ダイアログ ボックスを参照して、WCF 構成ファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="2e0e7-129">Clicking this button opens the **Import WCF configuration** dialog box to browse and locate a WCF configuration file.</span></span> <span data-ttu-id="2e0e7-130">有効な WCF 構成ファイルを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e0e7-130">Note that the file should be a valid WCF configuration file.</span></span> <span data-ttu-id="2e0e7-131">WCF 構成スキーマの詳細についてを参照してください「Windows Communication Foundation 構成スキーマ」 [http://go.microsoft.com/fwlink/?LinkId=163953](http://go.microsoft.com/fwlink/?LinkId=163953)です。</span><span class="sxs-lookup"><span data-stu-id="2e0e7-131">For more information about WCF configuration schema, see “Windows Communication Foundation Configuration Schema” at [http://go.microsoft.com/fwlink/?LinkId=163953](http://go.microsoft.com/fwlink/?LinkId=163953).</span></span>|  
    |<span data-ttu-id="2e0e7-132">**[エクスポート]**</span><span class="sxs-lookup"><span data-stu-id="2e0e7-132">**Export**</span></span>|<span data-ttu-id="2e0e7-133">WCF カスタム動作拡張機能を WCF 構成ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="2e0e7-133">Exports the WCF custom behavior extension to a WCF configuration file.</span></span> <span data-ttu-id="2e0e7-134">このボタンをクリックすると開きます、 **WCF 構成のエクスポート** ダイアログ ボックスを参照して、WCF 構成ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="2e0e7-134">Clicking this button opens the **Export WCF configuration** dialog box to browse and save the WCF configuration file.</span></span>|  
    |<span data-ttu-id="2e0e7-135">**Clear**</span><span class="sxs-lookup"><span data-stu-id="2e0e7-135">**Clear**</span></span>|<span data-ttu-id="2e0e7-136">既存の WCF カスタム動作拡張機能をアダプター ハンドラーのプロパティから消去します。</span><span class="sxs-lookup"><span data-stu-id="2e0e7-136">Clears the existing WCF custom behavior extension from the adapter handler properties.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2e0e7-137">参照</span><span class="sxs-lookup"><span data-stu-id="2e0e7-137">See Also</span></span>  
 [<span data-ttu-id="2e0e7-138">WCF カスタム アダプターを構成します。</span><span class="sxs-lookup"><span data-stu-id="2e0e7-138">Configuring the WCF-Custom Adapter</span></span>](../core/configuring-the-wcf-custom-adapter.md)