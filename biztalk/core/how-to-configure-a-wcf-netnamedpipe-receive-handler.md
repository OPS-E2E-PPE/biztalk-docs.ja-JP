---
title: Wcf-netnamedpipe 受信ハンドラーを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [WCF-NetNamedPipe adapters], global variables
- receive handlers, WCF-NetNamedPipe adapters
- configuring [WCF-NetNamedPipe adapters], receive handlers
- WCF-NetNamedPipe adapters, global variables
ms.assetid: f7ab2228-1049-40f0-87f7-6330a8f40cfe
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6a56fbeca1e2e6d362cef94dd6aa68161152b4b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342222"
---
# <a name="how-to-configure-a-wcf-netnamedpipe-receive-handler"></a><span data-ttu-id="627db-102">WCF-NetNamedPipe 受信ハンドラーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="627db-102">How to Configure a WCF-NetNamedPipe Receive Handler</span></span>
<span data-ttu-id="627db-103">受信ハンドラーを Wcf-netnamedpipe を構成するのには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="627db-103">Use the following procedure to configure a WCF-NetNamedPipe receive handler.</span></span>  

### <a name="to-change-global-variables-for-a-wcf-netnamedpipe-receive-handler"></a><span data-ttu-id="627db-104">グローバル変数を Wcf-netnamedpipe 受信ハンドラーを変更するには</span><span class="sxs-lookup"><span data-stu-id="627db-104">To change global variables for a WCF-NetNamedPipe receive handler</span></span>  

1. <span data-ttu-id="627db-105">BizTalk 管理コンソールで  [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**を展開し**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="627db-105">In the BizTalk Administration console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  

2. <span data-ttu-id="627db-106">展開したアダプターの一覧でクリックして**Wcf-netnamedpipe**、右側のウィンドウで、構成する受信ハンドラーを右クリックし をクリック、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="627db-106">In the expanded adapter list, click **WCF-NetNamedPipe**, in the right pane, right-click the receive handler that you want to configure, and then click **Properties**.</span></span>  

3. <span data-ttu-id="627db-107">**アダプター ハンドラーのプロパティ** ダイアログ ボックスの 、**全般** タブで、**ホスト名**一覧で、受信ハンドラーが関連付けられているが、ホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="627db-107">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the receive handler will be associated.</span></span>  

4. <span data-ttu-id="627db-108">**全般**] タブで [**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="627db-108">In the **General** tab, click **Properties**.</span></span> <span data-ttu-id="627db-109">**受信ハンドラー**  タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="627db-109">On the **Receive handler** tab, do the following:</span></span>  


   |        <span data-ttu-id="627db-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="627db-110">Use this</span></span>         |                                                                                                                         <span data-ttu-id="627db-111">目的</span><span class="sxs-lookup"><span data-stu-id="627db-111">To do this</span></span>                                                                                                                         |
   |-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="627db-112">**接続の最大数**</span><span class="sxs-lookup"><span data-stu-id="627db-112">**Maximum connections**</span></span> | <span data-ttu-id="627db-113">リスナーが保持することができる、アプリケーションによる受け入れを待機する接続の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="627db-113">Specify the maximum number of connections that the listener can have waiting to be accepted by the application.</span></span> <span data-ttu-id="627db-114">この数を超えた場合、新しい受信接続は受け入れを待機する代わりに削除されます。</span><span class="sxs-lookup"><span data-stu-id="627db-114">When this quota value is exceeded, new incoming connections are dropped rather than waiting to be accepted.</span></span><br /><br /> <span data-ttu-id="627db-115">既定値は 10 です。</span><span class="sxs-lookup"><span data-stu-id="627db-115">The default is 10.</span></span> |


5. <span data-ttu-id="627db-116">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="627db-116">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="627db-117">参照</span><span class="sxs-lookup"><span data-stu-id="627db-117">See Also</span></span>  
 <span data-ttu-id="627db-118">[WCF サービスの公開](../core/publishing-wcf-services.md) </span><span class="sxs-lookup"><span data-stu-id="627db-118">[Publishing WCF Services](../core/publishing-wcf-services.md) </span></span>  
 [<span data-ttu-id="627db-119">WCF-NetNamedPipe アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="627db-119">Configuring the WCF-NetNamedPipe Adapter</span></span>](../core/configuring-the-wcf-netnamedpipe-adapter.md)