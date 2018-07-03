---
title: Wcf-custom 送信ハンドラーを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00758b87-dffb-488b-9cf3-564d0ccd5938
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a80ec79dd839c4a7e82d17e3b559abf6cba89a6f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996835"
---
# <a name="how-to-configure-a-wcf-custom-send-handler"></a><span data-ttu-id="c75f6-102">WCF-Custom 送信ハンドラーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="c75f6-102">How to Configure a WCF-Custom Send Handler</span></span>
<span data-ttu-id="c75f6-103">[!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)] で、machine.config 以外の場所からカスタム動作拡張機能を検索する場合は、送信ハンドラーのプロパティを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c75f6-103">You must configure the send handler properties if you want the [!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)] to look up the custom behavior extensions from locations other than machine.config.</span></span>  
  
## <a name="why-should-wcf-custom-adapter-look-up-custom-behavior-extensions-from-locations-other-than-machineconfig"></a><span data-ttu-id="c75f6-104">WCF-Custom アダプターが machine.config 以外の場所からカスタム動作拡張機能を検索する理由</span><span class="sxs-lookup"><span data-stu-id="c75f6-104">Why Should WCF-Custom Adapter Look up Custom Behavior Extensions from Locations Other than machine.config?</span></span>  
 <span data-ttu-id="c75f6-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で使用されるカスタム動作拡張機能は、machine.config に登録されています。[!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)] は、動作拡張機能を読み込む前に、machine.config で動作拡張機能を検索します。ただし、machine.config は、特定のコンピューターで実行されているすべてのアプリケーションに必要な構成情報を格納する使用が理想的です。</span><span class="sxs-lookup"><span data-stu-id="c75f6-105">Custom behavior extensions used by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is registered in the machine.config. Before loading the behavior extensions, the [!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)] looks for the behavior extensions in machine.config. However, machine.config is ideally used to store configuration information that is required across all applications running on a particular computer.</span></span> <span data-ttu-id="c75f6-106">一方、WCF カスタム動作拡張機能はコンピューターで実行されているすべてのアプリケーションではなく、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でのみ要求されることがあります。</span><span class="sxs-lookup"><span data-stu-id="c75f6-106">On the other hand, WCF custom behavior extensions may be required only by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and not by all the applications running on the computer.</span></span> <span data-ttu-id="c75f6-107">したがって、machine.config にカスタム動作拡張機能を保存すれば目的にかないますが、ここは最適な場所ではありません。</span><span class="sxs-lookup"><span data-stu-id="c75f6-107">So, while storing the custom behavior extensions in machine.config serves the purpose, it is not the most optimal location.</span></span>  
  
 <span data-ttu-id="c75f6-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、[!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)] がカスタム動作拡張機能を参照するための追加の場所をアダプター ハンドラーのプロパティで指定します。</span><span class="sxs-lookup"><span data-stu-id="c75f6-108">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the adapter handler properties provide an additional location from which the [!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)] can look up the custom behavior extensions.</span></span> <span data-ttu-id="c75f6-109">machine.config で既に利用可能な動作拡張機能を置き換えるものではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c75f6-109">Note that this does not replace the behavior extensions already available in machine.config.</span></span>  
  
### <a name="additional-considerations"></a><span data-ttu-id="c75f6-110">その他の注意点</span><span class="sxs-lookup"><span data-stu-id="c75f6-110">Additional Considerations</span></span>  
 <span data-ttu-id="c75f6-111">WCF-Custom 送信ハンドラーのプロパティを構成する際は、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="c75f6-111">Keep the following points in mind while configuring the WCF-Custom send handler properties:</span></span>  
  
-   <span data-ttu-id="c75f6-112">カスタム動作拡張機能は machine.config かアダプター ハンドラーのプロパティのどちらか一方で利用可能にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c75f6-112">The custom behavior extensions must be available either in the machine.config or in the adapter handler properties.</span></span> <span data-ttu-id="c75f6-113">カスタム動作拡張機能を両方の場所に重複して設定しないでください。</span><span class="sxs-lookup"><span data-stu-id="c75f6-113">The custom behavior extensions must not be duplicated at both locations.</span></span>  
  
-   <span data-ttu-id="c75f6-114">カスタム動作拡張機能が既に machine.config で利用できる場合、同じカスタム動作拡張機能をアダプター ハンドラーのプロパティに設定しようとすると、すぐにエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="c75f6-114">If the custom behavior extension is already available in the machine.config and you try to set the same behavior extension for the adapter handler properties, you get an error as soon as you try to set the property.</span></span>  
  
-   <span data-ttu-id="c75f6-115">カスタム動作拡張機能が既にアダプター ハンドラーのプロパティに設定されている場合、machine.config を同じカスタム動作拡張機能で更新すると、実行時エラーが発生し、イベント ログにも記録されます。</span><span class="sxs-lookup"><span data-stu-id="c75f6-115">If the custom behavior extension is already set for the adapter handler properties and you then update the machine.config with the same behavior extension, you will get a runtime error and it is also logged in the event log.</span></span>  
  
-   <span data-ttu-id="c75f6-116">アダプター ハンドラーのプロパティを設定する前に、カスタム動作拡張機能で参照されるアセンブリがグローバル アセンブリ キャッシュ (GAC) に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c75f6-116">The assemblies referred in the custom behavior extension must be present in the Global Assembly Cache (GAC) before you set the adapter handler properties.</span></span>  
  
## <a name="configuring-the-adapter-handler-properties"></a><span data-ttu-id="c75f6-117">アダプター ハンドラーのプロパティの構成</span><span class="sxs-lookup"><span data-stu-id="c75f6-117">Configuring the Adapter Handler Properties</span></span>  
 <span data-ttu-id="c75f6-118">WCF-Custom 送信ハンドラーを構成するには、このトピックの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c75f6-118">Use the procedure in this topic to configure a WCF-Custom send handler.</span></span>  
  
#### <a name="to-configure-the-adapter-handler-properties"></a><span data-ttu-id="c75f6-119">アダプター ハンドラーのプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="c75f6-119">To configure the adapter handler properties</span></span>  
  
1. <span data-ttu-id="c75f6-120">BizTalk 管理コンソールで、 [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**を展開し**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="c75f6-120">In the BizTalk Administration Console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2. <span data-ttu-id="c75f6-121">展開したアダプターの一覧でクリックして**Wcf-custom**、右側のウィンドウで、構成する送信ハンドラーを右クリックし をクリック、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="c75f6-121">In the expanded adapter list, click **WCF-Custom**, in the right pane, right-click the send handler that you want to configure, and then click **Properties**.</span></span>  
  
3. <span data-ttu-id="c75f6-122">**アダプター ハンドラーのプロパティ** ダイアログ ボックスの 、**全般** タブで、**ホスト名**いる送信ハンドラー、関連付けられているとする をクリックし、ホストを選択します**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="c75f6-122">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the send handler will be associated, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="c75f6-123">**Wcf-custom トランスポートのプロパティ** ダイアログ ボックスの 、 **WCF 拡張機能** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c75f6-123">In the **WCF-Custom Transport Properties** dialog box, on the **WCF Extensions** tab, do the following:</span></span>  
  
   |<span data-ttu-id="c75f6-124">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c75f6-124">Use this</span></span>|<span data-ttu-id="c75f6-125">目的</span><span class="sxs-lookup"><span data-stu-id="c75f6-125">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="c75f6-126">**[インポート]**</span><span class="sxs-lookup"><span data-stu-id="c75f6-126">**Import**</span></span>|<span data-ttu-id="c75f6-127">WCF カスタム動作拡張機能が登録されている WCF 構成ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="c75f6-127">Imports a WCF configuration file with WCF custom behavior extensions.</span></span> <span data-ttu-id="c75f6-128">このボタンをクリックすると、 **WCF 構成のインポート** ダイアログ ボックスを参照して、WCF 構成ファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="c75f6-128">Clicking this button opens the **Import WCF configuration** dialog box to browse and locate a WCF configuration file.</span></span> <span data-ttu-id="c75f6-129">有効な WCF 構成ファイルを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c75f6-129">Note that the file should be a valid WCF configuration file.</span></span> <span data-ttu-id="c75f6-130">WCF 構成スキーマの詳細についてを参照してください「Windows Communication Foundation 構成スキーマ」 [ http://go.microsoft.com/fwlink/?LinkId=163953](http://go.microsoft.com/fwlink/?LinkId=163953)します。</span><span class="sxs-lookup"><span data-stu-id="c75f6-130">For more information about WCF configuration schema, see “Windows Communication Foundation Configuration Schema” at [http://go.microsoft.com/fwlink/?LinkId=163953](http://go.microsoft.com/fwlink/?LinkId=163953).</span></span>|  
   |<span data-ttu-id="c75f6-131">**[エクスポート]**</span><span class="sxs-lookup"><span data-stu-id="c75f6-131">**Export**</span></span>|<span data-ttu-id="c75f6-132">WCF カスタム動作拡張機能を WCF 構成ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="c75f6-132">Exports the WCF custom behavior extension to a WCF configuration file.</span></span> <span data-ttu-id="c75f6-133">このボタンをクリックすると、 **WCF 構成のエクスポート** ダイアログ ボックスを参照して、WCF 構成ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="c75f6-133">Clicking this button opens the **Export WCF configuration** dialog box to browse and save the WCF configuration file.</span></span>|  
   |<span data-ttu-id="c75f6-134">**Clear**</span><span class="sxs-lookup"><span data-stu-id="c75f6-134">**Clear**</span></span>|<span data-ttu-id="c75f6-135">既存の WCF カスタム動作拡張機能をアダプター ハンドラーのプロパティから消去します。</span><span class="sxs-lookup"><span data-stu-id="c75f6-135">Clears the existing WCF custom behavior extension from the adapter handler properties.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c75f6-136">参照</span><span class="sxs-lookup"><span data-stu-id="c75f6-136">See Also</span></span>  
 [<span data-ttu-id="c75f6-137">WCF-Custom アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="c75f6-137">Configuring the WCF-Custom Adapter</span></span>](../core/configuring-the-wcf-custom-adapter.md)