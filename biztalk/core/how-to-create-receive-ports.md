---
redirect_url: /biztalk/core/creating-tibco-rendezvous-receive-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: e04cdd82b0d82befcd629c52bde344f1a5bdc713
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65339017"
---
# <a name="how-to-create-receive-ports"></a><span data-ttu-id="67c35-101">作成する方法の受信ポート</span><span class="sxs-lookup"><span data-stu-id="67c35-101">How to Create Receive Ports</span></span>
<span data-ttu-id="67c35-102">Visual Studio を使用して受信ポートを作成する次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="67c35-102">Follow these steps to create a receive port using Visual Studio.</span></span>  
  
### <a name="to-create-a-receive-port"></a><span data-ttu-id="67c35-103">受信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="67c35-103">To create a receive port</span></span>  
  
1.  <span data-ttu-id="67c35-104">BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、必要な展開アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="67c35-104">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="67c35-105">右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="67c35-105">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Ports**.</span></span>  
  
3.  <span data-ttu-id="67c35-106">**受信ポートのプロパティ**ウィンドウの**全般**ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="67c35-106">In the **Receive Port Properties** window, on the **General** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="67c35-107">**名前**フィールドに「`ReceiveFromTIBCORV`します。</span><span class="sxs-lookup"><span data-stu-id="67c35-107">In the **Name** field, type `ReceiveFromTIBCORV`.</span></span>  
  
    2.  <span data-ttu-id="67c35-108">**認証**グループ ボックスで、認証の使用時にメッセージを処理する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="67c35-108">In the **Authentication** group box, specify how messages are handled when using authentication.</span></span>  
  
    3.  <span data-ttu-id="67c35-109">選択、**失敗したメッセージのルーティングを有効にする**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="67c35-109">Select the **Enable routing for failed messages** checkbox.</span></span>  
  
4.  <span data-ttu-id="67c35-110">**受信場所**ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="67c35-110">On the **Receive Locations** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="67c35-111">**[新規]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67c35-111">Click **New**.</span></span>  
  
    2.  <span data-ttu-id="67c35-112">**受信場所**ウィンドウで、**全般**ページで、入力、**名前**受信場所の。</span><span class="sxs-lookup"><span data-stu-id="67c35-112">In the **Receive Locations** window, on the **General** page, type the **Name** of the receive location.</span></span>  
  
    3.  <span data-ttu-id="67c35-113">**型**ドロップダウン リストで、トランスポートの種類の選択との間、**受信ハンドラー**ドロップダウン一覧でトランスポート アドレスを選択します。</span><span class="sxs-lookup"><span data-stu-id="67c35-113">From the **Type** drop-down list, select the transport type, and from the **Receive handler** drop-down list, select the transport address.</span></span>  
  
    4.  <span data-ttu-id="67c35-114">**受信パイプライン**ドロップダウン リストで、受信パイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="67c35-114">From the **Receive pipeline** drop-down list, select the receive pipeline.</span></span>  
  
    5.  <span data-ttu-id="67c35-115">**スケジュール**] ページで、[、**開始日**と**終了日**ドキュメントの受信を制限します。</span><span class="sxs-lookup"><span data-stu-id="67c35-115">On the **Schedule** page, select the **Start date** and the **End date** to restrict receiving documents.</span></span>  
  
    6.  <span data-ttu-id="67c35-116">選択、**有効にするサービス時間帯**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="67c35-116">Select the **Enable service window** checkbox.</span></span>  
  
    7.  <span data-ttu-id="67c35-117">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67c35-117">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="67c35-118">**受信マップ**ページで、選択したポートでドキュメントを変換するための受信マップを選択します。</span><span class="sxs-lookup"><span data-stu-id="67c35-118">On the **Inbound Maps** page, select the inbound maps for transforming documents on the selected port.</span></span>  
  
6.  <span data-ttu-id="67c35-119">**追跡** ページで、必要なメッセージ本文を追跡および追跡メッセージのプロパティを選択します。</span><span class="sxs-lookup"><span data-stu-id="67c35-119">On the **Tracking** page, select the desired tracking message bodies and tracking message properties.</span></span>  
  
7.  <span data-ttu-id="67c35-120">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67c35-120">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67c35-121">参照</span><span class="sxs-lookup"><span data-stu-id="67c35-121">See Also</span></span>  
 [<span data-ttu-id="67c35-122">TIBCO Rendezvous 受信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="67c35-122">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)