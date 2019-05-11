---
title: フォールバック検証プロパティ (EDIFACT) の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b925d063-e24b-4cfb-acbd-dcadb511011d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad87f6419745515496a1c140df6159bdd903d3b5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355531"
---
# <a name="configuring-fallback-validation-properties-edifact"></a><span data-ttu-id="308b2-102">フォールバック検証プロパティ (EDIFACT) の構成</span><span class="sxs-lookup"><span data-stu-id="308b2-102">Configuring Fallback Validation Properties (EDIFACT)</span></span>
<span data-ttu-id="308b2-103">このセクションでは、重複した制御番号が処理されていることを防止する方法の手順を提供します。</span><span class="sxs-lookup"><span data-stu-id="308b2-103">This section provides instructions on how to prevent duplicate control numbers from being processed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="308b2-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="308b2-104">Prerequisites</span></span>  
 <span data-ttu-id="308b2-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="308b2-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-duplicate-validation"></a><span data-ttu-id="308b2-106">重複する検証を構成するには</span><span class="sxs-lookup"><span data-stu-id="308b2-106">To configure duplicate validation</span></span>  
  
1. <span data-ttu-id="308b2-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノード、およびクリック**EDIFACT フォールバックの設定**します。</span><span class="sxs-lookup"><span data-stu-id="308b2-107">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **EDIFACT Fallback Settings**.</span></span>  
  
2. <span data-ttu-id="308b2-108">**EDIFACT フォールバックの設定**] ダイアログ ボックスで、 **EDIFACT アグリーメント ページ**] タブの [、**インターチェンジの設定**セクションで、[**検証**.</span><span class="sxs-lookup"><span data-stu-id="308b2-108">In the **EDIFACT Fallback Settings** dialog box, in the **EDIFACT Agreement Pages** tab, under the **Interchange Settings** section, click **Validation**.</span></span>  
  
3. <span data-ttu-id="308b2-109">選択、**インターチェンジ制御番号 (UNB5)** 受信パイプラインによる重複インターチェンジのブロックを有効にする チェック ボックス。</span><span class="sxs-lookup"><span data-stu-id="308b2-109">Select the **Interchange control number (UNB5)** check box to enable the receive pipeline to block duplicate interchanges.</span></span> <span data-ttu-id="308b2-110">選択した場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は受信したインターチェンジのインターチェンジ制御番号が別の受信したインターチェンジのインターチェンジ制御番号が一致しないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="308b2-110">If selected, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will check that the interchange control number for the received interchange does not match the interchange control number of another received interchange.</span></span> <span data-ttu-id="308b2-111">一致が検出されると、受信パイプラインはインターチェンジを処理できません。</span><span class="sxs-lookup"><span data-stu-id="308b2-111">If a match is detected, the receive pipeline will not process the interchange.</span></span>  
  
4. <span data-ttu-id="308b2-112">場合**インターチェンジ制御番号 (UNB5)** がオン、**内で重複する UNB5 をチェック**フィールドに、重複するインターチェンジを確認する日数を入力します。</span><span class="sxs-lookup"><span data-stu-id="308b2-112">If **Interchange control number (UNB5)** is selected, in the **Check for duplicate UNB5 within** field, enter the number of days to check for a duplicate interchange.</span></span>  
  
5. <span data-ttu-id="308b2-113">選択**インターチェンジのグループ制御番号 (UNG5)** 受信パイプラインが重複するグループを処理するを防ぐためにします。</span><span class="sxs-lookup"><span data-stu-id="308b2-113">Select **Group control number (UNG5) in interchange** to prevent the receive pipeline from processing duplicate groups.</span></span>  
  
6. <span data-ttu-id="308b2-114">選択**トランザクション セット制御番号 (UNH1) グループで**受信パイプラインが重複しているトランザクションを処理するを防ぐために設定します。</span><span class="sxs-lookup"><span data-stu-id="308b2-114">Select **Transaction Set Control Number (UNH1) in group** to prevent the receive pipeline from processing duplicate transaction sets.</span></span>  
  
7. <span data-ttu-id="308b2-115">をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="308b2-115">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="308b2-116">参照</span><span class="sxs-lookup"><span data-stu-id="308b2-116">See Also</span></span>  
 [<span data-ttu-id="308b2-117">インターチェンジ処理に対する EDIFACT フォールバック アグリーメント プロパティの構成</span><span class="sxs-lookup"><span data-stu-id="308b2-117">Configuring EDIFACT Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)