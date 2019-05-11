---
title: 受信確認 (Mdn) (AS2) の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb2bf98a-deb4-460f-a1fc-3d2397c39470
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81d1eb8c500ac746606da82509fb74e4d9afeb6a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391383"
---
# <a name="configuring-acknowledgements-mdns-as2"></a><span data-ttu-id="219c3-102">受信確認 (Mdn) (AS2) の構成</span><span class="sxs-lookup"><span data-stu-id="219c3-102">Configuring Acknowledgements (MDNs) (AS2)</span></span>
<span data-ttu-id="219c3-103">パートナー アグリーメントでは、AS2 メッセージを受信するパーティの MDN 応答を生成および返送を指定できます。</span><span class="sxs-lookup"><span data-stu-id="219c3-103">In the partner agreement, you can specify how the party receiving the AS2 message generates an MDN response and sends it to back.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="219c3-104">オフにした場合、このページで、次のプロパティが無効に、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェック ボックスを作成するパーティを作成するときに、契約です。</span><span class="sxs-lookup"><span data-stu-id="219c3-104">The following properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
> 
> - <span data-ttu-id="219c3-105">**MDN を受信しない場合は AS2 メッセージ再送信** チェック ボックスと関連プロパティ</span><span class="sxs-lookup"><span data-stu-id="219c3-105">**Resend AS2 message if MDN not received** check box and associated properties</span></span>  
>   -   <span data-ttu-id="219c3-106">**送信ポートの設定を上書き** チェック ボックスと関連プロパティ</span><span class="sxs-lookup"><span data-stu-id="219c3-106">**Override send port settings** check box and associated properties</span></span>  
> 
>   <span data-ttu-id="219c3-107">プロパティが無効になるのは、パーティから受信中のインターチェンジのプロパティに対応する一方向のアグリーメント タブ上のみです。</span><span class="sxs-lookup"><span data-stu-id="219c3-107">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="219c3-108">たとえば、2 つのパーティのパーティ A とパーティ B を作成するチェック ボックスをオフにしたパーティ A の場合は、上記のプロパティが無効になります、**パーティ A にパーティ B]-> [** 一方向アグリーメント タブ。</span><span class="sxs-lookup"><span data-stu-id="219c3-108">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="219c3-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="219c3-109">Prerequisites</span></span>  
 <span data-ttu-id="219c3-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="219c3-110">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-acknowledgements"></a><span data-ttu-id="219c3-111">受信確認を構成するには</span><span class="sxs-lookup"><span data-stu-id="219c3-111">To configure acknowledgements</span></span>  
  
1. <span data-ttu-id="219c3-112">AS2 契約の作成」の説明に従って[全般設定の構成 (AS2)](../core/configuring-general-settings-as2.md)します。</span><span class="sxs-lookup"><span data-stu-id="219c3-112">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="219c3-113">既存の AS2 アグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="219c3-113">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2. <span data-ttu-id="219c3-114">一方向アグリーメント タブで、次のようにクリックします。**受信確認 (Mdn)** します。</span><span class="sxs-lookup"><span data-stu-id="219c3-114">On a one-way agreement tab, click **Acknowledgements (MDNs)**.</span></span>  
  
3. <span data-ttu-id="219c3-115">選択、 **MessageBox にルーティング/配信の受信 MDN を処理する**をパススルー メッセージとしてし、メッセージ ボックスに、A2 デコーダ経由の MDN をルーティングする チェック ボックス。</span><span class="sxs-lookup"><span data-stu-id="219c3-115">Select the **Process inbound MDN into MessageBox for routing/delivery options** check box to route the MDN through the A2 Decoder as a passthrough message and then into the MessageBox.</span></span> <span data-ttu-id="219c3-116">このプロパティを選択すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]昇格、`IsAS2MdnResponseMessage`ルーティングを行うのためのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="219c3-116">When this property is selected, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] promotes the `IsAS2MdnResponseMessage` property for routing purposes.</span></span>  
  
4. <span data-ttu-id="219c3-117">オンにした場合、**検証と MSDN のメッセージ ヘッダーの代わりにアグリーメントの設定を使用して**プロパティ、**検証**] ページで、[、 **mdn を要求する**チェック ボックスをオンの場合、取引先は、AS2 メッセージへの応答で MDN を生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="219c3-117">If you checked the **Use agreement settings for validation and MSDN instead of message header** property in the **Validations** page, select the **Request MDN** check box if the trading partner must generate an MDN in response to the AS2 message.</span></span>  
  
    <span data-ttu-id="219c3-118">場合、 **mdn を要求する** チェック ボックスが選択されている次のプロパティを設定することもできます場合、。</span><span class="sxs-lookup"><span data-stu-id="219c3-118">If the **Request MDN** check box is selected, you can also set the following properties:</span></span>  
  
   1. <span data-ttu-id="219c3-119">選択、**署名付き MDN を要求** チェック ボックスとの間、**署名アルゴリズム**ドロップダウン選択 MIC アルゴリズム取引先が MDN に署名するために使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="219c3-119">Select the **Request signed MDN** check box and from the **Signing Algorithm** drop-down select the MIC algorithm that the trading partner must use to sign the MDN.</span></span> [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="219c3-120">MD5、SHA1、SHA2 をサポート (SHA256 (既定値)、SHA384、SHA512)。</span><span class="sxs-lookup"><span data-stu-id="219c3-120">supports MD5, SHA1, and SHA2 (SHA256 (default), SHA384, and SHA512).</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="219c3-121">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]以降のバージョン**、SHA2 サポートが自動的に含まれます。</span><span class="sxs-lookup"><span data-stu-id="219c3-121">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] and newer versions**, SHA2 support is automatically included.</span></span> <span data-ttu-id="219c3-122">以前[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]バージョンを参照してください[KB 3123748](https://support.microsoft.com/kb/3123748)します。</span><span class="sxs-lookup"><span data-stu-id="219c3-122">For previous [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] versions, see [KB 3123748](https://support.microsoft.com/kb/3123748).</span></span>
  
   2. <span data-ttu-id="219c3-123">選択、**非同期 MDN を要求する**チェック ボックスをオンし、 **- Receipt-delivery-option (URL)** テキスト ボックスに、受信側パーティは MDN を送信する必要がある URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="219c3-123">Select the **Request asynchronous MDN** check box and then in the **Receipt-Delivery-Option (URL)** text box, enter the URL that the receiving party should send the MDN to.</span></span>  
  
       <span data-ttu-id="219c3-124">場合、**非同期 MDN を要求する** チェック ボックスが選択されている次のプロパティを設定することもできます場合、。</span><span class="sxs-lookup"><span data-stu-id="219c3-124">If the **Request asynchronous MDN** check box is selected, you can also set the following properties:</span></span>  
  
      1. <span data-ttu-id="219c3-125">選択、 **MDN を受信しない場合は再送信 AS2 メッセージ**AS2 メッセージの再送信を有効にする チェック ボックス。</span><span class="sxs-lookup"><span data-stu-id="219c3-125">Select the **Resend AS2 message if MDN not received** check box to enable retransmission of the AS2 message.</span></span> <span data-ttu-id="219c3-126">値を入力**最小 AS2 メッセージ再送信間隔**、**数の AS2 メッセージ再送信試行**と**AS2 メッセージ再**を指定するフィールド、間隔、最大試行回数と、メッセージの再送信を停止するタイミングを再試行してください。</span><span class="sxs-lookup"><span data-stu-id="219c3-126">Enter a value for **Minimum AS2 message resend interval**, **Number of AS2 message resend attempts** and **Stop attempting AS2 message resends after** fields to specify the retry interval, maximum number of attempts and when to stop resending the message.</span></span>  
  
         > [!NOTE]
         >  <span data-ttu-id="219c3-127">選択する必要があります、**レポートを有効にする**チェック ボックスをオン、**全般プロパティ**のページ、**全般**タブを選択する前に**再送信 AS2 メッセージの場合は MDN されません受信した**します。</span><span class="sxs-lookup"><span data-stu-id="219c3-127">You must select the **Turn ON Reporting** check box on the **General Properties** page of the **General** tab before selecting **Resend AS2 message if MDN not received**.</span></span>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="219c3-128">AS2 レポートを AS2 メッセージ再送信するタイミングを決定するために保存された追跡情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="219c3-128">uses tracking information stored for AS2 reporting in order to determine when to resend an AS2 message.</span></span>  
  
      2. <span data-ttu-id="219c3-129">場合**MDN を受信しない場合は再送信 AS2 メッセージ** チェック ボックスを選択すると、確認**送信ポートの設定を上書き**を指定する、 **HTTP 最小再試行間隔**と**HTTP 再試行の回数**します。</span><span class="sxs-lookup"><span data-stu-id="219c3-129">If **Resend AS2 message if MDN not received** check box is selected, check **Override send port settings** to specify the **Minimum HTTP retry interval** and **Number of HTTP retry attempts**.</span></span> <span data-ttu-id="219c3-130">値を入力、 **HTTP しようとすると停止の後で再試行**を HTTP アダプターを使用した再試行の最大時間を指定するフィールド。</span><span class="sxs-lookup"><span data-stu-id="219c3-130">Enter a value for the **Stop attempting HTTP retries after** field to specify the maximum amount of time to attempt retries using the HTTP adapter.</span></span>  
  
   3. <span data-ttu-id="219c3-131">選択した場合、**非同期 MDN を要求する** チェック ボックスの URL を指定して **- Receipt-delivery-option (URL)** プロパティ、**ディス ポジション-通知-に**テキストボックスで、既定では、同じ URL に設定します。</span><span class="sxs-lookup"><span data-stu-id="219c3-131">If you selected the **Request asynchronous MDN** check box and specified a URL for **Receipt-Delivery-Option (URL)** property, the **Disposition-Notification-To** text box, is by default set to the same URL.</span></span> <span data-ttu-id="219c3-132">選択しなかった場合、**非同期 MDN を要求する** チェック ボックスの値を入力する必要があります**ディス ポジション-通知-に**します。</span><span class="sxs-lookup"><span data-stu-id="219c3-132">If you did not select the **Request asynchronous MDN** check box, you must enter a value for **Disposition-Notification-To**.</span></span> <span data-ttu-id="219c3-133">このフィールドの値は、AS2 処理時には使用されません。</span><span class="sxs-lookup"><span data-stu-id="219c3-133">The value of this field is not used during AS2 processing.</span></span>  
  
5. <span data-ttu-id="219c3-134">をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="219c3-134">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="219c3-135">参照</span><span class="sxs-lookup"><span data-stu-id="219c3-135">See Also</span></span>  
 [<span data-ttu-id="219c3-136">AS2 アグリーメントのプロパティの構成</span><span class="sxs-lookup"><span data-stu-id="219c3-136">Configuring AS2 Agreement Properties</span></span>](../core/configuring-as2-agreement-properties.md)