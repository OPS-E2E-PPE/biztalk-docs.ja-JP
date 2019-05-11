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
ms.openlocfilehash: 48133eaa50fed0062b17d9e3b25fe180d7495f89
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342194"
---
# <a name="how-to-configure-a-wcf-nettcp-receive-handler"></a><span data-ttu-id="60d88-102">WCF-NetTcp 受信ハンドラーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="60d88-102">How to Configure a WCF-NetTcp Receive Handler</span></span>
<span data-ttu-id="60d88-103">受信ハンドラーを Wcf-nettcp を構成するのには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="60d88-103">Use the following procedure to configure a WCF-NetTcp receive handler.</span></span>  

### <a name="to-change-global-variables-for-a-wcf-nettcp-receive-handler"></a><span data-ttu-id="60d88-104">グローバル変数を Wcf-nettcp 受信ハンドラーを変更するには</span><span class="sxs-lookup"><span data-stu-id="60d88-104">To change global variables for a WCF-NetTcp receive handler</span></span>  

1. <span data-ttu-id="60d88-105">BizTalk 管理コンソールで、 [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**を展開し**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="60d88-105">In the BizTalk Administration Console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  

2. <span data-ttu-id="60d88-106">展開したアダプターの一覧でクリックして**Wcf-nettcp**、右側のウィンドウで、構成する受信ハンドラーを右クリックし をクリック、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="60d88-106">In the expanded adapter list, click **WCF-NetTcp**, in the right pane, right-click the receive handler that you want to configure, and then click **Properties**.</span></span>  

3. <span data-ttu-id="60d88-107">**アダプター ハンドラーのプロパティ** ダイアログ ボックスの 、**全般** タブで、**ホスト名**一覧で、受信ハンドラーが関連付けられているが、ホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="60d88-107">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the receive handler will be associated.</span></span>  

4. <span data-ttu-id="60d88-108">**全般** タブで **プロパティ**の**受信ハンドラー**  タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="60d88-108">In the **General** tab, click **Properties**, On the **Receive handler** tab, do the following.</span></span>  


   |        <span data-ttu-id="60d88-109">プロパティ</span><span class="sxs-lookup"><span data-stu-id="60d88-109">Use this</span></span>         |                                                                                                                         <span data-ttu-id="60d88-110">目的</span><span class="sxs-lookup"><span data-stu-id="60d88-110">To do this</span></span>                                                                                                                         |
   |-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="60d88-111">**接続の最大数**</span><span class="sxs-lookup"><span data-stu-id="60d88-111">**Maximum connections**</span></span> | <span data-ttu-id="60d88-112">リスナーが保持することができる、アプリケーションによる受け入れを待機する接続の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="60d88-112">Specify the maximum number of connections that the listener can have waiting to be accepted by the application.</span></span> <span data-ttu-id="60d88-113">この数を超えた場合、新しい受信接続は受け入れを待機する代わりに削除されます。</span><span class="sxs-lookup"><span data-stu-id="60d88-113">When this quota value is exceeded, new incoming connections are dropped rather than waiting to be accepted.</span></span><br /><br /> <span data-ttu-id="60d88-114">既定値は 10 です。</span><span class="sxs-lookup"><span data-stu-id="60d88-114">The default is 10.</span></span> |


5. <span data-ttu-id="60d88-115">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60d88-115">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="60d88-116">参照</span><span class="sxs-lookup"><span data-stu-id="60d88-116">See Also</span></span>  
 <span data-ttu-id="60d88-117">[Wcf-nettcp アダプターを構成します。](../core/configuring-the-wcf-nettcp-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="60d88-117">[Configuring the WCF-NetTcp Adapter](../core/configuring-the-wcf-nettcp-adapter.md) </span></span>  
 [<span data-ttu-id="60d88-118">WCF サービスの公開</span><span class="sxs-lookup"><span data-stu-id="60d88-118">Publishing WCF Services</span></span>](../core/publishing-wcf-services.md)