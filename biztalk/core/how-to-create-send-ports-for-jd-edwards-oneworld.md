---
redirect_url: /biztalk/core/adding-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: d65b87fbcbdaf89289406ae6850b70c605123451
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015575"
---
# <a name="how-to-create-send-ports-for-jd-edwards-oneworld"></a><span data-ttu-id="1bb1f-101">JD Edwards OneWorld 用送信ポートの作成方法</span><span class="sxs-lookup"><span data-stu-id="1bb1f-101">How to Create Send Ports for JD Edwards OneWorld</span></span>
<span data-ttu-id="1bb1f-102">次の手順を使用すると、送信ポートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1bb1f-102">Use the following procedure to create a send port.</span></span>  
  
### <a name="to-create-a-send-port"></a><span data-ttu-id="1bb1f-103">送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="1bb1f-103">To create a send port</span></span>  
  
1.  <span data-ttu-id="1bb1f-104">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**に移動し、必要なアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="1bb1f-104">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then navigate to the required application.</span></span>  
  
2.  <span data-ttu-id="1bb1f-105">右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="1bb1f-105">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1bb1f-106">使用することも**静的な一方向ポート**です。</span><span class="sxs-lookup"><span data-stu-id="1bb1f-106">You can also use **Static One-Way Port**.</span></span>  
  
3.  <span data-ttu-id="1bb1f-107">**送信ポートのプロパティ** ダイアログ ボックスで、**名前**フィールドで、送信ポートの名前を入力 (たとえば、入力**SendToJDE**)。</span><span class="sxs-lookup"><span data-stu-id="1bb1f-107">In the **Send Port Properties** dialog box, in the **Name** field, type a send port name (for example, type **SendToJDE**.)</span></span>  
  
4.  <span data-ttu-id="1bb1f-108">**型**ドロップダウン リストで、 **[jdeoneworld]** です。</span><span class="sxs-lookup"><span data-stu-id="1bb1f-108">In the **Type** drop-down list, select **JDEOneWorld**.</span></span>  
  
5.  <span data-ttu-id="1bb1f-109">**URI**ドロップダウン リストで、送信ハンドラーを選択します。</span><span class="sxs-lookup"><span data-stu-id="1bb1f-109">In the **URI** drop-down list, select the send handler.</span></span>  
  
6.  <span data-ttu-id="1bb1f-110">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1bb1f-110">Click **OK**.</span></span>  
  
