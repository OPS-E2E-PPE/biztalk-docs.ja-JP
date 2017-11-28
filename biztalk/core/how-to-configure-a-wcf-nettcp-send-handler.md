---
title: "Wcf-nettcp 送信ハンドラーを構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send handlers, WCF-NetTcp adapters
- configuring [WCF-NetTcp adapters], send handlers
- WCF-NetTcp adapters, global variables
- configuring [WCF-NetTcp adapters], global variables
ms.assetid: c60fe03d-7e11-4e08-9a24-8ff443eee9c1
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02451dba6755e4db0c10d7cce20141468a67694f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-a-wcf-nettcp-send-handler"></a><span data-ttu-id="58a31-102">WCF-NetTcp 送信ハンドラーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="58a31-102">How to Configure a WCF-NetTcp Send Handler</span></span>
<span data-ttu-id="58a31-103">WCF-NetTcp 送信ハンドラーを構成するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="58a31-103">Use the following procedure to configure a WCF-NetTcp send handler.</span></span>  
  
### <a name="to-change-global-variables-for-a-wcf-nettcp-send-handler"></a><span data-ttu-id="58a31-104">WCF-NetTcp 送信ハンドラーのグローバル変数を変更するには</span><span class="sxs-lookup"><span data-stu-id="58a31-104">To change global variables for a WCF-NetTcp send handler</span></span>  
  
1.  <span data-ttu-id="58a31-105">BizTalk 管理コンソールで  [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**の順に展開および**アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="58a31-105">In the BizTalk Administration Console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="58a31-106">展開したアダプターの一覧でクリックして**Wcf-nettcp**、右側のペインで、構成する送信ハンドラを右クリックしをクリック**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="58a31-106">In the expanded adapter list, click **WCF-NetTcp**, in the right pane, right-click the send handler that you want to configure, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="58a31-107">**アダプター ハンドラーのプロパティ** ダイアログ ボックスで、**全般** タブの 、**ホスト名**一覧で、送信ハンドラーが関連付けられる、ホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="58a31-107">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the send handler will be associated.</span></span>  
  
4.  <span data-ttu-id="58a31-108">**全般** タブで、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="58a31-108">On the **General** tab, click **Properties**.</span></span> <span data-ttu-id="58a31-109">**送信ハンドラー**  タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="58a31-109">On the **Send handler** tab, do the following.</span></span>  
  
    |<span data-ttu-id="58a31-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="58a31-110">Use this</span></span>|<span data-ttu-id="58a31-111">目的</span><span class="sxs-lookup"><span data-stu-id="58a31-111">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="58a31-112">**接続の最大数**</span><span class="sxs-lookup"><span data-stu-id="58a31-112">**Maximum connections**</span></span>|<span data-ttu-id="58a31-113">接続プール内にキャッシュされている各エンドポイントの最大送信接続数を指定します。</span><span class="sxs-lookup"><span data-stu-id="58a31-113">Specify the maximum number of outbound connections for each endpoint that is cached in the connection pool.</span></span> <span data-ttu-id="58a31-114">これによって、一意のリモート エンドポイントのそれぞれに対してキャッシュされる接続数が制限されます。</span><span class="sxs-lookup"><span data-stu-id="58a31-114">This limits the number of connections that are cached for each unique remote endpoint.</span></span> <span data-ttu-id="58a31-115">この値は、一意のリモート エンドポイントに対してキャッシュされることを想定している最大接続数よりも大きい値に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58a31-115">You should set this value to be greater than the maximum number of connections that you expect to be cached for any unique remote endpoint.</span></span> <span data-ttu-id="58a31-116">アクティブな送信接続数がこの最大値を超えると、サービスが、この送信ハンドラーで実行されている WCF-NetTcp 送信ポートに応答していないように見える場合があります。</span><span class="sxs-lookup"><span data-stu-id="58a31-116">If the number of active outbound connections exceeds this maximum value, then the service may appear unresponsive to the WCF-NetTcp send ports running under this send hander.</span></span><br /><br /> <span data-ttu-id="58a31-117">既定値は、10 です。</span><span class="sxs-lookup"><span data-stu-id="58a31-117">The default is 10.</span></span>|  
  
5.  <span data-ttu-id="58a31-118">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58a31-118">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58a31-119">参照</span><span class="sxs-lookup"><span data-stu-id="58a31-119">See Also</span></span>  
 <span data-ttu-id="58a31-120">[WCF サービスの使用](../core/consuming-wcf-services.md) </span><span class="sxs-lookup"><span data-stu-id="58a31-120">[Consuming WCF Services](../core/consuming-wcf-services.md) </span></span>  
 [<span data-ttu-id="58a31-121">Wcf-nettcp アダプターを構成します。</span><span class="sxs-lookup"><span data-stu-id="58a31-121">Configuring the WCF-NetTcp Adapter</span></span>](../core/configuring-the-wcf-nettcp-adapter.md)