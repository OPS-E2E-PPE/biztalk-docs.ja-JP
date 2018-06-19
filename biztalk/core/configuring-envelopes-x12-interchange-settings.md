---
title: エンベロープ (X12 インターチェンジの設定) の構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4fade73-14cf-475c-81b5-6102c75db991
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf4f88ee1e5d786367c1a4bc0f5b2404fd5c1a37
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233418"
---
# <a name="configuring-envelopes-x12-interchange-settings"></a><span data-ttu-id="52fb3-102">エンベロープの構成 (X12 インターチェンジの設定)</span><span class="sxs-lookup"><span data-stu-id="52fb3-102">Configuring Envelopes (X12-Interchange Settings)</span></span>
<span data-ttu-id="52fb3-103">X12 インターチェンジのエンベロープの生成の設定は、受信側パーティに送信する X12 エンコード インターチェンジのエンベロープを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でどのように生成するかを定義します。</span><span class="sxs-lookup"><span data-stu-id="52fb3-103">X12 interchange envelope generation settings define how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generates the envelope of an X12-encoded interchange to be sent to the receiving party.</span></span> <span data-ttu-id="52fb3-104">ここでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がパーティに送信する X12 エンコード インターチェンジの ISA セグメントをどのように生成するかを定義します。</span><span class="sxs-lookup"><span data-stu-id="52fb3-104">In this section, you define how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generates the ISA segment for an X12-encoded interchange that it sends to the party.</span></span> <span data-ttu-id="52fb3-105">ISA セグメントは、X12 エンコード インターチェンジのインターチェンジ制御ヘッダーです。</span><span class="sxs-lookup"><span data-stu-id="52fb3-105">An ISA segment is the interchange control header for an X12-encoded interchange.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="52fb3-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイムでは、英数字の ISA フィールドの長さは固定されています。</span><span class="sxs-lookup"><span data-stu-id="52fb3-106">For the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime, the length of alphanumeric ISA fields is fixed.</span></span> <span data-ttu-id="52fb3-107">ただしの場合は、[!INCLUDE[TPM](../includes/tpm-md.md)]ユーザー インターフェイスでは、英数字の ISA フィールドの 1 つの文字を入力することがあります。</span><span class="sxs-lookup"><span data-stu-id="52fb3-107">However, for the [!INCLUDE[TPM](../includes/tpm-md.md)] user interface, you may enter a single character for an alphanumeric ISA field.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="52fb3-108">標準要件に準拠するための末尾の空白文字でこれらのフィールドが整数です。</span><span class="sxs-lookup"><span data-stu-id="52fb3-108"> will pad these fields with trailing space characters to ensure compliance with standards requirements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="52fb3-109">ここで説明する設定は、HIPAA インターチェンジ エンベロープの生成にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="52fb3-109">The settings described here also apply to HIPAA interchange envelope generation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="52fb3-110">オフにした場合のこのページですべてのプロパティは無効、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する**チェック ボックスを作成するパーティを作成するときに、アグリーメント。</span><span class="sxs-lookup"><span data-stu-id="52fb3-110">All the properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  <span data-ttu-id="52fb3-111">プロパティが無効になるのは、パーティから受信中のインターチェンジのプロパティに対応する一方向のアグリーメント タブ上のみです。</span><span class="sxs-lookup"><span data-stu-id="52fb3-111">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="52fb3-112">たとえば、2 つのパーティのパーティ A とパーティ B を作成して、チェック ボックスをオフにしたパーティ A、に対して、上記のプロパティの無効になりますで、**パーティ A にパーティ B]-> [** 一方向アグリーメント タブです。</span><span class="sxs-lookup"><span data-stu-id="52fb3-112">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="52fb3-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="52fb3-113">Prerequisites</span></span>  
 <span data-ttu-id="52fb3-114">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="52fb3-114">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-define-the-envelope"></a><span data-ttu-id="52fb3-115">エンベロープを定義するには</span><span class="sxs-lookup"><span data-stu-id="52fb3-115">To define the envelope</span></span>  
  
1.  <span data-ttu-id="52fb3-116">X12 エンコード アグリーメント」の説明に従って作成[全般設定を構成する (X12)](../core/configuring-general-settings-x12.md)です。</span><span class="sxs-lookup"><span data-stu-id="52fb3-116">Create an X12 encoding agreement as described in [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span> <span data-ttu-id="52fb3-117">既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="52fb3-117">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="52fb3-118">一方向アグリーメント タブの下にある**インターチェンジの設定**セクションで、**エンベロープ**です。</span><span class="sxs-lookup"><span data-stu-id="52fb3-118">On a one-way agreement tab, under **Interchange Settings** section, click **Envelopes**.</span></span>  
  
3.  <span data-ttu-id="52fb3-119">**ISA11 の使用法**、保持**標準識別子**繰り返し区切り記号の代わりに標準識別子を指定し、ドロップダウン リストから標準識別子の値を選択することを選択します。</span><span class="sxs-lookup"><span data-stu-id="52fb3-119">Under **ISA11 usage**, keep **Standard identifier** selected to specify a standard identifier instead of a repetition separator, and then select a value for the standard identifier from the drop-down list.</span></span> <span data-ttu-id="52fb3-120">選択**繰り返し区切り記号**を標準の識別子ではなく繰り返し区切り記号を指定し、繰り返し区切り記号として単一の文字を入力します。</span><span class="sxs-lookup"><span data-stu-id="52fb3-120">Select **Repetition separator** to specify a repetition separator instead of a standard identifier, and then enter a single character for the repetition separator.</span></span> <span data-ttu-id="52fb3-121">繰り返し区切り記号は、トランザクション セット内で繰り返すセグメントを区切るために使用されるもので、ASCII 文字セット内の値のみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="52fb3-121">The repetition separator, which is used to separate segments that repeat within a transaction set, is limited to the values in the ASCII character set.</span></span>  
  
4.  <span data-ttu-id="52fb3-122">**制御バージョン番号 (ISA12)**、X12 で使用される標準のバージョンを選択して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]送信インターチェンジを生成するためです。</span><span class="sxs-lookup"><span data-stu-id="52fb3-122">For **Control version number (ISA12)**, select the version of the X12 standard to be used by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for generating an outgoing interchange.</span></span>  
  
5.  <span data-ttu-id="52fb3-123">**使用状況インジケーター (ISA15)**、インターチェンジがによって生成されたかどうかを示すために [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]情報、実稼働データ、またはテスト データです。</span><span class="sxs-lookup"><span data-stu-id="52fb3-123">For **Usage indicator (ISA15)**, select to indicate whether an interchange generated by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is information, production data, or test data.</span></span>  
  
6.  <span data-ttu-id="52fb3-124">をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="52fb3-124">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52fb3-125">参照</span><span class="sxs-lookup"><span data-stu-id="52fb3-125">See Also</span></span>  
 [<span data-ttu-id="52fb3-126">(X12) インターチェンジの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="52fb3-126">Configuring Interchange Settings (X12)</span></span>](../core/configuring-interchange-settings-x12.md)