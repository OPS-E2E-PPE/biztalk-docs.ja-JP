---
title: "パーティの全般プロパティの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbabf7e5-6388-4900-ad47-cf5d5af396b5
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4bb40e943cc06f298db01142590e2a133c1ee05
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-general-party-properties"></a><span data-ttu-id="b9bac-102">パーティの全般プロパティの構成</span><span class="sxs-lookup"><span data-stu-id="b9bac-102">Configuring General Party Properties</span></span>
<span data-ttu-id="b9bac-103">パーティまたは取引先は、ビジネス リレーションシップの参加組織を表します。</span><span class="sxs-lookup"><span data-stu-id="b9bac-103">A party or trading partner represents a participating organization in a business relationship.</span></span> <span data-ttu-id="b9bac-104">パーティのプロパティには次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b9bac-104">Party properties contain the following information:</span></span>  
  
-   <span data-ttu-id="b9bac-105">パーティ名などの全般情報</span><span class="sxs-lookup"><span data-stu-id="b9bac-105">General information such as party name</span></span>  
  
-   <span data-ttu-id="b9bac-106">パーティに関連付けられた送信ポート</span><span class="sxs-lookup"><span data-stu-id="b9bac-106">Send ports associated with the party</span></span>  
  
-   <span data-ttu-id="b9bac-107">パーティに関連付けられた証明書</span><span class="sxs-lookup"><span data-stu-id="b9bac-107">Certificates associated with the party</span></span>  
  
 <span data-ttu-id="b9bac-108">パーティまたは取引先の詳細については、次を参照してください。[取引パートナー](../core/trading-partners-and-business-profiles.md)です。</span><span class="sxs-lookup"><span data-stu-id="b9bac-108">For more information about parties or trading partners, see [Trading Partners](../core/trading-partners-and-business-profiles.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b9bac-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="b9bac-109">Prerequisites</span></span>  
 <span data-ttu-id="b9bac-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9bac-110">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-party-properties"></a><span data-ttu-id="b9bac-111">パーティのプロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="b9bac-111">To configure party properties</span></span>  
  
1.  <span data-ttu-id="b9bac-112">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックして**パーティ**、 をポイント**新規**、クリックして**パーティ**です。</span><span class="sxs-lookup"><span data-stu-id="b9bac-112">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
2.  <span data-ttu-id="b9bac-113">**全般**のページ、**パーティ プロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="b9bac-113">On the **General** page of the **Party Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="b9bac-114">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b9bac-114">Use this</span></span>|<span data-ttu-id="b9bac-115">目的</span><span class="sxs-lookup"><span data-stu-id="b9bac-115">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="b9bac-116">**名前**</span><span class="sxs-lookup"><span data-stu-id="b9bac-116">**Name**</span></span>|<span data-ttu-id="b9bac-117">パーティ名を入力します。</span><span class="sxs-lookup"><span data-stu-id="b9bac-117">Enter a party name.</span></span>|  
    |<span data-ttu-id="b9bac-118">**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理します。**</span><span class="sxs-lookup"><span data-stu-id="b9bac-118">**Local BizTalk processes messages received by the party or supports sending messages from this party**</span></span>|<span data-ttu-id="b9bac-119">パーティが、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]をホストしている同じ取引先を表すように指定する場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="b9bac-119">Select this checkbox to specify that the party represents the same trading partner that also hosts [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="b9bac-120">**重要:**に付属する既定のパイプラインを使用するソリューション 2 パーティ TPM の[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、少なくとも 1 つのパーティの場合は、このチェック ボックスを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9bac-120">**Important:**  For a two-party TPM solution that uses out-of-the-box pipelines shipped with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you must select this check box for at least one party.</span></span> <span data-ttu-id="b9bac-121">**注:**このチェック ボックスをオフにすると、一部のプロパティは、このパーティのアグリーメントの作成中に無効になります。</span><span class="sxs-lookup"><span data-stu-id="b9bac-121">**Note:**  If you clear this check box, some properties will be disabled while creating the agreements for this party.</span></span>|  
    |<span data-ttu-id="b9bac-122">**追加のプロパティ – 名前/値**</span><span class="sxs-lookup"><span data-stu-id="b9bac-122">**Additional Properties – Name / Value**</span></span>|<span data-ttu-id="b9bac-123">パーティに関する任意の情報を格納する、名前と値の組み合わせを入力します。</span><span class="sxs-lookup"><span data-stu-id="b9bac-123">Enter a name-value pair to store any information about the party.</span></span> <span data-ttu-id="b9bac-124">名前と値の組み合わせは、必要な数だけ追加できます。</span><span class="sxs-lookup"><span data-stu-id="b9bac-124">You can add as many name-value pairs as you want.</span></span> <span data-ttu-id="b9bac-125">**注:**なんらかの処理の名前と値のペアが、BizTalk Server によって使用されません。 このデータは、情報提供のみを目的のはします。</span><span class="sxs-lookup"><span data-stu-id="b9bac-125">**Note:**  The name-value pairs are not used by the BizTalk Server for any processing; this data is for information purposes only.</span></span>|  
    |<span data-ttu-id="b9bac-126">**Del**</span><span class="sxs-lookup"><span data-stu-id="b9bac-126">**Delete**</span></span>|<span data-ttu-id="b9bac-127">選択した名前と値の組み合わせを削除する場合にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9bac-127">Click to delete the selected name-value pair.</span></span>|  
  
3.  <span data-ttu-id="b9bac-128">**送信ポート**のページ、**パーティ プロパティ** ダイアログ ボックスで、次の操作です。</span><span class="sxs-lookup"><span data-stu-id="b9bac-128">On the **Send Ports** page of the **Party Properties** dialog box, do the following.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b9bac-129">[!INCLUDE[prague](../includes/prague-md.md)] では、送信ポートの関連付けをアグリーメント レベルで行います。</span><span class="sxs-lookup"><span data-stu-id="b9bac-129">In [!INCLUDE[prague](../includes/prague-md.md)], the send port association is done at the agreement level.</span></span> <span data-ttu-id="b9bac-130">**送信ポート**下位互換性は、パーティのプロパティの一部として使用可能なページです。</span><span class="sxs-lookup"><span data-stu-id="b9bac-130">The **Send Ports** page available as part of the party properties is purely for backward compatibility.</span></span> <span data-ttu-id="b9bac-131">送信ポートをアグリーメントと関連付けるたびに、送信ポート設定がパーティ設定にも反映され、このページにも送信ポートの関連付けが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9bac-131">Whenever you associate a send port with an agreement, the send port setting is also propagated to the party setting and you can see the send port association in this page as well.</span></span> <span data-ttu-id="b9bac-132">ただし、その逆は真ではありません。</span><span class="sxs-lookup"><span data-stu-id="b9bac-132">However, the reverse is not true.</span></span> <span data-ttu-id="b9bac-133">送信ポートをパーティと関連付け、その送信ポートをアグリーメント設定の一部として自動的に利用可能にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b9bac-133">You cannot associate a send port with a party and then have that send port be automatically available as part of the agreement settings.</span></span> <span data-ttu-id="b9bac-134">送信ポートをアグリーメントに関連付ける方法の詳細については、次を参照してください。[を構成する送信ポートの関連付け (X12)](../core/configuring-send-port-association-x12.md)または[送信ポート (EDIFACT) の関連付けを構成する](../core/configuring-send-port-association-edifact.md)です。</span><span class="sxs-lookup"><span data-stu-id="b9bac-134">For more information on how to associate send ports with agreement, see [Configuring Send Port Association (X12)](../core/configuring-send-port-association-x12.md) or [Configuring Send Port Association (EDIFACT)](../core/configuring-send-port-association-edifact.md).</span></span>  
  
    |<span data-ttu-id="b9bac-135">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b9bac-135">Use this</span></span>|<span data-ttu-id="b9bac-136">目的</span><span class="sxs-lookup"><span data-stu-id="b9bac-136">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="b9bac-137">**送信ポートの名前**</span><span class="sxs-lookup"><span data-stu-id="b9bac-137">**Send ports - Name**</span></span>|<span data-ttu-id="b9bac-138">ドロップダウン リストから、このパーティにバインドする送信ポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="b9bac-138">From the drop-down list, select a send port to bind to this party.</span></span>|  
    |<span data-ttu-id="b9bac-139">**送信ポートの URI**</span><span class="sxs-lookup"><span data-stu-id="b9bac-139">**Send ports - URI**</span></span>|<span data-ttu-id="b9bac-140">送信ポートのアドレスを表示します。</span><span class="sxs-lookup"><span data-stu-id="b9bac-140">Displays the send port address.</span></span>|  
    |<span data-ttu-id="b9bac-141">**[削除]**</span><span class="sxs-lookup"><span data-stu-id="b9bac-141">**Remove**</span></span>|<span data-ttu-id="b9bac-142">選択した送信ポートをパーティから削除する をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9bac-142">Click to remove the selected send port from the party.</span></span>|  
    |<span data-ttu-id="b9bac-143">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="b9bac-143">**Properties**</span></span>|<span data-ttu-id="b9bac-144">クリックすると表示、**送信ポートのプロパティ**選択した送信ポートのダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="b9bac-144">Click to display the **Send Port Properties** dialog box for the selected send port.</span></span>|  
  
4.  <span data-ttu-id="b9bac-145">**証明書** ページで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="b9bac-145">On the **Certificate** page, do the following:</span></span>  
  
    |<span data-ttu-id="b9bac-146">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b9bac-146">Use this</span></span>|<span data-ttu-id="b9bac-147">目的</span><span class="sxs-lookup"><span data-stu-id="b9bac-147">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="b9bac-148">**参照**</span><span class="sxs-lookup"><span data-stu-id="b9bac-148">**Browse**</span></span>|<span data-ttu-id="b9bac-149">クリックすると表示、**証明書の選択**ダイアログ ボックスで、パーティに送信されるメッセージに適用するローカル コンピューターまたはその他のユーザーの証明書ストアから署名証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9bac-149">Click to display the **Select Certificate** dialog box, where you select the signature certificate from the Local Machine or Other People certificate store to apply to messages transmitted to the party.</span></span>|  
    |<span data-ttu-id="b9bac-150">**共通名**</span><span class="sxs-lookup"><span data-stu-id="b9bac-150">**Common Name**</span></span>|<span data-ttu-id="b9bac-151">選択した証明書の説明を表示します。</span><span class="sxs-lookup"><span data-stu-id="b9bac-151">Displays a description of the selected certificate.</span></span>|  
    |<span data-ttu-id="b9bac-152">**拇印**</span><span class="sxs-lookup"><span data-stu-id="b9bac-152">**Thumbprint**</span></span>|<span data-ttu-id="b9bac-153">パーティの解決および署名の確認に使用される秘密キー証明書の拇印を表示します。</span><span class="sxs-lookup"><span data-stu-id="b9bac-153">Displays the thumbprint of the private key certificate that is used for party resolution and signature verification.</span></span> <span data-ttu-id="b9bac-154">証明書の拇印には、HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH、H は 16 進数字 (0 ~ 9 の数字) または a ~ F の文字の形式があります。</span><span class="sxs-lookup"><span data-stu-id="b9bac-154">The certificate thumbprint has the format HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, where H is a hexadecimal digit (a number from 0 through 9 or a letter from A through F).</span></span>|  
    |<span data-ttu-id="b9bac-155">**証明書を削除します。**</span><span class="sxs-lookup"><span data-stu-id="b9bac-155">**Remove certificate**</span></span>|<span data-ttu-id="b9bac-156">表示されている証明書を削除する場合にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9bac-156">Click to remove the displayed certificate.</span></span>|  
  
5.  <span data-ttu-id="b9bac-157">をクリックして**適用**、プロパティを受け入れるか、をクリックする**[ok]**構成設定を完了します。</span><span class="sxs-lookup"><span data-stu-id="b9bac-157">Click **Apply** to accept the properties, or click **OK** to complete the configuration setting.</span></span> <span data-ttu-id="b9bac-158">どちらの操作では、設定を検証します。</span><span class="sxs-lookup"><span data-stu-id="b9bac-158">Either action will validate the settings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9bac-159">参照</span><span class="sxs-lookup"><span data-stu-id="b9bac-159">See Also</span></span>  
 [<span data-ttu-id="b9bac-160">EDI のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="b9bac-160">Configuring EDI Properties</span></span>](../core/configuring-edi-properties.md)