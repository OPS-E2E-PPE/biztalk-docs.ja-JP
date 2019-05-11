---
title: (X12) 識別子の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 665698d1-c46c-4149-9715-381b4966dd92
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 603c7d2f27dc350f269942e3303d4eeebf26cb1e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355412"
---
# <a name="configuring-identifiers-x12"></a><span data-ttu-id="4c2a5-102">識別子の構成 (X12)</span><span class="sxs-lookup"><span data-stu-id="4c2a5-102">Configuring Identifiers (X12)</span></span>
<span data-ttu-id="4c2a5-103">パートナー アグリーメントでは、X12 を設定する必要がありますが、インターチェンジを受信しないことを確認するために承認およびセキュリティのプロパティの未承認の受信者。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-103">In the partner agreement, you must set the X12 authorization and security properties in order to verify that the interchange is not being received by unauthorized recipients.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4c2a5-104">ここで説明するインターチェンジ処理プロパティは、HIPAA インターチェンジにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-104">The interchange processing properties described here apply also to HIPAA interchanges.</span></span>  
> 
> [!IMPORTANT]
>  <span data-ttu-id="4c2a5-105">オフにした場合、このページで、次のプロパティが無効に、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェック ボックスを作成するパーティを作成するときに、契約です。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-105">The following properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
> 
> - <span data-ttu-id="4c2a5-106">**DestinationPartyName** **追加のアグリーメント リゾルバー**セクション。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-106">**DestinationPartyName** under **Additional Agreement Resolvers** section.</span></span>  
> 
>   <span data-ttu-id="4c2a5-107">プロパティが無効になるのは、パーティから受信中のインターチェンジのプロパティに対応する一方向のアグリーメント タブ上のみです。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-107">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="4c2a5-108">たとえば、2 つのパーティのパーティ A とパーティ B を作成するチェック ボックスをオフにしたパーティ A の場合は、上記のプロパティが無効になります、**パーティ A にパーティ B]-> [** 一方向アグリーメント タブ。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-108">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4c2a5-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="4c2a5-109">Prerequisites</span></span>  
 <span data-ttu-id="4c2a5-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-110">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-set-sender-receiver-and-security-properties"></a><span data-ttu-id="4c2a5-111">送信者、受信者、およびセキュリティのプロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="4c2a5-111">To set sender, receiver, and security properties</span></span>  
  
1. <span data-ttu-id="4c2a5-112">X12 エンコード アグリーメントを」の説明に従って作成[全般設定を構成する (X12)](../core/configuring-general-settings-x12.md)します。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-112">Create an X12 encoding agreement as described in [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span> <span data-ttu-id="4c2a5-113">既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-113">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2. <span data-ttu-id="4c2a5-114">一方向アグリーメント タブで、**インターチェンジの設定**セクションで、**識別子**します。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-114">On a one-way agreement tab, under **Interchange Settings** section, click **Identifiers**.</span></span>  
  
3. <span data-ttu-id="4c2a5-115">値を入力、 **ISA1 2 (認証修飾子およびセキュリティ情報)** します。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-115">Enter values for the **ISA1-2 (Authorization qualifier and information)**.</span></span> <span data-ttu-id="4c2a5-116">値を選択、**認証修飾子 (ISA1)** 関連付けられているドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-116">Select the value for the **Authorization qualifier (ISA1)** from the associated drop-down list.</span></span> <span data-ttu-id="4c2a5-117">この値は、以外の場合**00**の**値 (ISA2)** テキスト ボックスに、1 文字の英数字の最小値と最大 10 個を入力します。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-117">If this value is other than **00**, for the **Value (ISA2)** text box, enter a minimum of one alphanumeric character and a maximum of 10.</span></span> <span data-ttu-id="4c2a5-118">これは、オプションのフィールドです。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-118">This is an optional field.</span></span> <span data-ttu-id="4c2a5-119">これらの値を指定すると場合、それ以外の場合、受信したインターチェンジの ISA1、ISA2 フィールドと一致する確認[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インターチェンジは中断されます。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-119">If you do specify these values, make sure they match the ISA1 and ISA2 fields in a received interchange otherwise [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will suspend the interchange.</span></span>  
  
4. <span data-ttu-id="4c2a5-120">値を入力、 **ISA3 ~ 4 (セキュリティ修飾子およびセキュリティ情報)** します。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-120">Enter values for the **ISA3-4 (Security qualifier and information)**.</span></span> <span data-ttu-id="4c2a5-121">値を選択、**セキュリティ修飾子 (ISA3)** ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-121">Select the value for the **Security qualifier (ISA3)** from the drop-down list.</span></span> <span data-ttu-id="4c2a5-122">この値は、以外の場合**00**、用、**値 (ISA4)** テキスト ボックスに、1 つの英数字値の最小値、最大 10 個を入力します。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-122">If this value is other than **00**, for the **Value (ISA4)** text box, enter a minimum of one alphanumeric value and a maximum of 10.</span></span> <span data-ttu-id="4c2a5-123">これは、オプションのフィールドです。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-123">This is an optional field.</span></span> <span data-ttu-id="4c2a5-124">これらの値には、受信したインターチェンジの ISA3 と ISA4 フィールドが一致しない場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インターチェンジは中断されます。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-124">If these values do not match the ISA3 and ISA4 fields in a received interchange, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will suspend the interchange.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="4c2a5-125">値**03 – パスワード (旧バージョンとの互換性) 用**、旧バージョンと互換性のために含まれる[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]は将来のバージョンで削除されます。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-125">The value **03 – Password (for backward compatibility)**, is included for backward compatibility with [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] and will be removed in future versions.</span></span>  
  
5. <span data-ttu-id="4c2a5-126">値を入力**ISA5 ~ 6 (送信者の修飾子と識別子)** します。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-126">Enter the values for **ISA5-6 (Sender qualifier and identifier)**.</span></span> <span data-ttu-id="4c2a5-127">修飾子の値を選択、**送信者 Id 修飾子 (ISA5)** ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-127">Select a value for the qualifier from the **Sender Id Qualifier (ISA5)** drop-down list.</span></span> <span data-ttu-id="4c2a5-128">識別子についての**値 (ISA6)** テキスト ボックスに、1 文字の英数字の最小値と最大 15 文字を入力します。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-128">For the identifier, in the **Value (ISA6)** text box, enter a minimum of one alphanumeric character and a maximum of 15 characters.</span></span>  
  
6. <span data-ttu-id="4c2a5-129">値を入力 **[isa7] ~ 8 (受信者の修飾子と識別子)** します。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-129">Enter the values for **ISA7-8 (Receiver qualifier and identifier)**.</span></span> <span data-ttu-id="4c2a5-130">修飾子の値を選択、**送信者 Id 修飾子 (ISA7)** ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-130">Select a value for the qualifier from the **Sender Id Qualifier (ISA7)** drop-down list.</span></span> <span data-ttu-id="4c2a5-131">識別子についての**値 (ISA8)** テキスト ボックスに、1 文字の英数字の最小値と最大 15 文字を入力します。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-131">For the identifier, in the **Value (ISA8)** text box, enter a minimum of one alphanumeric character and a maximum of 15 characters.</span></span>  
  
7. <span data-ttu-id="4c2a5-132">**追加のアグリーメント リゾルバー**セクションの**DestinationPartyName**プロパティ、送信先パーティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-132">In the **Additional Agreement Resolvers** section, for **DestinationPartyName** property, specify a value for the destination party.</span></span> <span data-ttu-id="4c2a5-133">この値は、送信メッセージをアグリーメントに解決するのにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-133">This value is also used to resolve outbound messages to an agreement.</span></span> <span data-ttu-id="4c2a5-134">詳細については、「[アグリーメントの解決と送信 EDI メッセージのスキーマ決定](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)します。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-134">For more information see, [Agreement Resolution and Schema Determination for Outgoing EDI Messages](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="4c2a5-135">通常必要はありませんを設定する、 **DestinationPartyName**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-135">You typically do not need to set the **DestinationPartyName** property.</span></span> <span data-ttu-id="4c2a5-136">このプロパティは、使用可能なアップグレード シナリオをサポートするために、アグリーメント プロパティの一部として。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-136">This property is available as part of the agreement properties to support upgrade scenarios.</span></span> <span data-ttu-id="4c2a5-137">BizTalk Server 2006 R2 または BizTalk Server 2009 からアップグレードするときに、 **DestinationPartyName**プロパティが BizTalk Server 2006 R2 または BizTalk Server 2009 のパーティの名前に設定します。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-137">When upgrading from BizTalk Server 2006 R2 or BizTalk Server 2009, the **DestinationPartyName** property is set to the name of the party in BizTalk Server 2006 R2 or BizTalk Server 2009.</span></span>  
  
8. <span data-ttu-id="4c2a5-138">をクリックして**適用**を変更を受け入れるか、をクリックする**OK**を入力し、変更を検証して、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-138">Click **Apply** to accept the changes, or click **OK** to enter and validate the changes, and then close the dialog box.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="4c2a5-139">クリックすると**OK**または**適用**この段階で、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-139">If you click **OK** or **Apply** at this stage, you will get an error.</span></span> <span data-ttu-id="4c2a5-140">ISA8 の値に ISA5 を提供する必要があるためにです、**識別子**他方の一方向アグリーメント タブのタブ。</span><span class="sxs-lookup"><span data-stu-id="4c2a5-140">That is because you still need to provide ISA5 to ISA8 values on the **Identifiers** tab for the other one-way agreement tab.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c2a5-141">参照</span><span class="sxs-lookup"><span data-stu-id="4c2a5-141">See Also</span></span>  
 [<span data-ttu-id="4c2a5-142">インターチェンジの設定の構成 (X12)</span><span class="sxs-lookup"><span data-stu-id="4c2a5-142">Configuring Interchange Settings (X12)</span></span>](../core/configuring-interchange-settings-x12.md)