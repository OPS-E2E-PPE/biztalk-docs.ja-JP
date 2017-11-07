---
redirect_url: /biztalk/core/creating-tibco-enterprise-message-service-send-handlers/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 6b15d9d03ef967bcf7189ef756da8fc63a0eb3f6
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-create-send-ports-for-tibco-enterprise-message-service"></a><span data-ttu-id="d4426-101">TIBCO Enterprise Message Service の送信ポートを作成する方法</span><span class="sxs-lookup"><span data-stu-id="d4426-101">How to Create Send Ports for TIBCO Enterprise Message Service</span></span>
<span data-ttu-id="d4426-102">送信ポートを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d4426-102">Follow these steps to create a send port.</span></span>  
  
## <a name="creating-a-send-port"></a><span data-ttu-id="d4426-103">送信ポートの作成</span><span class="sxs-lookup"><span data-stu-id="d4426-103">Creating a Send Port</span></span>  
  
#### <a name="to-create-a-send-port"></a><span data-ttu-id="d4426-104">送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="d4426-104">To create a send port</span></span>  
  
1.  <span data-ttu-id="d4426-105">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、し、必要な展開アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="d4426-105">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="d4426-106">右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="d4426-106">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="d4426-107">**送信ポートのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="d4426-107">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="d4426-108">たとえば、送信ポートの名前を入力`SendToTIBCOEMS`です。</span><span class="sxs-lookup"><span data-stu-id="d4426-108">Type a name for the send port, for example, `SendToTIBCOEMS`.</span></span>  
  
    2.  <span data-ttu-id="d4426-109">**型**ドロップダウン リストで、 **TIBCO EMS**です。</span><span class="sxs-lookup"><span data-stu-id="d4426-109">From the **Type** drop-down list, select **TIBCO EMS**.</span></span>  
  
    3.  <span data-ttu-id="d4426-110">**送信ハンドラー**ドロップダウン リストで、URI を選択します。</span><span class="sxs-lookup"><span data-stu-id="d4426-110">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="d4426-111">送信パイプラインのドロップダウン リストから選択**[microsoft.biztalk.defaultpipelines.xmltransmit]**です。</span><span class="sxs-lookup"><span data-stu-id="d4426-111">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="d4426-112">**受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]**です。</span><span class="sxs-lookup"><span data-stu-id="d4426-112">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
    6.  <span data-ttu-id="d4426-113">をクリックして**構成**送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="d4426-113">Click **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="d4426-114">**TIBCO EMS トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="d4426-114">In the **TIBCO EMS Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="d4426-115">入力**メッセージ処理**、**サーバー接続の定義**、**トランザクション サポート**、 **Username**、および**パスワード**です。</span><span class="sxs-lookup"><span data-stu-id="d4426-115">Enter **Message Handling**, **Server Connection Definition**, **Transaction Support**, **Username**, and the **password**.</span></span>  
  
         <span data-ttu-id="d4426-116">ログオン情報を設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d4426-116">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="d4426-117">一覧で、TIBCO EMS システムを表すよう作成した関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="d4426-117">In the list, select the affiliate application you created to represent the TIBCO EMS system.</span></span>  
  
    3.  <span data-ttu-id="d4426-118">**SSO を使用する****はい**です。</span><span class="sxs-lookup"><span data-stu-id="d4426-118">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="d4426-119">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4426-119">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="d4426-120">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4426-120">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4426-121">参照</span><span class="sxs-lookup"><span data-stu-id="d4426-121">See Also</span></span>  
  [<span data-ttu-id="d4426-122">TIBCO Enterprise Message Service 送信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="d4426-122">Creating  TIBCO Enterprise Message Service Send Handlers</span></span>](../core/creating-tibco-enterprise-message-service-send-handlers.md)