---
redirect_url: /biztalk/core/adding-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: fa16887a82e546c45774c9b4d27d6b54eb734c12
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334411"
---
# <a name="how-to-set-jd-edwards-oneworld-pipelines"></a><span data-ttu-id="98531-101">JD Edwards OneWorld パイプラインを設定する方法</span><span class="sxs-lookup"><span data-stu-id="98531-101">How to Set JD Edwards OneWorld Pipelines</span></span>
<span data-ttu-id="98531-102">Microsoft の BizTalk Adapter for JD Edwards OneWorld では、送信、XMLTransmit および XMLReceive を選択して受信パイプラインはそれぞれことが必要です。</span><span class="sxs-lookup"><span data-stu-id="98531-102">Microsoft BizTalk Adapter for JD Edwards OneWorld requires that you select XMLTransmit and XMLReceive for the send and receive pipelines respectively.</span></span>  
  
### <a name="to-set-pipelines"></a><span data-ttu-id="98531-103">パイプラインを設定するには</span><span class="sxs-lookup"><span data-stu-id="98531-103">To set pipelines</span></span>  
  
1.  <span data-ttu-id="98531-104">**開始**メニューで、 **Program Files**、 をポイント**Microsoft BizTalk Server** 、順にクリックします**BizTalk Server 管理**BizTalk Server 管理コンソールを開始します。</span><span class="sxs-lookup"><span data-stu-id="98531-104">On the **Start** menu, point to **Program Files**, point to **Microsoft BizTalk Server** , and then click **BizTalk Server Administration** to start the BizTalk Server Administration Console.</span></span>  
  
2.  <span data-ttu-id="98531-105">BizTalk Server 管理コンソールを展開し、 **BizTalk グループ**、展開**アプリケーション**、し、目的のアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="98531-105">Expand BizTalk Server Administration, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
3.  <span data-ttu-id="98531-106">選択**送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="98531-106">Select **Send Ports**.</span></span> <span data-ttu-id="98531-107">詳細ペインで選択した送信ポートを右クリックし、をクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="98531-107">In the details pane, right-click the selected send port and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="98531-108">**送信ポート プロパティ** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="98531-108">In the **Send Ports Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="98531-109">送信パイプラインを選択、**送信パイプライン**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="98531-109">Select the send pipeline from the **Send Pipeline** drop-down list.</span></span>  
  
    2.  <span data-ttu-id="98531-110">受信パイプラインを選択、**受信パイプライン**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="98531-110">Select the Receive pipeline from the **Receive Pipeline** drop-down list.</span></span>  
  
5.  <span data-ttu-id="98531-111">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98531-111">Click **OK**.</span></span>  
  
