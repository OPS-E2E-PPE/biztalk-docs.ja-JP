---
title: Wcf-nettcp 送信ハンドラーを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send handlers, WCF-NetTcp adapters
- configuring [WCF-NetTcp adapters], send handlers
- WCF-NetTcp adapters, global variables
- configuring [WCF-NetTcp adapters], global variables
ms.assetid: c60fe03d-7e11-4e08-9a24-8ff443eee9c1
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84506c0d5045fca3f8c914e80bf062edf270eaa5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342104"
---
# <a name="how-to-configure-a-wcf-nettcp-send-handler"></a><span data-ttu-id="8c2dc-102">WCF-NetTcp 送信ハンドラーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="8c2dc-102">How to Configure a WCF-NetTcp Send Handler</span></span>
<span data-ttu-id="8c2dc-103">送信ハンドラーを Wcf-nettcp を構成するのには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="8c2dc-103">Use the following procedure to configure a WCF-NetTcp send handler.</span></span>  

### <a name="to-change-global-variables-for-a-wcf-nettcp-send-handler"></a><span data-ttu-id="8c2dc-104">グローバル変数を Wcf-nettcp 送信ハンドラーを変更するには</span><span class="sxs-lookup"><span data-stu-id="8c2dc-104">To change global variables for a WCF-NetTcp send handler</span></span>  

1. <span data-ttu-id="8c2dc-105">BizTalk 管理コンソールで、 [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**を展開し**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="8c2dc-105">In the BizTalk Administration Console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  

2. <span data-ttu-id="8c2dc-106">展開したアダプターの一覧でクリックして**Wcf-nettcp**、右側のウィンドウで、構成する送信ハンドラーを右クリックし をクリック、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="8c2dc-106">In the expanded adapter list, click **WCF-NetTcp**, in the right pane, right-click the send handler that you want to configure, and then click **Properties**.</span></span>  

3. <span data-ttu-id="8c2dc-107">**アダプター ハンドラーのプロパティ** ダイアログ ボックスの 、**全般** タブで、**ホスト名**一覧で、送信ハンドラーが関連付けられているが、ホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="8c2dc-107">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the send handler will be associated.</span></span>  

4. <span data-ttu-id="8c2dc-108">**全般**] タブで [**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="8c2dc-108">On the **General** tab, click **Properties**.</span></span> <span data-ttu-id="8c2dc-109">**送信ハンドラー**  タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8c2dc-109">On the **Send handler** tab, do the following.</span></span>  


   |        <span data-ttu-id="8c2dc-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="8c2dc-110">Use this</span></span>         |                                                                                                                                                                                                                                                                          <span data-ttu-id="8c2dc-111">目的</span><span class="sxs-lookup"><span data-stu-id="8c2dc-111">To do this</span></span>                                                                                                                                                                                                                                                                          |
   |-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="8c2dc-112">**接続の最大数**</span><span class="sxs-lookup"><span data-stu-id="8c2dc-112">**Maximum connections**</span></span> | <span data-ttu-id="8c2dc-113">接続プールにキャッシュされている各エンドポイントの発信接続の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="8c2dc-113">Specify the maximum number of outbound connections for each endpoint that is cached in the connection pool.</span></span> <span data-ttu-id="8c2dc-114">これによって、一意のリモート エンドポイントのそれぞれに対してキャッシュされる接続数が制限されます。</span><span class="sxs-lookup"><span data-stu-id="8c2dc-114">This limits the number of connections that are cached for each unique remote endpoint.</span></span> <span data-ttu-id="8c2dc-115">この値は、一意のリモート エンドポイントに対してキャッシュされることを想定している最大接続数よりも大きい値に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c2dc-115">You should set this value to be greater than the maximum number of connections that you expect to be cached for any unique remote endpoint.</span></span> <span data-ttu-id="8c2dc-116">アクティブな発信接続の数を超える場合、この最大値、サービスは、この送信ハンドラーで実行されている Wcf-nettcp 送信ポートに応答しないように見える場合があります。</span><span class="sxs-lookup"><span data-stu-id="8c2dc-116">If the number of active outbound connections exceeds this maximum value, then the service may appear unresponsive to the WCF-NetTcp send ports running under this send hander.</span></span><br /><br /> <span data-ttu-id="8c2dc-117">既定値は 10 です。</span><span class="sxs-lookup"><span data-stu-id="8c2dc-117">The default is 10.</span></span> |


5. <span data-ttu-id="8c2dc-118">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c2dc-118">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="8c2dc-119">参照</span><span class="sxs-lookup"><span data-stu-id="8c2dc-119">See Also</span></span>  
 <span data-ttu-id="8c2dc-120">[WCF サービスの使用](../core/consuming-wcf-services.md) </span><span class="sxs-lookup"><span data-stu-id="8c2dc-120">[Consuming WCF Services](../core/consuming-wcf-services.md) </span></span>  
 [<span data-ttu-id="8c2dc-121">WCF-NetTcp アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="8c2dc-121">Configuring the WCF-NetTcp Adapter</span></span>](../core/configuring-the-wcf-nettcp-adapter.md)