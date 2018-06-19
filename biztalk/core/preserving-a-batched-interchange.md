---
title: バッチ インターチェンジの保存 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 907e07f3-1f3e-485e-a82d-b28eb7658e0a
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e7ea2bdef1fe2b2c3db92421d610b0b889e0460
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22265346"
---
# <a name="preserving-a-batched-interchange"></a><span data-ttu-id="59776-102">バッチ インターチェンジの保存</span><span class="sxs-lookup"><span data-stu-id="59776-102">Preserving a Batched Interchange</span></span>
<span data-ttu-id="59776-103">このトピックでは、バッチ EDI インターチェンジのトランザクション セットを分割せずに、インターチェンジを 1 つのドキュメントとして処理するアグリーメントの構成方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="59776-103">This topic describes how to configure an agreement for processing a batched EDI interchange as a single document without splitting the transaction sets from the interchange.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="59776-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="59776-104">Prerequisites</span></span>  
 <span data-ttu-id="59776-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="59776-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-the-receiving-and-sending-of-a-preserved-batch"></a><span data-ttu-id="59776-106">保存されたバッチの送受信を構成するには</span><span class="sxs-lookup"><span data-stu-id="59776-106">To configure the receiving and sending of a preserved batch</span></span>  
  
1.  <span data-ttu-id="59776-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして、**パーティ**ノード。</span><span class="sxs-lookup"><span data-stu-id="59776-107">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click the **Parties** node.</span></span> <span data-ttu-id="59776-108">**パーティとビジネス プロファイル** ページで、そのパーティが受信したバッチ インターチェンジに解決されるアグリーメントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="59776-108">In the **Parties and Business Profiles** page, click the party that has the agreement that will resolve to the incoming batched interchange.</span></span> <span data-ttu-id="59776-109">**アグリーメント**セクションで、ページのアグリーメントを右クリックし、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="59776-109">In the **Agreement** section of the page, right-click the agreement and click **Properties**.</span></span> <span data-ttu-id="59776-110">**アグリーメントのプロパティ**ダイアログ ボックスで、(受信のバッチ インターチェンジが解決先) の一方向アグリーメント タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="59776-110">In the **Agreement Properties** dialog box, in the one-way agreement tab (to which the inbound batched interchange will resolve), do the following:</span></span>  
  
    1.  <span data-ttu-id="59776-111">**識別子** ページで、ISA5、ISA6、ISA7、および ISA8 の値を入力の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="59776-111">In the **Identifiers** page, enter the values for enter values for ISA5, ISA6, ISA7, and ISA8.</span></span> <span data-ttu-id="59776-112">受信したバッチ処理インターチェンジがこのアグリーメントに解決されるように、正しい値を入力してください。</span><span class="sxs-lookup"><span data-stu-id="59776-112">Make sure you enter the correct values so that the incoming batched interchange resolves to this agreement.</span></span>  
  
    2.  <span data-ttu-id="59776-113">**ローカル ホストの設定**ページ (**インターチェンジの設定**) **受信者の設定** セクションの**受信バッチ処理オプション**、1 つに、次のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="59776-113">In the **Local Host Settings** page (under **Interchange Settings**), under **Receiver’s Settings** section, for the **Inbound batch processing option**, select one the following options:</span></span>  
  
        -   <span data-ttu-id="59776-114">**インターチェンジの保存 - エラーでインターチェンジを中断**– こと BizTalk Server は、インターチェンジはそのまま残す、バッチ インターチェンジ全体に対して XML ドキュメントを作成するを指定するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="59776-114">**Preserve Interchange - suspend Interchange on Error** – Select this option to specify that BizTalk Server should leave the interchange intact, creating an XML document for the entire batched interchange.</span></span> <span data-ttu-id="59776-115">このオプションを使用すると、インターチェンジ内の 1 つまたは複数のトランザクション セットが検証に失敗した場合に、BizTalk Server がインターチェンジ全体を保留するようになります。</span><span class="sxs-lookup"><span data-stu-id="59776-115">With this option, if one or more transaction sets in the interchange fail validation, BizTalk Server will suspend the entire interchange.</span></span>  
  
        -   <span data-ttu-id="59776-116">**インターチェンジの保存 - エラーのトランザクション セットを中断**– こと BizTalk Server は、インターチェンジはそのまま残す、バッチ インターチェンジ全体に対して XML ドキュメントを作成するを指定するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="59776-116">**Preserve Interchange - suspend Transaction Sets on Error** – Select this option to specify that BizTalk Server should leave the interchange intact, creating an XML document for the entire batched interchange.</span></span> <span data-ttu-id="59776-117">このオプションを使用して、インターチェンジ内の 1 つまたは複数のトランザクション セットには、検証が失敗した場合に BizTalk Server は中断そのトランザクション セットのみ、その他のすべてのトランザクション セットの処理を継続します。</span><span class="sxs-lookup"><span data-stu-id="59776-117">With this option, if one or more transaction sets in the interchange fail validation, BizTalk Server will suspend only those transaction sets, while continuing to process all other transaction sets.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="59776-118">上記 2 つのオプションのいずれか 1 つをオンにした場合、インターチェンジ、グループ、およびトランザクション セット セグメントのプロパティ (BizTalk Server で送信インターチェンジの ISA、GS、ST のヘッダーをどのように作成するかを決定します) は適用されません。</span><span class="sxs-lookup"><span data-stu-id="59776-118">If you select either of the two options mentioned above, the interchange, group, and transaction set segment properties (which determine how BizTalk Server will create the ISA, GS, and ST headers of an outgoing interchange) do not apply.</span></span> <span data-ttu-id="59776-119">保存されるインターチェンジに含まれているインターチェンジ、グループ、およびトランザクション セットの各ヘッダーは、送信パイプラインがインターチェンジの送信処理を行うときに保持されます。</span><span class="sxs-lookup"><span data-stu-id="59776-119">The interchange, group, and transaction-set headers that exist in the interchange that is being preserved are retained when the send pipeline processes it for sending.</span></span> <span data-ttu-id="59776-120">しかし、アグリーメントでインターチェンジに指定された値を使用する場合、`EDI.PopulateInterchangeValues` コンテクスト プロパティを true に設定します。</span><span class="sxs-lookup"><span data-stu-id="59776-120">However, if you do want to use the values specified for the interchange in the agreement, set the `EDI.PopulateInterchangeValues` context property to true.</span></span>  
  
2.  <span data-ttu-id="59776-121">保存されたバッチの Visual Studio プロジェクトを次のように作成します。</span><span class="sxs-lookup"><span data-stu-id="59776-121">Create a Visual Studio project for the preserved batch as follows:</span></span>  
  
    1.  <span data-ttu-id="59776-122">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、BizTalk プロジェクトを作成し、バッチ内のすべてのメッセージ用のスキーマを追加します。</span><span class="sxs-lookup"><span data-stu-id="59776-122">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], create a BizTalk project and add the schemas for all the messages within the batch.</span></span>  
  
    2.  <span data-ttu-id="59776-123">プロジェクトをビルドし、配置します。</span><span class="sxs-lookup"><span data-stu-id="59776-123">Build and deploy the project.</span></span>  
  
3.  <span data-ttu-id="59776-124">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、保存されたバッチを送信するための送信ポートを次のように作成します。</span><span class="sxs-lookup"><span data-stu-id="59776-124">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, create a send port to send preserved batches as follows:</span></span>  
  
    1.  <span data-ttu-id="59776-125">送信パイプラインに設定**EdiSend**または**AS2EdiSend**です。</span><span class="sxs-lookup"><span data-stu-id="59776-125">Set the send pipeline to **EdiSend** or **AS2EdiSend**.</span></span>  
  
    2.  <span data-ttu-id="59776-126">送信ポートのフィルターをコンテキスト プロパティ `EDI.ReuseEnvelope == True` に設定します。</span><span class="sxs-lookup"><span data-stu-id="59776-126">Set the filter of the send port to the context property `EDI.ReuseEnvelope == True`.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="59776-127">このフィルターを設定すると、保存されているすべてのバッチ インターチェンジに送信ポートがサブスクライブされます。</span><span class="sxs-lookup"><span data-stu-id="59776-127">Setting this filter ensures that the send port will subscribe to all batched interchanges that are preserved.</span></span> <span data-ttu-id="59776-128">EdiReceive 受信パイプラインは、インターチェンジを保存されたインターチェンジとして識別するために、コンテキスト プロパティ `EDI.ReuseEnvelope` を昇格させます。</span><span class="sxs-lookup"><span data-stu-id="59776-128">The EdiReceive receive pipeline promotes the context property `EDI.ReuseEnvelope` to identify the interchange as preserved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59776-129">参照</span><span class="sxs-lookup"><span data-stu-id="59776-129">See Also</span></span>  
 <span data-ttu-id="59776-130">[EDI バッチの構成](../core/configuring-edi-batches.md) </span><span class="sxs-lookup"><span data-stu-id="59776-130">[Configuring EDI Batches](../core/configuring-edi-batches.md) </span></span>  
 [<span data-ttu-id="59776-131">送信ポートを作成する方法</span><span class="sxs-lookup"><span data-stu-id="59776-131">How to Create a Send Port</span></span>](../core/how-to-create-a-send-port2.md)