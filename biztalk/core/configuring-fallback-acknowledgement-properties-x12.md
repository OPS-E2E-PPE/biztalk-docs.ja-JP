---
title: フォールバック受信確認プロパティ (X12) の構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce33f5dd-fbd5-448c-8ea3-05dd1467131a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 216961dea0bdf4a67c550fba8a599eff2d0c89ce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232834"
---
# <a name="configuring-fallback-acknowledgement-properties-x12"></a><span data-ttu-id="152ea-102">フォールバック受信確認プロパティの構成 (X12)</span><span class="sxs-lookup"><span data-stu-id="152ea-102">Configuring Fallback Acknowledgement Properties (X12)</span></span>
<span data-ttu-id="152ea-103">フォールバック アグリーメントでは、パーティから受信した X12 エンコード インターチェンジへの応答としての受信確認を [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で生成する方法、およびパーティに返す受信確認の種類を指定できます。</span><span class="sxs-lookup"><span data-stu-id="152ea-103">In the fallback agreement, you can specify how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generates acknowledgments in response to X12-encoded interchanges received from the party and what type of acknowledgment to return to a party.</span></span> <span data-ttu-id="152ea-104">ここでは、この指定を行う手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="152ea-104">This section provides instructions on how to do the same.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="152ea-105">ここで説明する受信確認プロパティは、HIPAA の受信確認にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="152ea-105">The acknowledgement properties described here apply also for HIPAA acknowledgements.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="152ea-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="152ea-106">Prerequisites</span></span>  
 <span data-ttu-id="152ea-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="152ea-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-x12-ack-properties"></a><span data-ttu-id="152ea-108">X12 確認のプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="152ea-108">To configure X12 ACK properties</span></span>  
  
1.  <span data-ttu-id="152ea-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノードをクリックして**X12 フォールバック設定**です。</span><span class="sxs-lookup"><span data-stu-id="152ea-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **X12 Fallback Settings**.</span></span>  
  
2.  <span data-ttu-id="152ea-110">**X12 フォールバック設定**] ダイアログ ボックスで、 **X12 アグリーメント ページ**] タブの [、**インターチェンジの設定**セクションで、[ **受信確認**.</span><span class="sxs-lookup"><span data-stu-id="152ea-110">In the **X12 Fallback Settings** dialog box, in the **X12 Agreement Pages** tab, under the **Interchange Settings** section, click **Acknowledgements**.</span></span>  
  
3.  <span data-ttu-id="152ea-111">選択**TA1 が必要**をインターチェンジ送信者に技術 (TA1) 確認を返します。</span><span class="sxs-lookup"><span data-stu-id="152ea-111">Select **TA1 Expected** to return a technical (TA1) acknowledgment to the interchange sender.</span></span>  
  
4.  <span data-ttu-id="152ea-112">選択**997 が必要**をインターチェンジ送信者に機能 (997) 確認を返します。</span><span class="sxs-lookup"><span data-stu-id="152ea-112">Select **997 Expected** to return a functional (997) acknowledgment to the interchange sender.</span></span>  
  
5.  <span data-ttu-id="152ea-113">をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="152ea-113">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="152ea-114">参照</span><span class="sxs-lookup"><span data-stu-id="152ea-114">See Also</span></span>  
 [<span data-ttu-id="152ea-115">設定の X12 インターチェンジ処理のためのフォールバック アグリーメント プロパティ</span><span class="sxs-lookup"><span data-stu-id="152ea-115">Configuring X12 Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)