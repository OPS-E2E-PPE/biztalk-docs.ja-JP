---
title: 検証の構成 (X12 インターチェンジの設定) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fdad7016-1d66-4d11-b620-c28368f00133
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0782546e8d016aba2f8ccc4bcd5b7ad5e81412de
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355092"
---
# <a name="configuring-validation-x12-interchange-settings"></a><span data-ttu-id="b09b1-102">検証の構成 (X12 インターチェンジの設定)</span><span class="sxs-lookup"><span data-stu-id="b09b1-102">Configuring Validation (X12-Interchange Settings)</span></span>
<span data-ttu-id="b09b1-103">X12 インターチェンジの検証生成の設定を定義する方法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]受信したインターチェンジの重複した制御番号を確認します。</span><span class="sxs-lookup"><span data-stu-id="b09b1-103">X12 interchange validation generation settings define how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] checks for duplicate control numbers in the received interchange.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b09b1-104">ここで説明した設定は、HIPAA インターチェンジの検証にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="b09b1-104">The settings described here also apply to HIPAA interchange validation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b09b1-105">プロパティは無効になりませんこのページをオフにした場合でも、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェック ボックスを作成するパーティを作成するときに、。契約です。</span><span class="sxs-lookup"><span data-stu-id="b09b1-105">No properties are disabled on this page even if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b09b1-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="b09b1-106">Prerequisites</span></span>  
 <span data-ttu-id="b09b1-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b09b1-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-validation"></a><span data-ttu-id="b09b1-108">検証を構成するには</span><span class="sxs-lookup"><span data-stu-id="b09b1-108">To configure validation</span></span>  
  
1. <span data-ttu-id="b09b1-109">X12 エンコード アグリーメントを」の説明に従って作成[全般設定を構成する (X12)](../core/configuring-general-settings-x12.md)します。</span><span class="sxs-lookup"><span data-stu-id="b09b1-109">Create an X12 encoding agreement as described in [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span> <span data-ttu-id="b09b1-110">既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="b09b1-110">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2. <span data-ttu-id="b09b1-111">一方向アグリーメント タブで、**インターチェンジの設定**セクションで、**検証**です。</span><span class="sxs-lookup"><span data-stu-id="b09b1-111">On a one-way agreement tab, under **Interchange Settings** section, click **Validation**.</span></span>  
  
3. <span data-ttu-id="b09b1-112">選択、**インターチェンジ制御番号**受信パイプラインによる重複インターチェンジのブロックを有効にする チェック ボックス。</span><span class="sxs-lookup"><span data-stu-id="b09b1-112">Select the **Interchange Control Number** check box to enable the receive pipeline to block duplicate interchanges.</span></span> <span data-ttu-id="b09b1-113">選択した場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は受信したインターチェンジのインターチェンジ制御番号 (ISA13) では、インターチェンジ制御番号が一致しないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="b09b1-113">If selected, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will check that the interchange control number (ISA13) for the received interchange does not match the interchange control number.</span></span> <span data-ttu-id="b09b1-114">一致が検出されると、受信パイプラインはインターチェンジを処理できません。</span><span class="sxs-lookup"><span data-stu-id="b09b1-114">If a match is detected, the receive pipeline will not process the interchange.</span></span>  
  
4. <span data-ttu-id="b09b1-115">場合**インターチェンジ制御番号**がオン、**内で重複している isa13 を確認**フィールドに、特定を使用して、重複するインターチェンジに対する確認を実行する日数を入力します。インターチェンジ制御番号。</span><span class="sxs-lookup"><span data-stu-id="b09b1-115">If **Interchange Control Number** is selected, in the **Check for duplicate ISA13 within** field, enter the number of days that a check for a duplicate interchange will be performed using a specific interchange control number.</span></span>  
  
5. <span data-ttu-id="b09b1-116">選択**グループ制御番号**受信パイプラインが重複するグループ制御番号 (GS6) のインターチェンジを処理するを防ぐためにします。</span><span class="sxs-lookup"><span data-stu-id="b09b1-116">Select **Group Control Number** to prevent the receive pipeline from processing interchanges with duplicate group control numbers (GS6).</span></span>  
  
6. <span data-ttu-id="b09b1-117">選択**トランザクション セット制御番号**受信パイプラインが重複するトランザクション セット制御番号 (ST2) のインターチェンジを処理するを防ぐためにします。</span><span class="sxs-lookup"><span data-stu-id="b09b1-117">Select **Transaction Set Control Number** to prevent the receive pipeline from processing interchanges with duplicate transaction set control numbers (ST2).</span></span>  
  
7. <span data-ttu-id="b09b1-118">をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="b09b1-118">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b09b1-119">参照</span><span class="sxs-lookup"><span data-stu-id="b09b1-119">See Also</span></span>  
 [<span data-ttu-id="b09b1-120">インターチェンジの設定の構成 (X12)</span><span class="sxs-lookup"><span data-stu-id="b09b1-120">Configuring Interchange Settings (X12)</span></span>](../core/configuring-interchange-settings-x12.md)