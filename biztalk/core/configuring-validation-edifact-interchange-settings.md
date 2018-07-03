---
title: 検証の構成 (EDIFACT インターチェンジの設定) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55820ebc-fe21-48a3-8985-1bf4184176ac
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a700282aee9651b8f259c931a460a774f900a4a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999731"
---
# <a name="configuring-validation-edifact-interchange-settings"></a><span data-ttu-id="b7fd7-102">検証を構成する (EDIFACT インターチェンジの設定)</span><span class="sxs-lookup"><span data-stu-id="b7fd7-102">Configuring Validation (EDIFACT-Interchange Settings)</span></span>
<span data-ttu-id="b7fd7-103">このセクションでは、重複する制御番号が処理されないようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b7fd7-103">This section provides instructions on how to prevent duplicate control numbers from being processed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b7fd7-104">プロパティは無効になりませんこのページをオフにした場合でも、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェック ボックスを作成するパーティを作成するときに、。契約です。</span><span class="sxs-lookup"><span data-stu-id="b7fd7-104">No properties are disabled on this page even if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b7fd7-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="b7fd7-105">Prerequisites</span></span>  
 <span data-ttu-id="b7fd7-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7fd7-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-duplicate-validation"></a><span data-ttu-id="b7fd7-107">重複する検証を構成するには</span><span class="sxs-lookup"><span data-stu-id="b7fd7-107">To configure duplicate validation</span></span>  
  
1. <span data-ttu-id="b7fd7-108">EDIFACT エンコード アグリーメントを」の説明に従って作成[を構成する一般的な設定 (EDIFACT)](../core/configuring-general-settings-edifact.md)します。</span><span class="sxs-lookup"><span data-stu-id="b7fd7-108">Create an EDIFACT encoding agreement as described in [Configuring General Settings (EDIFACT)](../core/configuring-general-settings-edifact.md).</span></span> <span data-ttu-id="b7fd7-109">既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="b7fd7-109">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2. <span data-ttu-id="b7fd7-110">一方向アグリーメント タブで、**インターチェンジの設定**セクションで、**検証**です。</span><span class="sxs-lookup"><span data-stu-id="b7fd7-110">On a one-way agreement tab, under **Interchange Settings** section, click **Validation**.</span></span>  
  
3. <span data-ttu-id="b7fd7-111">選択、**インターチェンジ制御番号 (UNB5)** 受信パイプラインによる重複インターチェンジのブロックを有効にする チェック ボックス。</span><span class="sxs-lookup"><span data-stu-id="b7fd7-111">Select the **Interchange control number (UNB5)** check box to enable the receive pipeline to block duplicate interchanges.</span></span> <span data-ttu-id="b7fd7-112">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、このオプションをオンにした場合、受信したインターチェンジのインターチェンジ制御番号が、受信した他のインターチェンジのインターチェンジ制御番号と重複していないかどうかがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="b7fd7-112">If selected, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will check that the interchange control number for the received interchange does not match the interchange control number of another received interchange.</span></span> <span data-ttu-id="b7fd7-113">一致した制御番号が検出された場合、受信パイプラインはインターチェンジを処理しません。</span><span class="sxs-lookup"><span data-stu-id="b7fd7-113">If a match is detected, the receive pipeline will not process the interchange.</span></span>  
  
4. <span data-ttu-id="b7fd7-114">場合**インターチェンジ制御番号 (UNB5)** がオン、**内で重複する UNB5 をチェック**フィールドに、重複するインターチェンジを確認する日数を入力します。</span><span class="sxs-lookup"><span data-stu-id="b7fd7-114">If **Interchange control number (UNB5)** is selected, in the **Check for duplicate UNB5 within** field, enter the number of days to check for a duplicate interchange.</span></span>  
  
5. <span data-ttu-id="b7fd7-115">選択**インターチェンジのグループ制御番号 (UNG5)** 受信パイプラインが重複するグループを処理するを防ぐためにします。</span><span class="sxs-lookup"><span data-stu-id="b7fd7-115">Select **Group control number (UNG5) in interchange** to prevent the receive pipeline from processing duplicate groups.</span></span>  
  
6. <span data-ttu-id="b7fd7-116">選択**トランザクション セット制御番号 (UNH1) グループで**受信パイプラインが重複しているトランザクションを処理するを防ぐために設定します。</span><span class="sxs-lookup"><span data-stu-id="b7fd7-116">Select **Transaction Set Control Number (UNH1) in group** to prevent the receive pipeline from processing duplicate transaction sets.</span></span>  
  
7. <span data-ttu-id="b7fd7-117">をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="b7fd7-117">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7fd7-118">参照</span><span class="sxs-lookup"><span data-stu-id="b7fd7-118">See Also</span></span>  
 [<span data-ttu-id="b7fd7-119">インターチェンジの設定の構成 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="b7fd7-119">Configuring Interchange Settings (EDIFACT)</span></span>](../core/configuring-interchange-settings-edifact.md)