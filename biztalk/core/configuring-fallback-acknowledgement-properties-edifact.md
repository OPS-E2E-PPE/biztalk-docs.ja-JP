---
title: フォールバック受信確認プロパティ (EDIFACT) の構成 |Microsoft Docs
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
ms.openlocfilehash: 1422e524d9527b5e7e5362d5867654026cc03768
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974179"
---
# <a name="configuring-fallback-acknowledgement-properties-edifact"></a><span data-ttu-id="1ffbf-102">フォールバック受信確認プロパティを構成する (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="1ffbf-102">Configuring Fallback Acknowledgement Properties (EDIFACT)</span></span>
<span data-ttu-id="1ffbf-103">フォールバック アグリーメントでは、パーティに返す受信確認の種類を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1ffbf-103">In the fallback agreement, you can specify what type of acknowledgment to return to a party.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1ffbf-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="1ffbf-104">Prerequisites</span></span>  
 <span data-ttu-id="1ffbf-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ffbf-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-edifact-ack-contrl-properties"></a><span data-ttu-id="1ffbf-106">EDIFACT 確認 (CONTRL) プロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="1ffbf-106">To configure EDIFACT ACK (CONTRL) properties</span></span>  
  
1. <span data-ttu-id="1ffbf-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノード、およびクリック**EDIFACT フォールバックの設定**します。</span><span class="sxs-lookup"><span data-stu-id="1ffbf-107">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **EDIFACT Fallback Settings**.</span></span>  
  
2. <span data-ttu-id="1ffbf-108">**EDIFACT フォールバックの設定**] ダイアログ ボックスで、 **EDIFACT アグリーメント ページ**] タブの [、**インターチェンジの設定**セクションで、[ **受信確認**します。</span><span class="sxs-lookup"><span data-stu-id="1ffbf-108">In the **EDIFACT Fallback Settings** dialog box, in the **EDIFACT Agreement Pages** tab, under the **Interchange Settings** section, click **Acknowledgements**.</span></span>  
  
3. <span data-ttu-id="1ffbf-109">選択**メッセージの受信 (CONTRL が必要です)** をインターチェンジの送信者に技術確認 (CONTRL) を返します。</span><span class="sxs-lookup"><span data-stu-id="1ffbf-109">Select **Receipt of message (CONTRL) expected** to return a technical (CONTRL) acknowledgment to the interchange sender.</span></span>  
  
4. <span data-ttu-id="1ffbf-110">選択**確認 (CONTRL) が必要です**をインターチェンジの送信者に機能確認 (CONTRL) を返します。</span><span class="sxs-lookup"><span data-stu-id="1ffbf-110">Select **Acknowledgement (CONTRL) expected** to return a functional (CONTRL) acknowledgment to the interchange sender.</span></span>  
  
5. <span data-ttu-id="1ffbf-111">をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="1ffbf-111">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ffbf-112">参照</span><span class="sxs-lookup"><span data-stu-id="1ffbf-112">See Also</span></span>  
 [<span data-ttu-id="1ffbf-113">インターチェンジ処理に対する EDIFACT フォールバック アグリーメント プロパティの構成</span><span class="sxs-lookup"><span data-stu-id="1ffbf-113">Configuring EDIFACT Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)