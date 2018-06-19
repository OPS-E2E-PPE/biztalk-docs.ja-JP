---
title: Wcf-netnamedpipe 送信ハンドラーを構成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-NetNamedPipe adapters, global adapters
- configuring [WCF-NetNamedPipe adapters], global adapters
- send handlers, WCF-NetNamedPipe adapters
- configuring [WCF-NetNamedPipe adapters], send handlers
ms.assetid: 1f281649-d09f-44eb-8af5-1f83233fab60
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 079d490ab8af28292c5f6adc6d98c8f64c5b16fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248018"
---
# <a name="how-to-configure-a-wcf-netnamedpipe-send-handler"></a><span data-ttu-id="408fc-102">WCF-NetNamedPipe 送信ハンドラーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="408fc-102">How to Configure a WCF-NetNamedPipe Send Handler</span></span>
<span data-ttu-id="408fc-103">WCF-NetNamedPipe 送信ハンドラーを構成するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="408fc-103">Use the following procedure to configure a WCF-NetNamedPipe send handler.</span></span>  
  
### <a name="to-change-global-variables-for-a-wcf-netnamedpipe-send-handler"></a><span data-ttu-id="408fc-104">WCF-NetNamedPipe 送信ハンドラーのグローバル変数を変更するには</span><span class="sxs-lookup"><span data-stu-id="408fc-104">To change global variables for a WCF-NetNamedPipe send handler</span></span>  
  
1.  <span data-ttu-id="408fc-105">BizTalk Server 管理コンソールで、展開[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**を順に展開**アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="408fc-105">In the BizTalk Server Administration console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="408fc-106">展開したアダプターの一覧でクリックして**Wcf-netnamedpipe**、右側のペインで、構成する送信ハンドラを右クリックしをクリック**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="408fc-106">In the expanded adapter list, click **WCF-NetNamedPipe**, in the right pane, right-click the send handler that you want to configure, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="408fc-107">**アダプター ハンドラーのプロパティ** ダイアログ ボックスで、**全般** タブの 、**ホスト名**一覧で、送信ハンドラーが関連付けられる、ホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="408fc-107">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the send handler will be associated.</span></span>  
  
4.  <span data-ttu-id="408fc-108">**全般** タブで、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="408fc-108">In the **General** tab, click **Properties**.</span></span> <span data-ttu-id="408fc-109">**送信ハンドラー**  タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="408fc-109">On the **Send handler** tab, do the following:</span></span>  
  
    |<span data-ttu-id="408fc-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="408fc-110">Use this</span></span>|<span data-ttu-id="408fc-111">目的</span><span class="sxs-lookup"><span data-stu-id="408fc-111">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="408fc-112">**接続の最大数**</span><span class="sxs-lookup"><span data-stu-id="408fc-112">**Maximum connections**</span></span>|<span data-ttu-id="408fc-113">接続プール内にキャッシュされている各エンドポイントの最大送信接続数を指定します。</span><span class="sxs-lookup"><span data-stu-id="408fc-113">Specify the maximum number of outbound connections for each endpoint that is cached in the connection pool.</span></span> <span data-ttu-id="408fc-114">これによって、一意のリモート エンドポイントのそれぞれに対してキャッシュされる接続数が制限されます。</span><span class="sxs-lookup"><span data-stu-id="408fc-114">This limits the number of connections that are cached for each unique remote endpoint.</span></span> <span data-ttu-id="408fc-115">この値は、一意のリモート エンドポイントに対してキャッシュされることを想定している最大接続数よりも大きい値に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="408fc-115">You should set this value to be greater than the maximum number of connections that you expect to be cached for any unique remote endpoint.</span></span> <span data-ttu-id="408fc-116">アクティブな送信接続数がこの最大値を超えると、サービスが、この送信ハンドラーで実行されている WCF-NetNamedPipe 送信ポートに応答していないように見える場合があります。</span><span class="sxs-lookup"><span data-stu-id="408fc-116">If the number of active outbound connections exceeds this maximum value, then the service may appear unresponsive to the WCF-NetNamedPipe send ports running under this send hander.</span></span><br /><br /> <span data-ttu-id="408fc-117">既定値は、10 です。</span><span class="sxs-lookup"><span data-stu-id="408fc-117">The default is 10.</span></span>|  
  
5.  <span data-ttu-id="408fc-118">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="408fc-118">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="408fc-119">参照</span><span class="sxs-lookup"><span data-stu-id="408fc-119">See Also</span></span>  
 <span data-ttu-id="408fc-120">[WCF サービスの使用](../core/consuming-wcf-services.md) </span><span class="sxs-lookup"><span data-stu-id="408fc-120">[Consuming WCF Services](../core/consuming-wcf-services.md) </span></span>  
 [<span data-ttu-id="408fc-121">Wcf-netnamedpipe アダプタを構成します。</span><span class="sxs-lookup"><span data-stu-id="408fc-121">Configuring the WCF-NetNamedPipe Adapter</span></span>](../core/configuring-the-wcf-netnamedpipe-adapter.md)