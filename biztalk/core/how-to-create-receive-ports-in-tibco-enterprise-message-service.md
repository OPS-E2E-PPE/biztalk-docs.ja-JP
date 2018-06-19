---
redirect_url: /biztalk/core/creating-tibco-enterprise-message-service-receive-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: e31246cf90f42206de6a22fcc32338fcb2936db3
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24014889"
---
# <a name="how-to-create-receive-ports-in-tibco-enterprise-message-service"></a><span data-ttu-id="65f96-101">TIBCO Enterprise Message Service での受信ポートの作成方法</span><span class="sxs-lookup"><span data-stu-id="65f96-101">How to Create Receive Ports in TIBCO Enterprise Message Service</span></span>
<span data-ttu-id="65f96-102">受信ポートを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="65f96-102">Follow these steps to create a receive port.</span></span>  
  
### <a name="to-create-a-receive-port"></a><span data-ttu-id="65f96-103">受信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="65f96-103">To create a receive port</span></span>  
  
1.  <span data-ttu-id="65f96-104">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、し、必要な展開アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="65f96-104">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="65f96-105">右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="65f96-105">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Ports**.</span></span>  
  
3.  <span data-ttu-id="65f96-106">**受信ポートのプロパティ** ウィンドウで、**全般** ページで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="65f96-106">In the **Receive Port Properties** window, on the **General** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="65f96-107">**名前**フィールドに「`ReceiveFromTIBCOEMS`です。</span><span class="sxs-lookup"><span data-stu-id="65f96-107">In the **Name** field, type `ReceiveFromTIBCOEMS`.</span></span>  
  
    2.  <span data-ttu-id="65f96-108">**認証**グループ ボックスで、認証の使用時のメッセージの処理方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="65f96-108">In the **Authentication** group box, specify how messages are handled when using authentication.</span></span>  
  
    3.  <span data-ttu-id="65f96-109">選択、**失敗したメッセージの有効化のルーティングを**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="65f96-109">Select the **Enable routing for failed messages** checkbox.</span></span>  
  
4.  <span data-ttu-id="65f96-110">**受信場所** ページで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="65f96-110">On the **Receive Locations** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="65f96-111">**[新規作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="65f96-111">Click **New**.</span></span>  
  
    2.  <span data-ttu-id="65f96-112">**受信場所**ウィンドウで、**全般** ページで、入力、**名前**受信場所のです。</span><span class="sxs-lookup"><span data-stu-id="65f96-112">In the **Receive Locations** window, on the **General** page, type the **Name** of the receive location.</span></span>  
  
    3.  <span data-ttu-id="65f96-113">**型**ドロップダウン一覧で、トランスポートの種類を選択してから、**受信ハンドラー**ドロップダウン一覧で、トランスポート アドレスを選択します。</span><span class="sxs-lookup"><span data-stu-id="65f96-113">From the **Type** drop-down list, select the transport type, and from the **Receive handler** drop-down list, select the transport address.</span></span>  
  
    4.  <span data-ttu-id="65f96-114">**受信パイプライン**ドロップダウン リストで、受信パイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="65f96-114">From the **Receive pipeline** drop-down list, select the receive pipeline.</span></span>  
  
    5.  <span data-ttu-id="65f96-115">**スケジュール**] ページで、[、**開始日**と**終了日**ドキュメントの受信を制限します。</span><span class="sxs-lookup"><span data-stu-id="65f96-115">On the **Schedule** page, select the **Start date** and the **End date** to restrict receiving documents.</span></span>  
  
    6.  <span data-ttu-id="65f96-116">選択、**有効にするサービス時間帯**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="65f96-116">Select the **Enable service window** checkbox.</span></span>  
  
    7.  <span data-ttu-id="65f96-117">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="65f96-117">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="65f96-118">**受信マップ**ページで、選択したポートでドキュメントを変換するための受信マップを選択します。</span><span class="sxs-lookup"><span data-stu-id="65f96-118">On the **Inbound Maps** page, select the inbound maps for transforming documents on the selected port.</span></span>  
  
6.  <span data-ttu-id="65f96-119">**追跡** ページで、必要なメッセージ本文の追跡と追跡メッセージのプロパティを選択します。</span><span class="sxs-lookup"><span data-stu-id="65f96-119">On the **Tracking** page, select the desired tracking message bodies and tracking message properties.</span></span>  
  
7.  <span data-ttu-id="65f96-120">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="65f96-120">Click **OK**.</span></span>  
  
