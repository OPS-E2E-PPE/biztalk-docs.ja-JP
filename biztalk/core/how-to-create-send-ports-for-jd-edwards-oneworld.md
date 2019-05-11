---
redirect_url: /biztalk/core/adding-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: e2101cee6e82283984bd0e830a583a96613d21b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385430"
---
# <a name="how-to-create-send-ports-for-jd-edwards-oneworld"></a><span data-ttu-id="00521-101">JD Edwards OneWorld 用送信ポートの作成方法</span><span class="sxs-lookup"><span data-stu-id="00521-101">How to Create Send Ports for JD Edwards OneWorld</span></span>
<span data-ttu-id="00521-102">送信ポートを作成するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="00521-102">Use the following procedure to create a send port.</span></span>  
  
### <a name="to-create-a-send-port"></a><span data-ttu-id="00521-103">送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="00521-103">To create a send port</span></span>  
  
1.  <span data-ttu-id="00521-104">BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、順に移動します、必要なアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="00521-104">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then navigate to the required application.</span></span>  
  
2.  <span data-ttu-id="00521-105">右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な送信請求-応答送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="00521-105">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="00521-106">使用することも**静的な一方向ポート**します。</span><span class="sxs-lookup"><span data-stu-id="00521-106">You can also use **Static One-Way Port**.</span></span>  
  
3.  <span data-ttu-id="00521-107">**送信ポートのプロパティ** ダイアログ ボックスで、**名前**フィールドに、送信ポートの名前を入力 (たとえば、「 **SendToJDE**。)</span><span class="sxs-lookup"><span data-stu-id="00521-107">In the **Send Port Properties** dialog box, in the **Name** field, type a send port name (for example, type **SendToJDE**.)</span></span>  
  
4.  <span data-ttu-id="00521-108">**型**ドロップダウン リストで、 **[jdeoneworld]** します。</span><span class="sxs-lookup"><span data-stu-id="00521-108">In the **Type** drop-down list, select **JDEOneWorld**.</span></span>  
  
5.  <span data-ttu-id="00521-109">**URI**ドロップダウン リストで、送信ハンドラーを選択します。</span><span class="sxs-lookup"><span data-stu-id="00521-109">In the **URI** drop-down list, select the send handler.</span></span>  
  
6.  <span data-ttu-id="00521-110">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="00521-110">Click **OK**.</span></span>  
  
