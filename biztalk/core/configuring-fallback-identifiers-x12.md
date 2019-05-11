---
title: フォールバック識別子 (X12) の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2cb5b32c-96ec-4192-9a10-6668a2cb1195
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d5612b0b6ffafd52709710148ee62d06245fb191
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391230"
---
# <a name="configuring-fallback-identifiers-x12"></a><span data-ttu-id="44818-102">フォールバック識別子の構成 (X12)</span><span class="sxs-lookup"><span data-stu-id="44818-102">Configuring Fallback Identifiers (X12)</span></span>
<span data-ttu-id="44818-103">フォールバック アグリーメントでは、X12 を設定する必要がありますが、インターチェンジを受信しないことを確認するために承認およびセキュリティのプロパティの未承認の受信者。</span><span class="sxs-lookup"><span data-stu-id="44818-103">In the fallback agreement, you must set the X12 authorization and security properties in order to verify that the interchange is not being received by unauthorized recipients.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="44818-104">ここで説明するインターチェンジ処理プロパティは、HIPAA インターチェンジにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="44818-104">The interchange processing properties described here apply also to HIPAA interchanges.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="44818-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="44818-105">Prerequisites</span></span>  
 <span data-ttu-id="44818-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="44818-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-set-sender-receiver-and-security-properties"></a><span data-ttu-id="44818-107">送信者、受信者、およびセキュリティのプロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="44818-107">To set sender, receiver, and security properties</span></span>  
  
1. <span data-ttu-id="44818-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノード、およびクリック**X12 フォールバックの設定**します。</span><span class="sxs-lookup"><span data-stu-id="44818-108">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **X12 Fallback Settings**.</span></span>  
  
2. <span data-ttu-id="44818-109">**X12 フォールバック設定**] ダイアログ ボックスで、 **X12 アグリーメント ページ**] タブの [、**インターチェンジの設定**セクションで、[ **識別子**.</span><span class="sxs-lookup"><span data-stu-id="44818-109">In the **X12 Fallback Settings** dialog box, in the **X12 Agreement Pages** tab, under the **Interchange Settings** section, click **Identifiers**.</span></span>  
  
3. <span data-ttu-id="44818-110">値を入力、 **ISA1 2 (認証修飾子およびセキュリティ情報)** します。</span><span class="sxs-lookup"><span data-stu-id="44818-110">Enter values for the **ISA1-2 (Authorization qualifier and information)**.</span></span> <span data-ttu-id="44818-111">値を選択、**認証修飾子 (ISA1)** 関連付けられているドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="44818-111">Select the value for the **Authorization qualifier (ISA1)** from the associated drop-down list.</span></span> <span data-ttu-id="44818-112">この値は、以外の場合**00**の**値 (ISA2)** テキスト ボックスに、1 文字の英数字の最小値と最大 10 個を入力します。</span><span class="sxs-lookup"><span data-stu-id="44818-112">If this value is other than **00**, for the **Value (ISA2)** text box, enter a minimum of one alphanumeric character and a maximum of 10.</span></span> <span data-ttu-id="44818-113">これは、オプションのフィールドです。</span><span class="sxs-lookup"><span data-stu-id="44818-113">This is an optional field.</span></span> <span data-ttu-id="44818-114">これらの値を指定すると場合、それ以外の場合、受信したインターチェンジの ISA1、ISA2 フィールドと一致する確認[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インターチェンジは中断されます。</span><span class="sxs-lookup"><span data-stu-id="44818-114">If you do specify these values, make sure they match the ISA1 and ISA2 fields in a received interchange otherwise [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will suspend the interchange.</span></span>  
  
4. <span data-ttu-id="44818-115">値を入力、 **ISA3 ~ 4 (セキュリティ修飾子およびセキュリティ情報)** します。</span><span class="sxs-lookup"><span data-stu-id="44818-115">Enter values for the **ISA3-4 (Security qualifier and information)**.</span></span> <span data-ttu-id="44818-116">値を選択、**セキュリティ修飾子 (ISA3)** ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="44818-116">Select the value for the **Security qualifier (ISA3)** from the drop-down list.</span></span> <span data-ttu-id="44818-117">この値は、以外の場合**00**、用、**値 (ISA4)** テキスト ボックスに、1 つの英数字値の最小値、最大 10 個を入力します。</span><span class="sxs-lookup"><span data-stu-id="44818-117">If this value is other than **00**, for the **Value (ISA4)** text box, enter a minimum of one alphanumeric value and a maximum of 10.</span></span> <span data-ttu-id="44818-118">これは、オプションのフィールドです。</span><span class="sxs-lookup"><span data-stu-id="44818-118">This is an optional field.</span></span> <span data-ttu-id="44818-119">これらの値には、受信したインターチェンジの ISA3 と ISA4 フィールドが一致しない場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インターチェンジは中断されます。</span><span class="sxs-lookup"><span data-stu-id="44818-119">If these values do not match the ISA3 and ISA4 fields in a received interchange, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will suspend the interchange.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="44818-120">値**03 – パスワード (旧バージョンとの互換性) 用**、旧バージョンと互換性のために含まれる[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]は将来のバージョンで削除されます。</span><span class="sxs-lookup"><span data-stu-id="44818-120">The value **03 – Password (for backward compatibility)**, is included for backward compatibility with [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] and will be removed in future versions.</span></span>  
  
5. <span data-ttu-id="44818-121">値を入力**ISA5 ~ 6 (送信者の修飾子と識別子)** します。</span><span class="sxs-lookup"><span data-stu-id="44818-121">Enter the values for **ISA5-6 (Sender qualifier and identifier)**.</span></span> <span data-ttu-id="44818-122">修飾子の値を選択、**送信者 Id 修飾子 (ISA5)** ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="44818-122">Select a value for the qualifier from the **Sender Id Qualifier (ISA5)** drop-down list.</span></span> <span data-ttu-id="44818-123">識別子についての**値 (ISA6)** テキスト ボックスに、1 文字の英数字の最小値と最大 15 文字を入力します。</span><span class="sxs-lookup"><span data-stu-id="44818-123">For the identifier, in the **Value (ISA6)** text box, enter a minimum of one alphanumeric character and a maximum of 15 characters.</span></span>  
  
6. <span data-ttu-id="44818-124">値を入力 **[isa7] ~ 8 (受信者の修飾子と識別子)** します。</span><span class="sxs-lookup"><span data-stu-id="44818-124">Enter the values for **ISA7-8 (Receiver qualifier and identifier)**.</span></span> <span data-ttu-id="44818-125">修飾子の値を選択、**受信者 Id 修飾子 (ISA7)** ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="44818-125">Select a value for the qualifier from the **Receiver Id Qualifier (ISA7)** drop-down list.</span></span> <span data-ttu-id="44818-126">識別子についての**値 (ISA8)** テキスト ボックスに、1 文字の英数字の最小値と最大 15 文字を入力します。</span><span class="sxs-lookup"><span data-stu-id="44818-126">For the identifier, in the **Value (ISA8)** text box, enter a minimum of one alphanumeric character and a maximum of 15 characters.</span></span>  
  
7. <span data-ttu-id="44818-127">をクリックして**適用**を変更を受け入れるか、をクリックする**OK**を入力し、変更を検証して、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="44818-127">Click **Apply** to accept the changes, or click **OK** to enter and validate the changes, and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44818-128">参照</span><span class="sxs-lookup"><span data-stu-id="44818-128">See Also</span></span>  
 [<span data-ttu-id="44818-129">インターチェンジ処理用の X12 フォールバック アグリーメント プロパティの構成</span><span class="sxs-lookup"><span data-stu-id="44818-129">Configuring X12 Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)