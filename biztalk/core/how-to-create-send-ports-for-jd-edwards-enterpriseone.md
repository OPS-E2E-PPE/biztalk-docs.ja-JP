---
redirect_url: /biztalk/core/adding-biztalk-adapter-for-jd-edwards-enterpriseone/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: c6b672b57f9498c8270a1ee310d498cca6c0b3de
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65339010"
---
# <a name="how-to-create-send-ports-for-jd-edwards-enterpriseone"></a><span data-ttu-id="aabc6-101">JD Edwards EnterpriseOne 用送信ポートを作成する方法</span><span class="sxs-lookup"><span data-stu-id="aabc6-101">How to Create Send Ports for JD Edwards EnterpriseOne</span></span>
<span data-ttu-id="aabc6-102">使用して[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="aabc6-102">Using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], create a send port.</span></span>  
  
### <a name="to-create-a-send-port"></a><span data-ttu-id="aabc6-103">送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="aabc6-103">To create a send port</span></span>  
  
1.  <span data-ttu-id="aabc6-104">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk Server**、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="aabc6-104">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="aabc6-105">BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**の順に展開し、送信ポートを作成するアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="aabc6-105">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, and expand **Applications**, and then expand the application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="aabc6-106">右クリック**送信ポート**クリック**新規**、順にクリックします**静的な送信請求-応答ポート**します。</span><span class="sxs-lookup"><span data-stu-id="aabc6-106">Right-click **Send Ports** and click **New**, and then click **Static Solicit-Response Port**.</span></span>  
  
4.  <span data-ttu-id="aabc6-107">**送信ポートのプロパティ** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="aabc6-107">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    -   <span data-ttu-id="aabc6-108">**名前**ボックスに、送信ポートの名前を入力 (たとえば、 `SendToJDE`)。</span><span class="sxs-lookup"><span data-stu-id="aabc6-108">In the **Name** box, type a send port name (for example, `SendToJDE`).</span></span>  
  
    -   <span data-ttu-id="aabc6-109">**型**ドロップダウン リストで、 **JDEdwards**します。</span><span class="sxs-lookup"><span data-stu-id="aabc6-109">From the **Type** drop-down list, select **JDEdwards**.</span></span>  
  
    -   <span data-ttu-id="aabc6-110">**送信ハンドラー**ドロップダウン リストで、送信ハンドラーのアドレスを選択します。</span><span class="sxs-lookup"><span data-stu-id="aabc6-110">From the **Send handler** drop-down list, select the send handler address.</span></span>  
  
5.  <span data-ttu-id="aabc6-111">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aabc6-111">Click **OK**.</span></span>  
  
