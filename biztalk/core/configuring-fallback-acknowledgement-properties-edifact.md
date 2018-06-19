---
title: フォールバック受信確認プロパティ (EDIFACT) の構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6062b881-3214-4e68-acbc-1f8c255fd86b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d9369eb7fff1a6217da774aaf62af6e036d0abd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233018"
---
# <a name="configuring-fallback-acknowledgement-properties-edifact"></a><span data-ttu-id="a11ea-102">フォールバック受信確認プロパティを構成する (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="a11ea-102">Configuring Fallback Acknowledgement Properties (EDIFACT)</span></span>
<span data-ttu-id="a11ea-103">フォールバック アグリーメントでは、パーティに返す受信確認の種類を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a11ea-103">In the fallback agreement, you can specify what type of acknowledgment to return to a party.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a11ea-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="a11ea-104">Prerequisites</span></span>  
 <span data-ttu-id="a11ea-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a11ea-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-edifact-ack-contrl-properties"></a><span data-ttu-id="a11ea-106">EDIFACT 確認 (CONTRL) プロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="a11ea-106">To configure EDIFACT ACK (CONTRL) properties</span></span>  
  
1.  <span data-ttu-id="a11ea-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックし、**パーティ**ノードをクリックして**EDIFACT フォールバックの設定**です。</span><span class="sxs-lookup"><span data-stu-id="a11ea-107">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **EDIFACT Fallback Settings**.</span></span>  
  
2.  <span data-ttu-id="a11ea-108">**EDIFACT フォールバックの設定**] ダイアログ ボックスで、 **EDIFACT アグリーメント ページ**] タブの [、**インターチェンジの設定**セクションで、[ **受信確認**です。</span><span class="sxs-lookup"><span data-stu-id="a11ea-108">In the **EDIFACT Fallback Settings** dialog box, in the **EDIFACT Agreement Pages** tab, under the **Interchange Settings** section, click **Acknowledgements**.</span></span>  
  
3.  <span data-ttu-id="a11ea-109">選択**メッセージの受信 (CONTRL が必要です)** をインターチェンジ送信者に技術 (CONTRL) 確認を返します。</span><span class="sxs-lookup"><span data-stu-id="a11ea-109">Select **Receipt of message (CONTRL) expected** to return a technical (CONTRL) acknowledgment to the interchange sender.</span></span>  
  
4.  <span data-ttu-id="a11ea-110">選択**確認 (CONTRL) が必要です**をインターチェンジ送信者に機能 (CONTRL) 確認を返します。</span><span class="sxs-lookup"><span data-stu-id="a11ea-110">Select **Acknowledgement (CONTRL) expected** to return a functional (CONTRL) acknowledgment to the interchange sender.</span></span>  
  
5.  <span data-ttu-id="a11ea-111">をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="a11ea-111">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a11ea-112">参照</span><span class="sxs-lookup"><span data-stu-id="a11ea-112">See Also</span></span>  
 [<span data-ttu-id="a11ea-113">インターチェンジ処理に対する EDIFACT フォールバック アグリーメントのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="a11ea-113">Configuring EDIFACT Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)