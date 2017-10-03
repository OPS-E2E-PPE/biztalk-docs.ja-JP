---
title: "検証 (AS2) の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1ff22dc8-a544-46f9-86fb-f6845e2dfe46
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e135d048f7dede032803b5830faec4570fa1f4d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-validation-as2"></a><span data-ttu-id="971df-102">検証の構成 (AS2)</span><span class="sxs-lookup"><span data-stu-id="971df-102">Configuring Validation (AS2)</span></span>
<span data-ttu-id="971df-103">パートナー アグリーメントで、受信 AS2 メッセージを検証する検証設定を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="971df-103">In the partner agreement, you must specify the validation settings to validate the inbound AS2 message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="971df-104">プロパティが無効**パーティ A にパーティ B->** をオフにした場合は、一方向アグリーメント タブの**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する** チェック ボックスパーティ A の同じ ページで、ただし、次のプロパティが無効にします**パーティ B には、パーティ A が->**  A の作成中に、チェック ボックスを選択した場合のタブ</span><span class="sxs-lookup"><span data-stu-id="971df-104">No properties are disabled on **Party A->Party B** one-way agreement tab if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box for Party A. However, the following properties are disabled on the same page in the **Party B->Party A** tab if you selected the check box while creating Party A.</span></span>  
>   
>  -   <span data-ttu-id="971df-105">**検証および MDN に対してメッセージ ヘッダーの代わりにアグリーメントの設定を使用します。**</span><span class="sxs-lookup"><span data-stu-id="971df-105">**Use agreement settings for validation and MDN instead of message header**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="971df-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="971df-106">Prerequisites</span></span>  
 <span data-ttu-id="971df-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="971df-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-validation-properties"></a><span data-ttu-id="971df-108">検証プロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="971df-108">To configure validation properties</span></span>  
  
1.  <span data-ttu-id="971df-109">AS2 アグリーメントを作成する」の説明に従って[全般設定の構成 (AS2)](../core/configuring-general-settings-as2.md)です。</span><span class="sxs-lookup"><span data-stu-id="971df-109">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="971df-110">既存の AS2 アグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="971df-110">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="971df-111">一方向アグリーメント タブで、をクリックして**検証**です。</span><span class="sxs-lookup"><span data-stu-id="971df-111">On a one-way agreement tab, click **Validation**.</span></span>  
  
3.  <span data-ttu-id="971df-112">選択、**検証および MDN に対してメッセージ ヘッダーの代わりにアグリーメントの設定を使用して**するチェック ボックス[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]デジタル署名、圧縮、および暗号化の設定に基づいて、受信メッセージの検証アグリーメント。</span><span class="sxs-lookup"><span data-stu-id="971df-112">Select the **Use agreement settings for validation and MDN instead of message header** check box if you want [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] validate the digital signature, compression, and encryption of the incoming message, based upon the settings in the agreement.</span></span> <span data-ttu-id="971df-113">このチェック ボックスをオフにすると、この処理を決定するために、アグリーメントのプロパティではなく、メッセージの AS2 ヘッダーのプロパティに対してメッセージが検証されます。</span><span class="sxs-lookup"><span data-stu-id="971df-113">If the check box is cleared, the messages will be validated against the properties in the message AS2 header instead of the agreement properties to determine this processing.</span></span> <span data-ttu-id="971df-114">AS2 ヘッダーの一覧は、次を参照してください。 [AS2 メッセージ](../core/as2-messages.md)です。</span><span class="sxs-lookup"><span data-stu-id="971df-114">For a list of AS2 headers, see [AS2 Messages](../core/as2-messages.md).</span></span>  
  
4.  <span data-ttu-id="971df-115">選択、**メッセージに署名する必要があります**受信メッセージが署名されていることを確認する チェック ボックスです。</span><span class="sxs-lookup"><span data-stu-id="971df-115">Select the **Message should be signed** check box to ensure that the inbound message is signed.</span></span>  
  
5.  <span data-ttu-id="971df-116">選択、**メッセージを圧縮する**受信メッセージが圧縮されていることを確認する チェック ボックスです。</span><span class="sxs-lookup"><span data-stu-id="971df-116">Select the **Message should be compressed** check box to ensure that the inbound message is compressed.</span></span>  
  
6.  <span data-ttu-id="971df-117">選択、**メッセージを暗号化する**受信メッセージが暗号化されていることを確認する チェック ボックスです。</span><span class="sxs-lookup"><span data-stu-id="971df-117">Select the **Message should be encrypted** check box to ensure that the inbound message is encrypted.</span></span> <span data-ttu-id="971df-118">暗号化アルゴリズムを選択して、**暗号化アルゴリズム**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="971df-118">Select the encryption algorithm from the **Encryption Algorithm** drop-down list.</span></span> 

    <span data-ttu-id="971df-119">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]以降のバージョン**AES のサポートは自動的に含まれます。</span><span class="sxs-lookup"><span data-stu-id="971df-119">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] and newer versions**, AES support is automatically included.</span></span> <span data-ttu-id="971df-120">DES3、RC2 では、AES128 のオプションがあります (既定)、AES192、AES256 です。</span><span class="sxs-lookup"><span data-stu-id="971df-120">Options include DES3, RC2, AES128 (default), AES192, and AES256.</span></span>
    
    <span data-ttu-id="971df-121">以前[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]バージョン、オプションは DES3 および RC2。</span><span class="sxs-lookup"><span data-stu-id="971df-121">For previous [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] versions, the options are DES3 and RC2.</span></span>
  
    > [!NOTE]
    >  <span data-ttu-id="971df-122">適切なプロパティが設定されている場合のみ、AS2 受信パイプラインはデジタル署名の検証、メッセージの圧縮解除、またはメッセージの解読を行います。</span><span class="sxs-lookup"><span data-stu-id="971df-122">Only if the appropriate property is set, the AS2 receive pipeline verifies the digital signature, decompresses the message, or decrypts the message.</span></span> <span data-ttu-id="971df-123">場合、**検証および MDN に対してメッセージ ヘッダーの代わりにアグリーメントの設定を使用して**プロパティが選択されているし、メッセージが署名、圧縮、およびアグリーメントで選択されているものの暗号化のさまざまなトランスポートのプロパティプロパティ、AS2 デコーダはメッセージを中断し、エラーを送信します。</span><span class="sxs-lookup"><span data-stu-id="971df-123">If the **Use agreement settings for validation and MDN instead of message header** property is selected and the message has different transport properties for signing, compression, and encryption than those selected on the agreement properties, then the AS2 Decoder will suspend the message and post an error.</span></span>  
  
7.  <span data-ttu-id="971df-124">選択、**証明書失効リストのチェック**受信メッセージの検証に使用する証明書をそれが取り消されたことを示す、証明書失効リストに含まれているかどうかを決定する チェック ボックスまたは、有効期限の日付が渡されるかどうか。</span><span class="sxs-lookup"><span data-stu-id="971df-124">Select the **Check Certification Revocation List** check box to determine whether the certificate to be used in validating an incoming message has been included in the Certification Revocation List, indicating that it has been revoked, or whether the expiration date has passed.</span></span> <span data-ttu-id="971df-125">証明書が証明書失効リストに含まれている場合または期限切れの場合、BizTalk Server はメッセージの暗号化を解除せずに中断します。</span><span class="sxs-lookup"><span data-stu-id="971df-125">If so, BizTalk Server will not decrypt the message, but will suspend it.</span></span> <span data-ttu-id="971df-126">このプロパティをオフにした場合、この確認は行われません。</span><span class="sxs-lookup"><span data-stu-id="971df-126">If this property is cleared, BizTalk Server will not perform this check.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="971df-127">証明書失効リストを取得および検索する場合には遅延が生じます。</span><span class="sxs-lookup"><span data-stu-id="971df-127">There is a latency involved with retrieving and searching the certificate revocation list.</span></span>  
  
8.  <span data-ttu-id="971df-128">選択、**内で重複するメッセージを確認**受信メッセージが重複するのかどうかを判断する チェック ボックスが以前にメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="971df-128">Select the **Check for duplicate messages within** check box to determine if the incoming message is a duplicate of previously received messages.</span></span>  
  
     <span data-ttu-id="971df-129">オンにした場合、**内で重複するメッセージを確認**プロパティ、設定、**日数**かを確認するときに使用する以前に受信したメッセージの範囲を示すプロパティを複製以外の場合は、をチェック**重複メッセージを中断**重複メッセージを中断することを示すプロパティです。</span><span class="sxs-lookup"><span data-stu-id="971df-129">If you checked the **Check for duplicate messages within** property, set the **days** property to indicate the span of previously received messages to use when checking for duplicates; check the **Suspend duplicate messages** property to indicate that duplicate messages should be suspended.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="971df-130">**AS2-から**と**AS2-に**フィールドを使用して、メッセージが重複しているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="971df-130">The **AS2-From** and **AS2-To** fields are used to determine if a message is a duplicate.</span></span> <span data-ttu-id="971df-131">メッセージのこれらのフィールドに含まれている値が、受信済みメッセージと同じである場合、他のヘッダーまたはペイロードが異なっている場合でも、そのメッセージは重複しているとしてマークされます。</span><span class="sxs-lookup"><span data-stu-id="971df-131">If the message contains the same values for these fields as a previously received message, it will be marked as duplicate even if the other headers or the payload is different.</span></span>  
  
9. <span data-ttu-id="971df-132">をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="971df-132">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="971df-133">参照</span><span class="sxs-lookup"><span data-stu-id="971df-133">See Also</span></span>  
 [<span data-ttu-id="971df-134">AS2 アグリーメント プロパティの構成</span><span class="sxs-lookup"><span data-stu-id="971df-134">Configuring AS2 Agreement Properties</span></span>](../core/configuring-as2-agreement-properties.md)