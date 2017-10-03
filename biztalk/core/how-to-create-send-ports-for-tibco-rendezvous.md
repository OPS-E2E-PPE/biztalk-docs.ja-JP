---
title: "TIBCO Rendezvous の送信ポートを作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating send ports
- ports, send
- send ports, creating
ms.assetid: 0c8d9fdc-b273-4876-9f93-b5a85539a3c1
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d0b6e7dbb1a3b32979c94ec1af9483bd9fcb7cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-send-ports-for-tibco-rendezvous"></a><span data-ttu-id="8f181-102">TIBCO Rendezvous の送信ポートを作成する方法</span><span class="sxs-lookup"><span data-stu-id="8f181-102">How to Create Send Ports for TIBCO Rendezvous</span></span>
<span data-ttu-id="8f181-103">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用して送信ポートを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8f181-103">Follow these steps to create a send port using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
### <a name="to-create-a-send-port"></a><span data-ttu-id="8f181-104">送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="8f181-104">To create a send port</span></span>  
  
1.  <span data-ttu-id="8f181-105">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、し、必要な展開アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="8f181-105">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="8f181-106">右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="8f181-106">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="8f181-107">**送信ポートのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="8f181-107">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="8f181-108">たとえば、送信ポートの名前を入力`SendToTIBCORV`です。</span><span class="sxs-lookup"><span data-stu-id="8f181-108">Type a name for the send port, for example, `SendToTIBCORV`.</span></span>  
  
    2.  <span data-ttu-id="8f181-109">**型**ドロップダウン リストで、 **TIBCO Rendezvous**です。</span><span class="sxs-lookup"><span data-stu-id="8f181-109">From the **Type** drop-down list, select **TIBCO Rendezvous**.</span></span>  
  
    3.  <span data-ttu-id="8f181-110">**送信ハンドラー**ドロップダウン リストで、URI を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f181-110">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="8f181-111">送信パイプラインのドロップダウン リストから選択**[microsoft.biztalk.defaultpipelines.xmltransmit]**です。</span><span class="sxs-lookup"><span data-stu-id="8f181-111">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="8f181-112">**受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]**です。</span><span class="sxs-lookup"><span data-stu-id="8f181-112">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
    6.  <span data-ttu-id="8f181-113">をクリックして**構成**送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="8f181-113">Click **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="8f181-114">**TIBCO Rendezvous トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="8f181-114">In the **TIBCO Rendezvous Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="8f181-115">プロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="8f181-115">Enter the properties.</span></span>  
  
         <span data-ttu-id="8f181-116">ログオン情報を設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8f181-116">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="8f181-117">一覧で、TIBCO Rendezvous システムを表すように作成した SSO 関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="8f181-117">In the list, select the SSO affiliate application you created to represent the TIBCO Rendezvous system.</span></span>  
  
    3.  <span data-ttu-id="8f181-118">**SSO を使用する****はい**です。</span><span class="sxs-lookup"><span data-stu-id="8f181-118">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="8f181-119">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f181-119">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="8f181-120">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f181-120">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f181-121">参照</span><span class="sxs-lookup"><span data-stu-id="8f181-121">See Also</span></span>  
 [<span data-ttu-id="8f181-122">TIBCO Rendezvous 送信ハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="8f181-122">Creating TIBCO Rendezvous Send Handlers</span></span>](../core/creating-tibco-rendezvous-send-handlers.md)