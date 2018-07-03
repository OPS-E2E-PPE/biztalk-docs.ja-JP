---
title: サービスの送信ハンドラーを Windows SharePoint を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [Windows SharePoint Services adapters], send handlers
- send handlers, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, send handlers
ms.assetid: 457767d9-6e39-4553-9bbe-212fcb7c04bc
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90ac23759558549122f31a793852b479b67744d4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988555"
---
# <a name="how-to-configure-a-windows-sharepoint-services-send-handler"></a><span data-ttu-id="f130a-102">Windows SharePoint Services 送信ハンドラを構成する方法</span><span class="sxs-lookup"><span data-stu-id="f130a-102">How to Configure a Windows SharePoint Services Send Handler</span></span>
<span data-ttu-id="f130a-103">次の手順を使用して、Windows SharePoint Services 送信ハンドラが関連付けられているホストを変更します。</span><span class="sxs-lookup"><span data-stu-id="f130a-103">Use the following procedure to change the host with which the Windows SharePoint Services send handler is associated.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f130a-104">各ホストに関連付けられる送信ハンドラーは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="f130a-104">Each host can have only one send handler associated with it.</span></span>  
  
### <a name="to-change-global-variables-for-a-windows-sharepoint-services-send-handler"></a><span data-ttu-id="f130a-105">Windows SharePoint Services 送信ハンドラのグローバル変数を変更するには</span><span class="sxs-lookup"><span data-stu-id="f130a-105">To change global variables for a Windows SharePoint Services send handler</span></span>  
  
1. <span data-ttu-id="f130a-106">BizTalk Server 管理コンソールで、クリックして展開[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**をクリックして展開と**BizTalk グループ [\<servername\>:\<管理データベース\>]** をクリックして展開**プラットフォームの設定**をクリックして展開と**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="f130a-106">In the BizTalk Server Administration console, click to expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, and then click to expand **BizTalk Group [\<servername\>:\<management database\>]**, click to expand **Platform Settings**, and then click to expand **Adapters**.</span></span> <span data-ttu-id="f130a-107">フォルダの下にアダプタの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f130a-107">The list of adapters appears under the folder.</span></span>  
  
2. <span data-ttu-id="f130a-108">クリックして**Windows SharePoint Services**、右側のウィンドウで、構成、およびクリックする送信ハンドラーを右クリック**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="f130a-108">Click **Windows SharePoint Services**, and in the right pane, right-click the send handler that you want to configure, and then click **Properties**.</span></span>  
  
3. <span data-ttu-id="f130a-109">**アダプター ハンドラーのプロパティ** ダイアログ ボックスの 、**全般** タブで、**ホスト名**一覧で、送信ハンドラーが関連付けられているが、ホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="f130a-109">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the send handler will be associated.</span></span>  
  
4. <span data-ttu-id="f130a-110">**全般**] タブで [**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="f130a-110">On the **General** tab, click **Properties**.</span></span>  
  
5. <span data-ttu-id="f130a-111">**Windows SharePoint Services トランスポート プロパティ** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f130a-111">In the **Windows SharePoint Services Transport Properties** dialog box, do the following:</span></span>  
  
   |<span data-ttu-id="f130a-112">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f130a-112">Use this</span></span>|<span data-ttu-id="f130a-113">目的</span><span class="sxs-lookup"><span data-stu-id="f130a-113">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="f130a-114">[送信バッチ サイズ]</span><span class="sxs-lookup"><span data-stu-id="f130a-114">Send Batch Size</span></span>|<span data-ttu-id="f130a-115">Windows SharePoint Services の Web サービスがバッチとして処理するドキュメントの最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="f130a-115">The maximum number of documents that the Windows SharePoint Services Web service will process as a batch.</span></span> <span data-ttu-id="f130a-116">既定値は 20 です。</span><span class="sxs-lookup"><span data-stu-id="f130a-116">The default is 20.</span></span> <span data-ttu-id="f130a-117">**注:** 最小値は 1 です。</span><span class="sxs-lookup"><span data-stu-id="f130a-117">**Note:**  The minimum value is 1.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f130a-118">参照</span><span class="sxs-lookup"><span data-stu-id="f130a-118">See Also</span></span>  
 <span data-ttu-id="f130a-119">[サービスの受信場所を Windows SharePoint を構成する方法](../core/how-to-configure-a-windows-sharepoint-services-receive-location.md) </span><span class="sxs-lookup"><span data-stu-id="f130a-119">[How to Configure a Windows SharePoint Services Receive Location](../core/how-to-configure-a-windows-sharepoint-services-receive-location.md) </span></span>  
 <span data-ttu-id="f130a-120">[Windows SharePoint Services 送信ポートを構成する方法](../core/how-to-configure-a-windows-sharepoint-services-send-port.md) </span><span class="sxs-lookup"><span data-stu-id="f130a-120">[How to Configure a Windows SharePoint Services Send Port](../core/how-to-configure-a-windows-sharepoint-services-send-port.md) </span></span>  
 <span data-ttu-id="f130a-121">[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md) </span><span class="sxs-lookup"><span data-stu-id="f130a-121">[How to Create a Send Port](../core/how-to-create-a-send-port2.md) </span></span>  
 <span data-ttu-id="f130a-122">[Windows SharePoint Services アダプターのプロパティに関するリファレンス](../core/windows-sharepoint-services-adapter-properties-reference.md) </span><span class="sxs-lookup"><span data-stu-id="f130a-122">[Windows SharePoint Services Adapter Properties Reference](../core/windows-sharepoint-services-adapter-properties-reference.md) </span></span>  
 <span data-ttu-id="f130a-123">[Windows SharePoint Services アダプターの式](../core/windows-sharepoint-services-adapter-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="f130a-123">[Windows SharePoint Services Adapter Expressions](../core/windows-sharepoint-services-adapter-expressions.md) </span></span>  
 [<span data-ttu-id="f130a-124">サポートされている Windows SharePoint Services 列の型</span><span class="sxs-lookup"><span data-stu-id="f130a-124">Supported Windows SharePoint Services Column Types</span></span>](../core/supported-windows-sharepoint-services-column-types.md)