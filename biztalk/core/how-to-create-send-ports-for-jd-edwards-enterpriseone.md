---
redirect_url: /biztalk/core/adding-biztalk-adapter-for-jd-edwards-enterpriseone/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: fe877aa8c7b76a638df93a073eed0cf26f71a609
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013281"
---
# <a name="how-to-create-send-ports-for-jd-edwards-enterpriseone"></a><span data-ttu-id="dc775-101">JD Edwards EnterpriseOne 用送信ポートの作成方法</span><span class="sxs-lookup"><span data-stu-id="dc775-101">How to Create Send Ports for JD Edwards EnterpriseOne</span></span>
<span data-ttu-id="dc775-102">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用して送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="dc775-102">Using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], create a send port.</span></span>  
  
### <a name="to-create-a-send-port"></a><span data-ttu-id="dc775-103">送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="dc775-103">To create a send port</span></span>  
  
1.  <span data-ttu-id="dc775-104">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk Server**、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="dc775-104">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="dc775-105">BizTalk Server 管理コンソールで、次のように展開します**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、を展開**アプリケーション**、の順に展開し、。送信ポートを作成するアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="dc775-105">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, and expand **Applications**, and then expand the application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="dc775-106">右クリック**送信ポート** をクリック**新規**、クリックして**静的な送信請求-応答ポート**です。</span><span class="sxs-lookup"><span data-stu-id="dc775-106">Right-click **Send Ports** and click **New**, and then click **Static Solicit-Response Port**.</span></span>  
  
4.  <span data-ttu-id="dc775-107">**送信ポートのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="dc775-107">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    -   <span data-ttu-id="dc775-108">**名前**ボックスに、送信ポートの名前を入力 (たとえば、 `SendToJDE`)。</span><span class="sxs-lookup"><span data-stu-id="dc775-108">In the **Name** box, type a send port name (for example, `SendToJDE`).</span></span>  
  
    -   <span data-ttu-id="dc775-109">**型**ドロップダウン リストで、 **JDEdwards**です。</span><span class="sxs-lookup"><span data-stu-id="dc775-109">From the **Type** drop-down list, select **JDEdwards**.</span></span>  
  
    -   <span data-ttu-id="dc775-110">**送信ハンドラー**ドロップダウン リストで、送信ハンドラーのアドレスを選択します。</span><span class="sxs-lookup"><span data-stu-id="dc775-110">From the **Send handler** drop-down list, select the send handler address.</span></span>  
  
5.  <span data-ttu-id="dc775-111">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc775-111">Click **OK**.</span></span>  
  
