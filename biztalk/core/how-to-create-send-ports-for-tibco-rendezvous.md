---
redirect_url: /biztalk/core/creating-tibco-rendezvous-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: c3fe43f5ec5f69c84d9f679325a7437d84f2b7d8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338930"
---
# <a name="how-to-create-send-ports-for-tibco-rendezvous"></a><span data-ttu-id="ed836-101">TIBCO Rendezvous の送信ポートを作成する方法</span><span class="sxs-lookup"><span data-stu-id="ed836-101">How to Create Send Ports for TIBCO Rendezvous</span></span>
<span data-ttu-id="ed836-102">次の手順を実行して、作成、送信ポートを使用して[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="ed836-102">Follow these steps to create a send port using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
### <a name="to-create-a-send-port"></a><span data-ttu-id="ed836-103">送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="ed836-103">To create a send port</span></span>  
  
1.  <span data-ttu-id="ed836-104">BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、必要な展開アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="ed836-104">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="ed836-105">右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な送信請求-応答送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="ed836-105">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="ed836-106">**送信ポートのプロパティ** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ed836-106">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="ed836-107">たとえば、送信ポートの名前を入力`SendToTIBCORV`します。</span><span class="sxs-lookup"><span data-stu-id="ed836-107">Type a name for the send port, for example, `SendToTIBCORV`.</span></span>  
  
    2.  <span data-ttu-id="ed836-108">**型**ドロップダウン リストで、 **TIBCO Rendezvous**します。</span><span class="sxs-lookup"><span data-stu-id="ed836-108">From the **Type** drop-down list, select **TIBCO Rendezvous**.</span></span>  
  
    3.  <span data-ttu-id="ed836-109">**送信ハンドラー**ドロップダウン リストで、URI を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed836-109">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="ed836-110">**送信パイプライン**ドロップダウン リストで、 **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**します。</span><span class="sxs-lookup"><span data-stu-id="ed836-110">From the **Send Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span> <span data-ttu-id="ed836-111">**受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]** します。</span><span class="sxs-lookup"><span data-stu-id="ed836-111">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
    6.  <span data-ttu-id="ed836-112">クリックして**構成**送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="ed836-112">Click **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="ed836-113">**TIBCO Rendezvous トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ed836-113">In the **TIBCO Rendezvous Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="ed836-114">プロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="ed836-114">Enter the properties.</span></span>  
  
         <span data-ttu-id="ed836-115">ログオン情報を設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ed836-115">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="ed836-116">一覧で、TIBCO Rendezvous システムを表すように作成した SSO 関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="ed836-116">In the list, select the SSO affiliate application you created to represent the TIBCO Rendezvous system.</span></span>  
  
    3.  <span data-ttu-id="ed836-117">**SSO を使用**、**はい**します。</span><span class="sxs-lookup"><span data-stu-id="ed836-117">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="ed836-118">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed836-118">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="ed836-119">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed836-119">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed836-120">参照</span><span class="sxs-lookup"><span data-stu-id="ed836-120">See Also</span></span>  
 [<span data-ttu-id="ed836-121">TIBCO Rendezvous 送信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="ed836-121">Creating TIBCO Rendezvous Send Handlers</span></span>](../core/creating-tibco-rendezvous-send-handlers.md)