---
redirect_url: /biztalk/core/creating-peoplesoft-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: ec518c16383d847bf13706a6469b038b447c1543
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013657"
---
# <a name="how-to-create-send-ports-for-peoplesoft-enterprise"></a><span data-ttu-id="bd45e-101">PeopleSoft Enterprise の送信ポートを作成する方法</span><span class="sxs-lookup"><span data-stu-id="bd45e-101">How to Create Send Ports for PeopleSoft Enterprise</span></span>
<span data-ttu-id="bd45e-102">BizTalk Server 管理コンソールを使用して送信ポートを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bd45e-102">Follow these steps to create a send port using BizTalk Server Administration Console.</span></span>  
  
## <a name="creating-a-send-port"></a><span data-ttu-id="bd45e-103">送信ポートの作成</span><span class="sxs-lookup"><span data-stu-id="bd45e-103">Creating a Send Port</span></span>  
  
#### <a name="to-create-a-send-port"></a><span data-ttu-id="bd45e-104">送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="bd45e-104">To create a send port</span></span>  
  
1.  <span data-ttu-id="bd45e-105">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、し、必要な展開アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="bd45e-105">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="bd45e-106">右クリック**送信ポート**、] をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="bd45e-106">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="bd45e-107">**送信ポートのプロパティ**] ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="bd45e-107">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="bd45e-108">たとえば、送信ポートの名前を入力`SSOSendToPeopleSoft`です。</span><span class="sxs-lookup"><span data-stu-id="bd45e-108">Type a name for the send port, for example, `SSOSendToPeopleSoft`.</span></span>  
  
    2.  <span data-ttu-id="bd45e-109">**型**ドロップダウン リストで、 **PeopleSoft**です。</span><span class="sxs-lookup"><span data-stu-id="bd45e-109">From the **Type** drop-down list, select **PeopleSoft**.</span></span>  
  
    3.  <span data-ttu-id="bd45e-110">**送信ハンドラー**ドロップダウン リストで、URI を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd45e-110">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="bd45e-111">送信パイプラインのドロップダウン リストから選択 **[microsoft.biztalk.defaultpipelines.xmltransmit]** です。</span><span class="sxs-lookup"><span data-stu-id="bd45e-111">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="bd45e-112">**受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]** です。</span><span class="sxs-lookup"><span data-stu-id="bd45e-112">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
    6.  <span data-ttu-id="bd45e-113">をクリックして**構成**送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="bd45e-113">Click **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="bd45e-114">**PeopleSoft トランスポートのプロパティ**] ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="bd45e-114">In the **PeopleSoft Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="bd45e-115">展開**アダプターに必要なプロパティ**、入力と**アプリケーション サーバーのパス**、 **JAVA_HOME**、**ユーザー名**、 **パスワード**、および Peoplesoft システムに接続するための Jar ファイルです。</span><span class="sxs-lookup"><span data-stu-id="bd45e-115">Expand **Adapter Required Properties**, and enter **Application Server Path**, **JAVA_HOME**, **user name**, **password**, and the Jar file for connecting into the Peoplesoft system.</span></span>  
  
         <span data-ttu-id="bd45e-116">ログオン情報を設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="bd45e-116">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="bd45e-117">一覧で、PeopleSoft システムを表すよう作成した SSO 関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="bd45e-117">In the list, select the SSO affiliate application you created to represent the PeopleSoft system.</span></span>  
  
    3.  <span data-ttu-id="bd45e-118">**SSO を使用する**[**はい**です。</span><span class="sxs-lookup"><span data-stu-id="bd45e-118">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="bd45e-119">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd45e-119">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="bd45e-120">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd45e-120">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd45e-121">参照</span><span class="sxs-lookup"><span data-stu-id="bd45e-121">See Also</span></span>  
 [<span data-ttu-id="bd45e-122">PeopleSoft 送信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="bd45e-122">Creating PeopleSoft Send Handlers</span></span>](../core/creating-peoplesoft-send-handlers.md)