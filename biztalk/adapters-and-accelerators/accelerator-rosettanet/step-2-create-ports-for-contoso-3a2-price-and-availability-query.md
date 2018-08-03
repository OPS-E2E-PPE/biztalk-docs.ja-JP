---
title: '手順 2: Contoso 3 a 2 Price and Availability クエリ応答のシナリオが BizTalk エクスプ ローラーのポートの作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating ports
ms.assetid: e0b12a96-e799-47ac-8293-7de10662bdf0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64101a31b1d1ea9c7af00471c5d764a1d8cfe598
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210146"
---
# <a name="step-2-creating-ports-for-the-contoso-3a2-price-and-availability-queryresponse-scenario"></a><span data-ttu-id="a76e2-102">手順 2: Contoso 3 a 2 Price and Availability クエリ/応答シナリオ用のポートの作成</span><span class="sxs-lookup"><span data-stu-id="a76e2-102">Step 2: Creating Ports for the Contoso 3A2 Price and Availability Query/Response Scenario</span></span>
<span data-ttu-id="a76e2-103">この手順では、BizTalk Server によって提供される SQL アダプターを使用して送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="a76e2-103">In this step, you create send ports using the SQL adapter provided by BizTalk Server.</span></span> <span data-ttu-id="a76e2-104">この SQL ポートを使用して、Contoso の ERP システムとの間で 3A2 Price and Availability 応答を送受信します。</span><span class="sxs-lookup"><span data-stu-id="a76e2-104">You use the SQL port for sending and receiving the 3A2 Price and Availability response to and from the ERP system for Contoso.</span></span>  
  
### <a name="to-configure-a-send-port-using-the-sql-adapter"></a><span data-ttu-id="a76e2-105">SQL アダプターを使用して送信ポートを構成するには</span><span class="sxs-lookup"><span data-stu-id="a76e2-105">To configure a send port using the SQL adapter</span></span>  
  
1.  <span data-ttu-id="a76e2-106">Visual Studio での**ビュー**  メニューのをクリックして**BizTalk エクスプ ローラー**です。</span><span class="sxs-lookup"><span data-stu-id="a76e2-106">In Visual Studio, on the **View** menu, click **BizTalk Explorer**.</span></span>  
  
2.  <span data-ttu-id="a76e2-107">BizTalk エクスプ ローラーで右クリック**送信ポート**、クリックして**送信ポートの追加**です。</span><span class="sxs-lookup"><span data-stu-id="a76e2-107">In BizTalk Explorer, right-click **Send Ports**, and then click **Add Send Port**.</span></span>  
  
3.  <span data-ttu-id="a76e2-108">新しい送信ポートを作成 ダイアログ ボックスで、次のように選択します。**静的な送信請求-応答ポート**クリックしてドロップダウン リストから**OK**です。</span><span class="sxs-lookup"><span data-stu-id="a76e2-108">In the Create New Send Port dialog box, select **Static Solicit-Response Port** from the drop-down list, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="a76e2-109">静的な送信請求-応答送信ポートのプロパティ ダイアログ ボックスで、**名前**ボックスに、入力**3 a2sqlreqresponsesendport**です。</span><span class="sxs-lookup"><span data-stu-id="a76e2-109">In the Static Solicit-Response Send Port Properties dialog box, in the **Name** box, type **3A2SQLReqResponseSendPort**.</span></span>  
  
5.  <span data-ttu-id="a76e2-110">[プロパティ] ウィンドウで、**全般**選択見出し、 **SQL**として、**トランスポートの種類**です。</span><span class="sxs-lookup"><span data-stu-id="a76e2-110">In the Properties window under the **General** heading, select **SQL** as the **Transport Type**.</span></span>  
  
6.  <span data-ttu-id="a76e2-111">**アドレス URI**ボックスで、省略記号ボタンをクリックして (**.**).</span><span class="sxs-lookup"><span data-stu-id="a76e2-111">In the **Address URI** box, click the ellipsis button (**…**).</span></span>  
  
7.  <span data-ttu-id="a76e2-112">SQL トランスポートのプロパティ ダイアログ ボックスで、省略記号ボタンをクリックします (**.**) の横に、**接続文字列**ボックス。</span><span class="sxs-lookup"><span data-stu-id="a76e2-112">In the SQL Transport Properties dialog box, click the ellipsis button (**…**) next to the **Connection String** box.</span></span>  
  
8.  <span data-ttu-id="a76e2-113">[データ リンク プロパティ] ダイアログ ボックスで、**を選択するか、サーバー名を入力**ボックスに、入力**localhost**です。</span><span class="sxs-lookup"><span data-stu-id="a76e2-113">In the Data Link Properties dialog box, in the **Select or enter a server name** box, type **localhost**.</span></span>  
  
9. <span data-ttu-id="a76e2-114">選択**Windows NT 統合セキュリティ**です。</span><span class="sxs-lookup"><span data-stu-id="a76e2-114">Select **Use Windows NT Integrated security**.</span></span>  
  
10. <span data-ttu-id="a76e2-115">**サーバー上のデータベースを選択**ボックスで、選択**Contoso**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="a76e2-115">In the **Select the database on the server** box, select **Contoso**, and then click **OK**.</span></span>  
  
11. <span data-ttu-id="a76e2-116">SQL トランスポートのプロパティ ダイアログ ボックスで、**ドキュメント Target Namespace**ボックスに、入力**http://Contoso.com/Price**です。</span><span class="sxs-lookup"><span data-stu-id="a76e2-116">In the SQL Transport Properties dialog box, in the **Document Target Namespace** box, type **http://Contoso.com/Price**.</span></span>  
  
12. <span data-ttu-id="a76e2-117">**応答ドキュメントのルート要素名**ボックスに、入力 **[rootpriceresponse]**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="a76e2-117">In the **Response Document Root Element Name** box, type **rootPriceResponse**, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="a76e2-118">静的な送信請求-応答送信ポートのプロパティ ダイアログ ボックスの左側のウィンドウでをクリックして**送信**です。</span><span class="sxs-lookup"><span data-stu-id="a76e2-118">In the left pane of the Static Solicit-Response Send Port Properties dialog box, click **Send**.</span></span>  
  
14. <span data-ttu-id="a76e2-119">静的な送信請求-応答送信ポートのプロパティ-構成-送信-全般 ダイアログ ボックスで、**送信パイプライン**ボックスで、 **microsoft.biztalk.defaultpipelines.xmltransmit**です。</span><span class="sxs-lookup"><span data-stu-id="a76e2-119">In the Static Solicit-Response Send Port Properties-Configurations-Send-General dialog box, in the **Send Pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
15. <span data-ttu-id="a76e2-120">**受信パイプライン**ボックスで、 **Microsoft.BizTalk.DefaultPipelines.XMLReceive**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="a76e2-120">In the **Receive Pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.XMLReceive**, and then click **OK**.</span></span>  
  
16. <span data-ttu-id="a76e2-121">BizTalk エクスプ ローラーで右クリック**3 a2sqlreqresponsesendport**、クリックして**Enlist**です。</span><span class="sxs-lookup"><span data-stu-id="a76e2-121">In BizTalk Explorer, right-click **3A2SQLReqResponseSendPort**, and then click **Enlist**.</span></span> <span data-ttu-id="a76e2-122">もう一度右クリックし、をクリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="a76e2-122">Right-click it again, and click **Start**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a76e2-123">参照</span><span class="sxs-lookup"><span data-stu-id="a76e2-123">See Also</span></span>  
 [<span data-ttu-id="a76e2-124">作成と Contoso のプライベート プロセスの変更</span><span class="sxs-lookup"><span data-stu-id="a76e2-124">Creating and Modifying the Private Process for Contoso</span></span>](creating-and-modifying-the-private-process-for-contoso.md)