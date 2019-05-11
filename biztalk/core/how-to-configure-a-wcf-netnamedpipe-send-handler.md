---
title: Wcf-netnamedpipe 送信ハンドラーを構成する方法 |Microsoft Docs
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
ms.openlocfilehash: 69941385bdadc3670a88fd48c37fb77e22657752
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342215"
---
# <a name="how-to-configure-a-wcf-netnamedpipe-send-handler"></a><span data-ttu-id="affbe-102">WCF-NetNamedPipe 送信ハンドラーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="affbe-102">How to Configure a WCF-NetNamedPipe Send Handler</span></span>
<span data-ttu-id="affbe-103">送信ハンドラーを Wcf-netnamedpipe を構成するのには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="affbe-103">Use the following procedure to configure a WCF-NetNamedPipe send handler.</span></span>  

### <a name="to-change-global-variables-for-a-wcf-netnamedpipe-send-handler"></a><span data-ttu-id="affbe-104">グローバル変数を Wcf-netnamedpipe 送信ハンドラーを変更するには</span><span class="sxs-lookup"><span data-stu-id="affbe-104">To change global variables for a WCF-NetNamedPipe send handler</span></span>  

1. <span data-ttu-id="affbe-105">BizTalk Server 管理コンソールで  [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**順に展開**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="affbe-105">In the BizTalk Server Administration console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  

2. <span data-ttu-id="affbe-106">展開したアダプターの一覧でクリックして**Wcf-netnamedpipe**、右側のウィンドウで、構成する送信ハンドラーを右クリックし をクリック、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="affbe-106">In the expanded adapter list, click **WCF-NetNamedPipe**, in the right pane, right-click the send handler that you want to configure, and then click **Properties**.</span></span>  

3. <span data-ttu-id="affbe-107">**アダプター ハンドラーのプロパティ** ダイアログ ボックスの 、**全般** タブで、**ホスト名**一覧で、送信ハンドラーが関連付けられているが、ホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="affbe-107">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the send handler will be associated.</span></span>  

4. <span data-ttu-id="affbe-108">**全般**] タブで [**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="affbe-108">In the **General** tab, click **Properties**.</span></span> <span data-ttu-id="affbe-109">**送信ハンドラー**  タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="affbe-109">On the **Send handler** tab, do the following:</span></span>  


   |        <span data-ttu-id="affbe-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="affbe-110">Use this</span></span>         |                                                                                                                                                                                                                                                                             <span data-ttu-id="affbe-111">目的</span><span class="sxs-lookup"><span data-stu-id="affbe-111">To do this</span></span>                                                                                                                                                                                                                                                                             |
   |-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="affbe-112">**接続の最大数**</span><span class="sxs-lookup"><span data-stu-id="affbe-112">**Maximum connections**</span></span> | <span data-ttu-id="affbe-113">接続プールにキャッシュされている各エンドポイントの発信接続の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="affbe-113">Specify the maximum number of outbound connections for each endpoint that is cached in the connection pool.</span></span> <span data-ttu-id="affbe-114">これによって、一意のリモート エンドポイントのそれぞれに対してキャッシュされる接続数が制限されます。</span><span class="sxs-lookup"><span data-stu-id="affbe-114">This limits the number of connections that are cached for each unique remote endpoint.</span></span> <span data-ttu-id="affbe-115">この値は、一意のリモート エンドポイントに対してキャッシュされることを想定している最大接続数よりも大きい値に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="affbe-115">You should set this value to be greater than the maximum number of connections that you expect to be cached for any unique remote endpoint.</span></span> <span data-ttu-id="affbe-116">アクティブな発信接続の数を超える場合、この最大値、サービスは、この送信ハンドラーで実行されている Wcf-netnamedpipe 送信ポートに応答しないように見える場合があります。</span><span class="sxs-lookup"><span data-stu-id="affbe-116">If the number of active outbound connections exceeds this maximum value, then the service may appear unresponsive to the WCF-NetNamedPipe send ports running under this send hander.</span></span><br /><br /> <span data-ttu-id="affbe-117">既定値は 10 です。</span><span class="sxs-lookup"><span data-stu-id="affbe-117">The default is 10.</span></span> |


5. <span data-ttu-id="affbe-118">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="affbe-118">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="affbe-119">参照</span><span class="sxs-lookup"><span data-stu-id="affbe-119">See Also</span></span>  
 <span data-ttu-id="affbe-120">[WCF サービスの使用](../core/consuming-wcf-services.md) </span><span class="sxs-lookup"><span data-stu-id="affbe-120">[Consuming WCF Services](../core/consuming-wcf-services.md) </span></span>  
 [<span data-ttu-id="affbe-121">WCF-NetNamedPipe アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="affbe-121">Configuring the WCF-NetNamedPipe Adapter</span></span>](../core/configuring-the-wcf-netnamedpipe-adapter.md)