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
ms.openlocfilehash: 4276ad1b5ae995cfb6370377d7d1671ede09bd52
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975451"
---
# <a name="configuring-fallback-validation-properties-edifact"></a><span data-ttu-id="25761-102">フォールバック検証プロパティの構成 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="25761-102">Configuring Fallback Validation Properties (EDIFACT)</span></span>
<span data-ttu-id="25761-103">このセクションでは、重複する制御番号が処理されないようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="25761-103">This section provides instructions on how to prevent duplicate control numbers from being processed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="25761-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="25761-104">Prerequisites</span></span>  
 <span data-ttu-id="25761-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="25761-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-duplicate-validation"></a><span data-ttu-id="25761-106">重複する検証を構成するには</span><span class="sxs-lookup"><span data-stu-id="25761-106">To configure duplicate validation</span></span>  
  
1. <span data-ttu-id="25761-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノード、およびクリック**EDIFACT フォールバックの設定**します。</span><span class="sxs-lookup"><span data-stu-id="25761-107">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **EDIFACT Fallback Settings**.</span></span>  
  
2. <span data-ttu-id="25761-108">**EDIFACT フォールバックの設定**] ダイアログ ボックスで、 **EDIFACT アグリーメント ページ**] タブの [、**インターチェンジの設定**セクションで、[**検証**.</span><span class="sxs-lookup"><span data-stu-id="25761-108">In the **EDIFACT Fallback Settings** dialog box, in the **EDIFACT Agreement Pages** tab, under the **Interchange Settings** section, click **Validation**.</span></span>  
  
3. <span data-ttu-id="25761-109">選択、**インターチェンジ制御番号 (UNB5)** 受信パイプラインによる重複インターチェンジのブロックを有効にする チェック ボックス。</span><span class="sxs-lookup"><span data-stu-id="25761-109">Select the **Interchange control number (UNB5)** check box to enable the receive pipeline to block duplicate interchanges.</span></span> <span data-ttu-id="25761-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、このオプションをオンにした場合、受信したインターチェンジのインターチェンジ制御番号が、受信した他のインターチェンジのインターチェンジ制御番号と重複していないかどうかがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="25761-110">If selected, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will check that the interchange control number for the received interchange does not match the interchange control number of another received interchange.</span></span> <span data-ttu-id="25761-111">一致した制御番号が検出された場合、受信パイプラインはインターチェンジを処理しません。</span><span class="sxs-lookup"><span data-stu-id="25761-111">If a match is detected, the receive pipeline will not process the interchange.</span></span>  
  
4. <span data-ttu-id="25761-112">場合**インターチェンジ制御番号 (UNB5)** がオン、**内で重複する UNB5 をチェック**フィールドに、重複するインターチェンジを確認する日数を入力します。</span><span class="sxs-lookup"><span data-stu-id="25761-112">If **Interchange control number (UNB5)** is selected, in the **Check for duplicate UNB5 within** field, enter the number of days to check for a duplicate interchange.</span></span>  
  
5. <span data-ttu-id="25761-113">選択**インターチェンジのグループ制御番号 (UNG5)** 受信パイプラインが重複するグループを処理するを防ぐためにします。</span><span class="sxs-lookup"><span data-stu-id="25761-113">Select **Group control number (UNG5) in interchange** to prevent the receive pipeline from processing duplicate groups.</span></span>  
  
6. <span data-ttu-id="25761-114">選択**トランザクション セット制御番号 (UNH1) グループで**受信パイプラインが重複しているトランザクションを処理するを防ぐために設定します。</span><span class="sxs-lookup"><span data-stu-id="25761-114">Select **Transaction Set Control Number (UNH1) in group** to prevent the receive pipeline from processing duplicate transaction sets.</span></span>  
  
7. <span data-ttu-id="25761-115">をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="25761-115">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25761-116">参照</span><span class="sxs-lookup"><span data-stu-id="25761-116">See Also</span></span>  
 [<span data-ttu-id="25761-117">インターチェンジ処理に対する EDIFACT フォールバック アグリーメント プロパティの構成</span><span class="sxs-lookup"><span data-stu-id="25761-117">Configuring EDIFACT Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)