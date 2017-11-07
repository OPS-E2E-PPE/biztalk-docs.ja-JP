---
redirect_url: /biztalk/core/creating-tibco-rendezvous-receive-handlers/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 0cd93bcd2d1855f137600214b6a07d52b6f52e4f
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-create-receive-ports"></a><span data-ttu-id="05c7a-101">作成する方法の受信ポート</span><span class="sxs-lookup"><span data-stu-id="05c7a-101">How to Create Receive Ports</span></span>
<span data-ttu-id="05c7a-102">Visual Studio を使用して受信ポートを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="05c7a-102">Follow these steps to create a receive port using Visual Studio.</span></span>  
  
### <a name="to-create-a-receive-port"></a><span data-ttu-id="05c7a-103">受信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="05c7a-103">To create a receive port</span></span>  
  
1.  <span data-ttu-id="05c7a-104">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、し、必要な展開アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="05c7a-104">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="05c7a-105">右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="05c7a-105">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Ports**.</span></span>  
  
3.  <span data-ttu-id="05c7a-106">**受信ポートのプロパティ** ウィンドウで、**全般** ページで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="05c7a-106">In the **Receive Port Properties** window, on the **General** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="05c7a-107">**名前**フィールドに「`ReceiveFromTIBCORV`です。</span><span class="sxs-lookup"><span data-stu-id="05c7a-107">In the **Name** field, type `ReceiveFromTIBCORV`.</span></span>  
  
    2.  <span data-ttu-id="05c7a-108">**認証**グループ ボックスで、認証の使用時のメッセージの処理方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="05c7a-108">In the **Authentication** group box, specify how messages are handled when using authentication.</span></span>  
  
    3.  <span data-ttu-id="05c7a-109">選択、**失敗したメッセージの有効化のルーティングを**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="05c7a-109">Select the **Enable routing for failed messages** checkbox.</span></span>  
  
4.  <span data-ttu-id="05c7a-110">**受信場所** ページで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="05c7a-110">On the **Receive Locations** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="05c7a-111">**[新規作成]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="05c7a-111">Click **New**.</span></span>  
  
    2.  <span data-ttu-id="05c7a-112">**受信場所**ウィンドウで、**全般** ページで、入力、**名前**受信場所のです。</span><span class="sxs-lookup"><span data-stu-id="05c7a-112">In the **Receive Locations** window, on the **General** page, type the **Name** of the receive location.</span></span>  
  
    3.  <span data-ttu-id="05c7a-113">**型**ドロップダウン一覧で、トランスポートの種類を選択してから、**受信ハンドラー**ドロップダウン一覧で、トランスポート アドレスを選択します。</span><span class="sxs-lookup"><span data-stu-id="05c7a-113">From the **Type** drop-down list, select the transport type, and from the **Receive handler** drop-down list, select the transport address.</span></span>  
  
    4.  <span data-ttu-id="05c7a-114">**受信パイプライン**ドロップダウン リストで、受信パイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="05c7a-114">From the **Receive pipeline** drop-down list, select the receive pipeline.</span></span>  
  
    5.  <span data-ttu-id="05c7a-115">**スケジュール**] ページで、[、**開始日**と**終了日**ドキュメントの受信を制限します。</span><span class="sxs-lookup"><span data-stu-id="05c7a-115">On the **Schedule** page, select the **Start date** and the **End date** to restrict receiving documents.</span></span>  
  
    6.  <span data-ttu-id="05c7a-116">選択、**有効にするサービス時間帯**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="05c7a-116">Select the **Enable service window** checkbox.</span></span>  
  
    7.  <span data-ttu-id="05c7a-117">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="05c7a-117">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="05c7a-118">**受信マップ**ページで、選択したポートでドキュメントを変換するための受信マップを選択します。</span><span class="sxs-lookup"><span data-stu-id="05c7a-118">On the **Inbound Maps** page, select the inbound maps for transforming documents on the selected port.</span></span>  
  
6.  <span data-ttu-id="05c7a-119">**追跡** ページで、必要なメッセージ本文の追跡と追跡メッセージのプロパティを選択します。</span><span class="sxs-lookup"><span data-stu-id="05c7a-119">On the **Tracking** page, select the desired tracking message bodies and tracking message properties.</span></span>  
  
7.  <span data-ttu-id="05c7a-120">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="05c7a-120">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05c7a-121">参照</span><span class="sxs-lookup"><span data-stu-id="05c7a-121">See Also</span></span>  
 [<span data-ttu-id="05c7a-122">TIBCO Rendezvous 受信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="05c7a-122">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)