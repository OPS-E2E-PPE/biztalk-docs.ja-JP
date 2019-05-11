---
title: 全般的なローカル ホスト設定 (AS2) の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 980daac2-8387-44cc-ae55-38639f759668
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b990a44c9599ff725bdd19f7bfdd8286ec11487d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391111"
---
# <a name="configuring-general-local-host-settings-as2"></a><span data-ttu-id="cfebd-102">全般的なローカル ホスト設定の構成 (AS2)</span><span class="sxs-lookup"><span data-stu-id="cfebd-102">Configuring General Local Host Settings (AS2)</span></span>
<span data-ttu-id="cfebd-103">ローカル ホストの全般設定の一部として、AS2 メッセージとメッセージの AS2 ヘッダーの一部として、ファイル名を保持するかどうかのコンテンツの種類を指定できます。</span><span class="sxs-lookup"><span data-stu-id="cfebd-103">As part of the local host general settings, you can specify the content type of the AS2 messages and whether the file name is preserved as part of the AS2 message header.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cfebd-104">オフにした場合、このページで、すべてのプロパティが無効に、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェック ボックスを作成するパーティを作成するときに、契約です。</span><span class="sxs-lookup"><span data-stu-id="cfebd-104">All the properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  <span data-ttu-id="cfebd-105">プロパティが無効になるのは、パーティから受信中のインターチェンジのプロパティに対応する一方向のアグリーメント タブ上のみです。</span><span class="sxs-lookup"><span data-stu-id="cfebd-105">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="cfebd-106">たとえば、2 つのパーティのパーティ A とパーティ B を作成するチェック ボックスをオフにしたパーティ A の場合は、上記のプロパティが無効になります、**パーティ A にパーティ B]-> [** 一方向アグリーメント タブ。</span><span class="sxs-lookup"><span data-stu-id="cfebd-106">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cfebd-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="cfebd-107">Prerequisites</span></span>  
 <span data-ttu-id="cfebd-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfebd-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-the-general-settings"></a><span data-ttu-id="cfebd-109">[全般] 設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="cfebd-109">To configure the general settings</span></span>  
  
1.  <span data-ttu-id="cfebd-110">AS2 契約の作成」の説明に従って[全般設定の構成 (AS2)](../core/configuring-general-settings-as2.md)します。</span><span class="sxs-lookup"><span data-stu-id="cfebd-110">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="cfebd-111">既存の AS2 アグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="cfebd-111">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="cfebd-112">一方向アグリーメント タブで、**ローカル ホスト設定**セクションで、**全般**します。</span><span class="sxs-lookup"><span data-stu-id="cfebd-112">On a one-way agreement tab, under **Local Host Settings** section, click **General**.</span></span>  
  
3.  <span data-ttu-id="cfebd-113">選択、**証明書失効リストの確認メッセージを送信する前に**送信メッセージの署名に使用される証明書を証明書失効リストに含まれているかどうかを判断する チェック ボックスを示すその it が失効、または有効期限の日付が渡されるかどうか。</span><span class="sxs-lookup"><span data-stu-id="cfebd-113">Select the **Check Certification Revocation List before sending the message** check box to determine whether the certificate to be used in signing an outgoing messages has been included in the Certification Revocation List, indicating that it has been revoked, or whether the expiration date has passed.</span></span> <span data-ttu-id="cfebd-114">そうである場合、BizTalk Server は、メッセージ暗号化は行われませんが、中断します。</span><span class="sxs-lookup"><span data-stu-id="cfebd-114">If so, BizTalk Server will not encrypt the message, but will suspend it.</span></span> <span data-ttu-id="cfebd-115">このプロパティをオフにした場合、この確認は行われません。</span><span class="sxs-lookup"><span data-stu-id="cfebd-115">If this property is cleared, BizTalk Server will not perform this check.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cfebd-116">証明書失効リストを取得および検索する場合には遅延が生じます。</span><span class="sxs-lookup"><span data-stu-id="cfebd-116">There is a latency involved with retrieving and searching the certificate revocation list.</span></span>  
  
4.  <span data-ttu-id="cfebd-117">**既定のコンテンツの種類**、送信 AS2 メッセージのパーティを使用する必要がある既定のコンテンツ タイプを選択します。</span><span class="sxs-lookup"><span data-stu-id="cfebd-117">For **Default content type**, select the default content type that the party must use for an outgoing AS2 message.</span></span> <span data-ttu-id="cfebd-118">場合、`ContentType`プロパティをこの値の設定が送信メッセージの生成に使用されます。 それ以外であること、メッセージのボディ部のコンテキストにおける設定**既定のコンテンツの種類**プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="cfebd-118">If the `ContentType` property is set in the context for a message body part, that setting is used to generate the outgoing message; otherwise, the value of this **Default content type** property is used.</span></span>  
  
5.  <span data-ttu-id="cfebd-119">選択、 **MIME ヘッダーでファイル名を送信**送信 AS2 メッセージの MIME ヘッダーの一部としてファイル名を送信する チェック ボックス。</span><span class="sxs-lookup"><span data-stu-id="cfebd-119">Select the **Transmit file name in MIME header** check box to send a file name as part of the MIME header for the outbound AS2 message.</span></span> <span data-ttu-id="cfebd-120">ファイル名を指定するには、次のように選択します。**ファイル名の指定**または**システム ファイル名を生成**します。</span><span class="sxs-lookup"><span data-stu-id="cfebd-120">To specify the file name, select **Specify file name** or **Have system generate file name**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cfebd-121">選択**システム ファイル名を生成**AS2 メッセージで送信される各添付ファイルのファイル名として新しい GUID 値が生成されます。</span><span class="sxs-lookup"><span data-stu-id="cfebd-121">Selecting **Have system generate file name** will generate a new GUID value as the file name of each attachment sent in the AS2 message.</span></span>  
  
6.  <span data-ttu-id="cfebd-122">選択した場合**ファイル名の指定**、内の文字列値またはコンテキスト プロパティを入力、**ファイル名の指定**フィールド。</span><span class="sxs-lookup"><span data-stu-id="cfebd-122">If you selected **Specify file name**, enter a string value or context property in the **Specify file name** field.</span></span> <span data-ttu-id="cfebd-123">有効にすることも**場合メッセージは中断コンテキスト プロパティ (%property% など)見つかりません。** 選択されているコンテキスト プロパティは、送信メッセージが存在しない場合、メッセージを中断します。</span><span class="sxs-lookup"><span data-stu-id="cfebd-123">You can also enable **Suspend message if context property (e.g. %property%) not found** to suspend the message if the selected context property does not exist for the outbound message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cfebd-124">コンテキスト プロパティを指定するには、プロパティ名に % 文字で囲みます。</span><span class="sxs-lookup"><span data-stu-id="cfebd-124">To specify a context-property, enclose the property name with the % character.</span></span> <span data-ttu-id="cfebd-125">たとえば、`%FILE.ReceivedFileName%` のようにします。</span><span class="sxs-lookup"><span data-stu-id="cfebd-125">For example, `%FILE.ReceivedFileName%`.</span></span>  
  
7.  <span data-ttu-id="cfebd-126">をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="cfebd-126">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfebd-127">参照</span><span class="sxs-lookup"><span data-stu-id="cfebd-127">See Also</span></span>  
 [<span data-ttu-id="cfebd-128">ローカル ホスト設定の構成 (AS2)</span><span class="sxs-lookup"><span data-stu-id="cfebd-128">Configuring Local Host Settings (AS2)</span></span>](../core/configuring-local-host-settings-as2.md)