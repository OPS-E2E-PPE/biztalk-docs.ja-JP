---
title: フォールバック受信確認プロパティ (X12) の構成 |Microsoft Docs
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
ms.openlocfilehash: 26ba465598f94f5f9ff41e74d50962a71b0ad979
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391255"
---
# <a name="configuring-fallback-acknowledgement-properties-x12"></a><span data-ttu-id="e6f6d-102">フォールバック受信確認プロパティの構成 (X12)</span><span class="sxs-lookup"><span data-stu-id="e6f6d-102">Configuring Fallback Acknowledgement Properties (X12)</span></span>
<span data-ttu-id="e6f6d-103">フォールバック アグリーメントで指定できますか[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パーティとパーティに返す受信確認の種類から受信した X12 エンコード インターチェンジへの応答の受信確認を生成します。</span><span class="sxs-lookup"><span data-stu-id="e6f6d-103">In the fallback agreement, you can specify how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generates acknowledgments in response to X12-encoded interchanges received from the party and what type of acknowledgment to return to a party.</span></span> <span data-ttu-id="e6f6d-104">このセクションでは、同じ操作を実行する方法の手順を提供します。</span><span class="sxs-lookup"><span data-stu-id="e6f6d-104">This section provides instructions on how to do the same.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6f6d-105">ここで説明する受信確認プロパティは、HIPAA の受信確認にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="e6f6d-105">The acknowledgement properties described here apply also for HIPAA acknowledgements.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e6f6d-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="e6f6d-106">Prerequisites</span></span>  
 <span data-ttu-id="e6f6d-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6f6d-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-x12-ack-properties"></a><span data-ttu-id="e6f6d-108">X12 確認のプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="e6f6d-108">To configure X12 ACK properties</span></span>  
  
1. <span data-ttu-id="e6f6d-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノード、およびクリック**X12 フォールバックの設定**します。</span><span class="sxs-lookup"><span data-stu-id="e6f6d-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **X12 Fallback Settings**.</span></span>  
  
2. <span data-ttu-id="e6f6d-110">**X12 フォールバック設定**] ダイアログ ボックスで、 **X12 アグリーメント ページ**] タブの [、**インターチェンジの設定**セクションで、[ **受信確認**.</span><span class="sxs-lookup"><span data-stu-id="e6f6d-110">In the **X12 Fallback Settings** dialog box, in the **X12 Agreement Pages** tab, under the **Interchange Settings** section, click **Acknowledgements**.</span></span>  
  
3. <span data-ttu-id="e6f6d-111">選択**TA1 が必要**をインターチェンジの送信者に技術 (TA1) 確認を返します。</span><span class="sxs-lookup"><span data-stu-id="e6f6d-111">Select **TA1 Expected** to return a technical (TA1) acknowledgment to the interchange sender.</span></span>  
  
4. <span data-ttu-id="e6f6d-112">選択**997 が必要**機能 (997) 確認をインターチェンジの送信者に戻ります。</span><span class="sxs-lookup"><span data-stu-id="e6f6d-112">Select **997 Expected** to return a functional (997) acknowledgment to the interchange sender.</span></span>  
  
5. <span data-ttu-id="e6f6d-113">をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e6f6d-113">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6f6d-114">参照</span><span class="sxs-lookup"><span data-stu-id="e6f6d-114">See Also</span></span>  
 [<span data-ttu-id="e6f6d-115">インターチェンジ処理用の X12 フォールバック アグリーメント プロパティの構成</span><span class="sxs-lookup"><span data-stu-id="e6f6d-115">Configuring X12 Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)