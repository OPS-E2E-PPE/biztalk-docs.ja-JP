---
title: "TIBCO Enterprise Message Service の送信ポートを作成する方法 |Microsoft ドキュメント"
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
ms.assetid: 6e569244-494e-4db4-8030-eda3b390d073
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bfadeb3306687bfcbea27c0df41973b12b003563
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-send-ports-for-tibco-enterprise-message-service"></a><span data-ttu-id="99001-102">TIBCO Enterprise Message Service の送信ポートを作成する方法</span><span class="sxs-lookup"><span data-stu-id="99001-102">How to Create Send Ports for TIBCO Enterprise Message Service</span></span>
<span data-ttu-id="99001-103">送信ポートを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="99001-103">Follow these steps to create a send port.</span></span>  
  
## <a name="creating-a-send-port"></a><span data-ttu-id="99001-104">送信ポートの作成</span><span class="sxs-lookup"><span data-stu-id="99001-104">Creating a Send Port</span></span>  
  
#### <a name="to-create-a-send-port"></a><span data-ttu-id="99001-105">送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="99001-105">To create a send port</span></span>  
  
1.  <span data-ttu-id="99001-106">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、し、必要な展開アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="99001-106">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="99001-107">右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="99001-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="99001-108">**送信ポートのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="99001-108">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="99001-109">たとえば、送信ポートの名前を入力`SendToTIBCOEMS`です。</span><span class="sxs-lookup"><span data-stu-id="99001-109">Type a name for the send port, for example, `SendToTIBCOEMS`.</span></span>  
  
    2.  <span data-ttu-id="99001-110">**型**ドロップダウン リストで、 **TIBCO EMS**です。</span><span class="sxs-lookup"><span data-stu-id="99001-110">From the **Type** drop-down list, select **TIBCO EMS**.</span></span>  
  
    3.  <span data-ttu-id="99001-111">**送信ハンドラー**ドロップダウン リストで、URI を選択します。</span><span class="sxs-lookup"><span data-stu-id="99001-111">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="99001-112">送信パイプラインのドロップダウン リストから選択**[microsoft.biztalk.defaultpipelines.xmltransmit]**です。</span><span class="sxs-lookup"><span data-stu-id="99001-112">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="99001-113">**受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]**です。</span><span class="sxs-lookup"><span data-stu-id="99001-113">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
    6.  <span data-ttu-id="99001-114">をクリックして**構成**送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="99001-114">Click **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="99001-115">**TIBCO EMS トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="99001-115">In the **TIBCO EMS Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="99001-116">入力**メッセージ処理**、**サーバー接続の定義**、**トランザクション サポート**、 **Username**、および**パスワード**です。</span><span class="sxs-lookup"><span data-stu-id="99001-116">Enter **Message Handling**, **Server Connection Definition**, **Transaction Support**, **Username**, and the **password**.</span></span>  
  
         <span data-ttu-id="99001-117">ログオン情報を設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="99001-117">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="99001-118">一覧で、TIBCO EMS システムを表すよう作成した関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="99001-118">In the list, select the affiliate application you created to represent the TIBCO EMS system.</span></span>  
  
    3.  <span data-ttu-id="99001-119">**SSO を使用する****はい**です。</span><span class="sxs-lookup"><span data-stu-id="99001-119">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="99001-120">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99001-120">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="99001-121">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99001-121">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99001-122">参照</span><span class="sxs-lookup"><span data-stu-id="99001-122">See Also</span></span>  
 <span data-ttu-id="99001-123">[送信ポートの TIBCO Enterprise Message Service トランスポート プロパティの設定](../core/setting-tibco-enterprise-message-service-transport-properties-for-the-send-port.md) </span><span class="sxs-lookup"><span data-stu-id="99001-123">[Setting TIBCO Enterprise Message Service Transport Properties for the Send Port](../core/setting-tibco-enterprise-message-service-transport-properties-for-the-send-port.md) </span></span>  
 [<span data-ttu-id="99001-124">TIBCO Enterprise Message Service 送信ハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="99001-124">Creating  TIBCO Enterprise Message Service Send Handlers</span></span>](../core/creating-tibco-enterprise-message-service-send-handlers.md)