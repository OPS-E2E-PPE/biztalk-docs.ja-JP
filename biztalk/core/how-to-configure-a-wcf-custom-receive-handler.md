---
title: Wcf-custom 受信ハンドラーを構成する方法 |Microsoft Docs
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
ms.openlocfilehash: a24977805f9d55ec95784a81a2a2c914d887f440
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342265"
---
# <a name="how-to-configure-a-wcf-custom-receive-handler"></a><span data-ttu-id="cfa60-102">WCF-Custom 受信ハンドラーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="cfa60-102">How to Configure a WCF-Custom Receive Handler</span></span>
<span data-ttu-id="cfa60-103">する場合は、受信ハンドラのプロパティを構成する必要があります、 [!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)] machine.config 以外の場所からカスタム動作拡張機能を検索します。</span><span class="sxs-lookup"><span data-stu-id="cfa60-103">You must configure the receive handler properties if you want the [!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)] to look up the custom behavior extensions from locations other than machine.config.</span></span>  
  
## <a name="why-should-wcf-custom-adapter-lookup-custom-behavior-extensions-from-locations-other-than-machineconfig"></a><span data-ttu-id="cfa60-104">なぜ machine.config 以外の場所から WCF カスタム アダプター参照カスタム動作拡張機能を必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="cfa60-104">Why Should WCF-Custom Adapter Lookup Custom Behavior Extensions from Locations Other than machine.config?</span></span>  
 <span data-ttu-id="cfa60-105">使用されるカスタム動作拡張機能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]machine.config に登録されます。動作拡張機能を読み込む前に、 [!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)] machine.config で動作拡張機能を検索します。ただし、machine.config は、特定のコンピューターで実行されているすべてのアプリケーションに必要な構成情報を格納する使用が理想的です。</span><span class="sxs-lookup"><span data-stu-id="cfa60-105">Custom behavior extensions used by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] are registered in the machine.config. Before loading the behavior extensions, the [!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)] looks for the behavior extensions in machine.config. However, machine.config is ideally used to store configuration information that is required across all applications running on a particular computer.</span></span> <span data-ttu-id="cfa60-106">WCF カスタム動作拡張機能でのみ必要とその一方で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターで実行されているすべてのアプリケーションではなく、します。</span><span class="sxs-lookup"><span data-stu-id="cfa60-106">On the other hand, WCF custom behavior extensions may be required only by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and not by all the applications running on the computer.</span></span> <span data-ttu-id="cfa60-107">したがって、machine.config にカスタム動作拡張機能を格納する役目を果たします、中には最適な場所ではありません。</span><span class="sxs-lookup"><span data-stu-id="cfa60-107">So, while storing the custom behavior extensions in machine.config serves the purpose, it is not the most optimal location.</span></span>  
  
 <span data-ttu-id="cfa60-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、アダプター ハンドラーのプロパティは、元の追加の場所を指定、[!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)]カスタム動作拡張機能を調べることができます。</span><span class="sxs-lookup"><span data-stu-id="cfa60-108">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the adapter handler properties provide an additional location from which the [!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)] can look up the custom behavior extensions.</span></span> <span data-ttu-id="cfa60-109">Machine.config で既に利用できる動作拡張機能は置き換えられませんことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="cfa60-109">Note that this does not replace the behavior extensions already available in machine.config.</span></span>  
  
### <a name="additional-considerations"></a><span data-ttu-id="cfa60-110">その他の注意点</span><span class="sxs-lookup"><span data-stu-id="cfa60-110">Additional Considerations</span></span>  
 <span data-ttu-id="cfa60-111">受信ハンドラのプロパティを維持する Wcf-custom を構成するときに、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="cfa60-111">Keep the following points in mind while configuring the WCF-Custom receive handler properties:</span></span>  
  
-   <span data-ttu-id="cfa60-112">カスタム動作拡張機能は、machine.config かアダプター ハンドラーのプロパティである必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfa60-112">The custom behavior extensions must be available either in the machine.config or in the adapter handler properties.</span></span> <span data-ttu-id="cfa60-113">カスタム動作拡張機能は、両方の場所に重複していない必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfa60-113">The custom behavior extensions must not be duplicated at both locations.</span></span>  
  
-   <span data-ttu-id="cfa60-114">カスタム動作拡張機能は、machine.config で利用可能な既にアダプター ハンドラーのプロパティの同じ動作拡張機能を設定しようとする場合は、プロパティを設定しようとするとすぐにエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="cfa60-114">If the custom behavior extension is already available in the machine.config and you try to set the same behavior extension for the adapter handler properties, you get an error as soon as you try to set the property.</span></span>  
  
-   <span data-ttu-id="cfa60-115">カスタム動作拡張機能は既にアダプター ハンドラーのプロパティを設定し、同じ動作拡張機能で、machine.config を更新する場合は、ランタイム エラーが発生してもイベント ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="cfa60-115">If the custom behavior extension is already set for the adapter handler properties and you then update the machine.config with the same behavior extension, you will get a runtime error and it is also logged in the event log.</span></span> <span data-ttu-id="cfa60-116">受信場所も無効になります。</span><span class="sxs-lookup"><span data-stu-id="cfa60-116">The receive location is also disabled.</span></span>  
  
-   <span data-ttu-id="cfa60-117">カスタム動作拡張機能で参照されるアセンブリは、アダプター ハンドラーのプロパティを設定する前に、グローバル アセンブリ キャッシュ (GAC) に存在することがあります。</span><span class="sxs-lookup"><span data-stu-id="cfa60-117">The assemblies referred in the custom behavior extension must be present in the Global Assembly Cache (GAC) before you set the adapter handler properties.</span></span>  
  
## <a name="configuring-the-adapter-handler-properties"></a><span data-ttu-id="cfa60-118">アダプター ハンドラーのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="cfa60-118">Configuring the Adapter Handler Properties</span></span>  
 <span data-ttu-id="cfa60-119">受信ハンドラーを Wcf-custom を構成するには、このトピックの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="cfa60-119">Use the procedure in this topic to configure a WCF-Custom receive handler.</span></span>  
  
#### <a name="to-configure-the-adapter-handler-properties"></a><span data-ttu-id="cfa60-120">アダプター ハンドラーのプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="cfa60-120">To configure the adapter handler properties</span></span>  
  
1. <span data-ttu-id="cfa60-121">BizTalk 管理コンソールで、 [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**を展開し**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="cfa60-121">In the BizTalk Administration Console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2. <span data-ttu-id="cfa60-122">展開したアダプターの一覧でクリックして**Wcf-custom**、右側のウィンドウで、構成する受信ハンドラーを右クリックし をクリック、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="cfa60-122">In the expanded adapter list, click **WCF-Custom**, in the right pane, right-click the receive handler that you want to configure, and then click **Properties**.</span></span>  
  
3. <span data-ttu-id="cfa60-123">**アダプター ハンドラーのプロパティ** ダイアログ ボックスの 、**全般** タブで、**ホスト名**一覧で、受信ハンドラーが関連付けられている場合、あるホストを選択し、クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="cfa60-123">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the receive handler will be associated, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="cfa60-124">**Wcf-custom トランスポートのプロパティ** ダイアログ ボックスの 、 **WCF 拡張機能** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="cfa60-124">In the **WCF-Custom Transport Properties** dialog box, on the **WCF Extensions** tab, do the following:</span></span>  
  
   |<span data-ttu-id="cfa60-125">プロパティ</span><span class="sxs-lookup"><span data-stu-id="cfa60-125">Use this</span></span>|<span data-ttu-id="cfa60-126">目的</span><span class="sxs-lookup"><span data-stu-id="cfa60-126">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="cfa60-127">**[インポート]**</span><span class="sxs-lookup"><span data-stu-id="cfa60-127">**Import**</span></span>|<span data-ttu-id="cfa60-128">WCF カスタム動作拡張機能を持つ WCF 構成ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="cfa60-128">Imports a WCF configuration file with WCF custom behavior extensions.</span></span> <span data-ttu-id="cfa60-129">このボタンをクリックすると、 **WCF 構成のインポート** ダイアログ ボックスを参照して、WCF 構成ファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="cfa60-129">Clicking this button opens the **Import WCF configuration** dialog box to browse and locate a WCF configuration file.</span></span> <span data-ttu-id="cfa60-130">ファイルは有効な WCF 構成ファイルである必要がありますに注意してください。</span><span class="sxs-lookup"><span data-stu-id="cfa60-130">Note that the file should be a valid WCF configuration file.</span></span> <span data-ttu-id="cfa60-131">WCF 構成スキーマの詳細についてを参照してください「Windows Communication Foundation 構成スキーマ」 [ http://go.microsoft.com/fwlink/?LinkId=163953](http://go.microsoft.com/fwlink/?LinkId=163953)します。</span><span class="sxs-lookup"><span data-stu-id="cfa60-131">For more information about WCF configuration schema, see “Windows Communication Foundation Configuration Schema” at [http://go.microsoft.com/fwlink/?LinkId=163953](http://go.microsoft.com/fwlink/?LinkId=163953).</span></span>|  
   |<span data-ttu-id="cfa60-132">**[エクスポート]**</span><span class="sxs-lookup"><span data-stu-id="cfa60-132">**Export**</span></span>|<span data-ttu-id="cfa60-133">WCF カスタム動作拡張機能を WCF 構成ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="cfa60-133">Exports the WCF custom behavior extension to a WCF configuration file.</span></span> <span data-ttu-id="cfa60-134">このボタンをクリックすると、 **WCF 構成のエクスポート** ダイアログ ボックスを参照して、WCF 構成ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="cfa60-134">Clicking this button opens the **Export WCF configuration** dialog box to browse and save the WCF configuration file.</span></span>|  
   |<span data-ttu-id="cfa60-135">**Clear**</span><span class="sxs-lookup"><span data-stu-id="cfa60-135">**Clear**</span></span>|<span data-ttu-id="cfa60-136">アダプター ハンドラーのプロパティから既存の WCF カスタム動作拡張機能をクリアします。</span><span class="sxs-lookup"><span data-stu-id="cfa60-136">Clears the existing WCF custom behavior extension from the adapter handler properties.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cfa60-137">参照</span><span class="sxs-lookup"><span data-stu-id="cfa60-137">See Also</span></span>  
 [<span data-ttu-id="cfa60-138">WCF-Custom アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="cfa60-138">Configuring the WCF-Custom Adapter</span></span>](../core/configuring-the-wcf-custom-adapter.md)