---
title: Wcf-nettcp 受信ハンドラーを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-NetTcp adapters, global variables
- receive handlers, WCF-NetTcp adapters
- configuring [WCF-NetTcp adapters], global variables
- configuring [WCF-NetTcp adapters], receive handlers
ms.assetid: a4a283d1-21de-4d6b-9cb5-f2f9f823903b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8d7e68e4df5a729aae7f84932b53d319fea0114
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009947"
---
# <a name="how-to-configure-a-wcf-nettcp-receive-handler"></a><span data-ttu-id="9ab5f-102">WCF-NetTcp 受信ハンドラーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="9ab5f-102">How to Configure a WCF-NetTcp Receive Handler</span></span>
<span data-ttu-id="9ab5f-103">WCF-NetTcp 受信ハンドラーを構成するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="9ab5f-103">Use the following procedure to configure a WCF-NetTcp receive handler.</span></span>  

### <a name="to-change-global-variables-for-a-wcf-nettcp-receive-handler"></a><span data-ttu-id="9ab5f-104">WCF-NetTcp 受信ハンドラーのグローバル変数を変更するには</span><span class="sxs-lookup"><span data-stu-id="9ab5f-104">To change global variables for a WCF-NetTcp receive handler</span></span>  

1. <span data-ttu-id="9ab5f-105">BizTalk 管理コンソールで、 [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**を展開し**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="9ab5f-105">In the BizTalk Administration Console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  

2. <span data-ttu-id="9ab5f-106">展開したアダプターの一覧でクリックして**Wcf-nettcp**、右側のウィンドウで、構成する受信ハンドラーを右クリックし をクリック、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="9ab5f-106">In the expanded adapter list, click **WCF-NetTcp**, in the right pane, right-click the receive handler that you want to configure, and then click **Properties**.</span></span>  

3. <span data-ttu-id="9ab5f-107">**アダプター ハンドラーのプロパティ** ダイアログ ボックスの 、**全般** タブで、**ホスト名**一覧で、受信ハンドラーが関連付けられているが、ホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="9ab5f-107">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the receive handler will be associated.</span></span>  

4. <span data-ttu-id="9ab5f-108">**全般** タブで **プロパティ**の**受信ハンドラー**  タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9ab5f-108">In the **General** tab, click **Properties**, On the **Receive handler** tab, do the following.</span></span>  


   |        <span data-ttu-id="9ab5f-109">プロパティ</span><span class="sxs-lookup"><span data-stu-id="9ab5f-109">Use this</span></span>         |                                                                                                                         <span data-ttu-id="9ab5f-110">目的</span><span class="sxs-lookup"><span data-stu-id="9ab5f-110">To do this</span></span>                                                                                                                         |
   |-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="9ab5f-111">**接続の最大数**</span><span class="sxs-lookup"><span data-stu-id="9ab5f-111">**Maximum connections**</span></span> | <span data-ttu-id="9ab5f-112">リスナーが保持することができる、アプリケーションによる受け入れを待機する接続の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="9ab5f-112">Specify the maximum number of connections that the listener can have waiting to be accepted by the application.</span></span> <span data-ttu-id="9ab5f-113">この数を超えた場合、新しい受信接続は受け入れを待機する代わりに削除されます。</span><span class="sxs-lookup"><span data-stu-id="9ab5f-113">When this quota value is exceeded, new incoming connections are dropped rather than waiting to be accepted.</span></span><br /><br /> <span data-ttu-id="9ab5f-114">既定値は 10 です。</span><span class="sxs-lookup"><span data-stu-id="9ab5f-114">The default is 10.</span></span> |


5. <span data-ttu-id="9ab5f-115">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ab5f-115">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="9ab5f-116">参照</span><span class="sxs-lookup"><span data-stu-id="9ab5f-116">See Also</span></span>  
 <span data-ttu-id="9ab5f-117">[Wcf-nettcp アダプターを構成します。](../core/configuring-the-wcf-nettcp-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="9ab5f-117">[Configuring the WCF-NetTcp Adapter](../core/configuring-the-wcf-nettcp-adapter.md) </span></span>  
 [<span data-ttu-id="9ab5f-118">WCF サービスの公開</span><span class="sxs-lookup"><span data-stu-id="9ab5f-118">Publishing WCF Services</span></span>](../core/publishing-wcf-services.md)