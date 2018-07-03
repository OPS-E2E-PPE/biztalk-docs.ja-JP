---
title: 識別子の構成 (EDIFACT) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 097292f2-1aa5-42e4-aeee-c7d4cbdae17c
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c50743c237c66edcba1e6609dcd1ab9cb0081bc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997219"
---
# <a name="configuring-identifiers-edifact"></a><span data-ttu-id="f803f-102">識別子の構成 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="f803f-102">Configuring Identifiers (EDIFACT)</span></span>
<span data-ttu-id="f803f-103">未承認の受信者がインターチェンジを受信していないことを確認するには、パートナー アグリーメントで、受信者の参照パスワードを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f803f-103">In the partner agreement, you must set the recipient reference password, in order to verify that the interchange is not being received by unauthorized recipients.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f803f-104">オフにした場合、このページで、次のプロパティが無効に、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェック ボックスを作成するパーティを作成するときに、契約です。</span><span class="sxs-lookup"><span data-stu-id="f803f-104">The following properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
> 
> - <span data-ttu-id="f803f-105">**DestinationPartyName** **追加のアグリーメント リゾルバー**セクション。</span><span class="sxs-lookup"><span data-stu-id="f803f-105">**DestinationPartyName** under **Additional Agreement Resolvers** section.</span></span>  
> 
>   <span data-ttu-id="f803f-106">プロパティが無効になるのは、パーティから受信中のインターチェンジのプロパティに対応する一方向のアグリーメント タブ上のみです。</span><span class="sxs-lookup"><span data-stu-id="f803f-106">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="f803f-107">たとえば、2 つのパーティのパーティ A とパーティ B を作成するチェック ボックスをオフにしたパーティ A の場合は、上記のプロパティが無効になります、**パーティ A にパーティ B]-> [** 一方向アグリーメント タブ。</span><span class="sxs-lookup"><span data-stu-id="f803f-107">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f803f-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="f803f-108">Prerequisites</span></span>  
 <span data-ttu-id="f803f-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f803f-109">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-set-the-sender-recipient-and-recipient-password"></a><span data-ttu-id="f803f-110">送信者、受信者、および受信者パスワードを設定するには</span><span class="sxs-lookup"><span data-stu-id="f803f-110">To set the sender, recipient, and recipient password</span></span>  
  
1.  <span data-ttu-id="f803f-111">EDIFACT エンコード アグリーメントを」の説明に従って作成[を構成する一般的な設定 (EDIFACT)](../core/configuring-general-settings-edifact.md)します。</span><span class="sxs-lookup"><span data-stu-id="f803f-111">Create an EDIFACT encoding agreement as described in [Configuring General Settings (EDIFACT)](../core/configuring-general-settings-edifact.md).</span></span> <span data-ttu-id="f803f-112">既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="f803f-112">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="f803f-113">一方向アグリーメント タブで、**インターチェンジの設定**セクションで、**識別子**します。</span><span class="sxs-lookup"><span data-stu-id="f803f-113">On a one-way agreement tab, under **Interchange Settings** section, click **Identifiers**.</span></span>  
  
3.  <span data-ttu-id="f803f-114">**送信者 (UNB2)** セクションで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f803f-114">In the **Sender (UNB2)** section, do the following:</span></span>  
  
    1.  <span data-ttu-id="f803f-115">**Id (UNB2.1)**、1 つの最小値、35 文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="f803f-115">For **Identification (UNB2.1)**, enter an alphanumeric value with a minimum of one and a maximum of 35.</span></span> <span data-ttu-id="f803f-116">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="f803f-116">This is a required field.</span></span>  
  
    2.  <span data-ttu-id="f803f-117">**コードの修飾子 (UNB2.2)**、ドロップダウン リストから値を選択します。</span><span class="sxs-lookup"><span data-stu-id="f803f-117">For **Code qualifier (UNB2.2)**, select a value from the drop-down list.</span></span> <span data-ttu-id="f803f-118">このフィールドの入力は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="f803f-118">This is an optional field.</span></span>  
  
    3.  <span data-ttu-id="f803f-119">**逆ルーティングのアドレス (UNB2.3)**、1 つの文字の最小値、最大 14 文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="f803f-119">For **Reverse routing address (UNB2.3)**, enter an alphanumeric value with a minimum of one character and a maximum of 14 characters.</span></span> <span data-ttu-id="f803f-120">このフィールドの入力は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="f803f-120">This is an optional field.</span></span>  
  
4.  <span data-ttu-id="f803f-121">**受信者 (UNB3)** セクションで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f803f-121">In the **Recipient (UNB3)** section, do the following:</span></span>  
  
    1.  <span data-ttu-id="f803f-122">**Id (UNB3.1)**、1 つの最小値、35 文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="f803f-122">For **Identification (UNB3.1)**, enter an alphanumeric value with a minimum of one and a maximum of 35.</span></span> <span data-ttu-id="f803f-123">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="f803f-123">This is a required field.</span></span>  
  
    2.  <span data-ttu-id="f803f-124">**コードの修飾子 (UNB3.2)**、ドロップダウン リストから値を選択します。</span><span class="sxs-lookup"><span data-stu-id="f803f-124">For **Code qualifier (UNB3.2)**, select a value from the drop-down list.</span></span> <span data-ttu-id="f803f-125">このフィールドの入力は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="f803f-125">This is an optional field.</span></span>  
  
    3.  <span data-ttu-id="f803f-126">**逆ルーティングのアドレス (UNB3.3)**、1 つの文字の最小値、最大 14 文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="f803f-126">For **Reverse routing address (UNB3.3)**, enter an alphanumeric value with a minimum of one character and a maximum of 14 characters.</span></span> <span data-ttu-id="f803f-127">このフィールドの入力は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="f803f-127">This is an optional field.</span></span>  
  
    4.  <span data-ttu-id="f803f-128">必要な場合、**受信者の参照パスワード (UNB6)** セクションで、受信者の参照パスワードの値を入力します。</span><span class="sxs-lookup"><span data-stu-id="f803f-128">If required, in the **Recipient reference password (UNB6)** section, enter values for the recipient reference password.</span></span> <span data-ttu-id="f803f-129">**値 (UNB6.1)**、1 つの最小値、14 文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="f803f-129">For **Value (UNB6.1)**, enter an alphanumeric value with a minimum of one and a maximum of 14.</span></span> <span data-ttu-id="f803f-130">**修飾子 (UNB6.2)**、1 つの文字の最小値、最大 2 つの文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="f803f-130">For **Qualifier (UNB6.2)**, enter an alphanumeric value with a minimum of one character and a maximum of two characters.</span></span> <span data-ttu-id="f803f-131">これらは省略可能なフィールドです。</span><span class="sxs-lookup"><span data-stu-id="f803f-131">These are optional fields.</span></span> <span data-ttu-id="f803f-132">これらの値が、受信したインターチェンジの "UNB6.1" フィールドおよび "UNB6.2" フィールドと一致しない場合、インターチェンジは中断されます。</span><span class="sxs-lookup"><span data-stu-id="f803f-132">If these values do not match the UNB6.1 and UNB6.2 fields in a received interchange, BizTalk Server will suspend the interchange.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="f803f-133">組み合わせた**UNB6.1**と**UNB6.2**で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f803f-133">The combination of **UNB6.1** and **UNB6.2** must be unique.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="f803f-134">[UNB6.1] と [UNB6.2] の両方に値を入力し、変更を適用してから、[UNB6.1] の値を削除すると、[UNB6.2] の値も削除されて、このフィールドが無効になります。</span><span class="sxs-lookup"><span data-stu-id="f803f-134">If you enter values for both UNB6.1 and UNB6.2, apply the changes and then blank out UNB6.1, the value in UNB6.2 will also be deleted and the field will be disabled.</span></span>  
  
5.  <span data-ttu-id="f803f-135">**追加のアグリーメント リゾルバー**セクションの**DestinationPartyName**プロパティ、送信先パーティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="f803f-135">In the **Additional Agreement Resolvers** section, for **DestinationPartyName** property, specify a value for the destination party.</span></span> <span data-ttu-id="f803f-136">この値は、アグリーメントに対して送信メッセージを解決するためにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="f803f-136">This value is also used to resolve outbound messages to an agreement.</span></span> <span data-ttu-id="f803f-137">詳細については、「[アグリーメントの解決と送信 EDI メッセージのスキーマ決定](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)します。</span><span class="sxs-lookup"><span data-stu-id="f803f-137">For more information see, [Agreement Resolution and Schema Determination for Outgoing EDI Messages](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f803f-138">通常必要はありませんを設定する、 **DestinationPartyName**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="f803f-138">You typically do not need to set the **DestinationPartyName** property.</span></span> <span data-ttu-id="f803f-139">このプロパティは、アップグレード シナリオをサポートするアグリーメント プロパティの一部として使用できます。</span><span class="sxs-lookup"><span data-stu-id="f803f-139">This property is available as part of the agreement properties to support upgrade scenarios.</span></span> <span data-ttu-id="f803f-140">BizTalk Server 2006 R2 または BizTalk Server 2009 からアップグレードするときに、 **DestinationPartyName**プロパティが BizTalk Server 2006 R2 または BizTalk Server 2009 のパーティの名前に設定します。</span><span class="sxs-lookup"><span data-stu-id="f803f-140">When upgrading from BizTalk Server 2006 R2 or BizTalk Server 2009, the **DestinationPartyName** property is set to the name of the party in BizTalk Server 2006 R2 or BizTalk Server 2009.</span></span>  
  
6.  <span data-ttu-id="f803f-141">をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="f803f-141">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="f803f-142">クリックすると**OK**または**適用**この段階で、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="f803f-142">If you click **OK** or **Apply** at this stage, you will get an error.</span></span> <span data-ttu-id="f803f-143">UNB2 と UNB3 の値を提供する必要があるためにです、**識別子**他方の一方向アグリーメント タブのタブ。</span><span class="sxs-lookup"><span data-stu-id="f803f-143">That is because you still need to provide UNB2 and UNB3 values on the **Identifiers** tab for the other one-way agreement tab.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f803f-144">参照</span><span class="sxs-lookup"><span data-stu-id="f803f-144">See Also</span></span>  
 [<span data-ttu-id="f803f-145">インターチェンジの設定の構成 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="f803f-145">Configuring Interchange Settings (EDIFACT)</span></span>](../core/configuring-interchange-settings-edifact.md)