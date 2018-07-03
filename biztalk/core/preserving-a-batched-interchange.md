---
title: バッチ インターチェンジの保存 |Microsoft Docs
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
ms.openlocfilehash: 887995e9a44996c57da9e36bec1c5ec3edc1cc7b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993491"
---
# <a name="preserving-a-batched-interchange"></a><span data-ttu-id="d7f78-102">バッチ インターチェンジの保存</span><span class="sxs-lookup"><span data-stu-id="d7f78-102">Preserving a Batched Interchange</span></span>
<span data-ttu-id="d7f78-103">このトピックでは、バッチ EDI インターチェンジのトランザクション セットを分割せずに、インターチェンジを 1 つのドキュメントとして処理するアグリーメントの構成方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d7f78-103">This topic describes how to configure an agreement for processing a batched EDI interchange as a single document without splitting the transaction sets from the interchange.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d7f78-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="d7f78-104">Prerequisites</span></span>  
 <span data-ttu-id="d7f78-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7f78-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-the-receiving-and-sending-of-a-preserved-batch"></a><span data-ttu-id="d7f78-106">保存されたバッチの送受信を構成するには</span><span class="sxs-lookup"><span data-stu-id="d7f78-106">To configure the receiving and sending of a preserved batch</span></span>  
  
1. <span data-ttu-id="d7f78-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして、**パーティ**ノード。</span><span class="sxs-lookup"><span data-stu-id="d7f78-107">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click the **Parties** node.</span></span> <span data-ttu-id="d7f78-108">**パーティとビジネス プロファイル** ページで、受信したバッチ インターチェンジを解決するアグリーメントのパーティをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7f78-108">In the **Parties and Business Profiles** page, click the party that has the agreement that will resolve to the incoming batched interchange.</span></span> <span data-ttu-id="d7f78-109">**契約**セクション、ページのアグリーメントを右クリックし、をクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="d7f78-109">In the **Agreement** section of the page, right-click the agreement and click **Properties**.</span></span> <span data-ttu-id="d7f78-110">**アグリーメントのプロパティ**ダイアログ ボックスの一方向アグリーメント タブ (受信のバッチ インターチェンジが解決先) で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d7f78-110">In the **Agreement Properties** dialog box, in the one-way agreement tab (to which the inbound batched interchange will resolve), do the following:</span></span>  
  
   1.  <span data-ttu-id="d7f78-111">**識別子** ページで、ISA5、ISA6、ISA7、および ISA8 の値を入力の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="d7f78-111">In the **Identifiers** page, enter the values for enter values for ISA5, ISA6, ISA7, and ISA8.</span></span> <span data-ttu-id="d7f78-112">受信したバッチ処理インターチェンジがこのアグリーメントに解決されるように、正しい値を入力してください。</span><span class="sxs-lookup"><span data-stu-id="d7f78-112">Make sure you enter the correct values so that the incoming batched interchange resolves to this agreement.</span></span>  
  
   2.  <span data-ttu-id="d7f78-113">**ローカル ホスト設定**ページ (**インターチェンジの設定**) 下で、**受信者の設定**セクションの**受信バッチ処理オプション**、1 つに、次のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="d7f78-113">In the **Local Host Settings** page (under **Interchange Settings**), under **Receiver’s Settings** section, for the **Inbound batch processing option**, select one the following options:</span></span>  
  
       -   <span data-ttu-id="d7f78-114">**インターチェンジの保存 - エラーでインターチェンジを中断**– BizTalk Server がままにするインターチェンジ、バッチ インターチェンジ全体に対して XML ドキュメントを作成するかを指定するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="d7f78-114">**Preserve Interchange - suspend Interchange on Error** – Select this option to specify that BizTalk Server should leave the interchange intact, creating an XML document for the entire batched interchange.</span></span> <span data-ttu-id="d7f78-115">このオプションを使用すると、インターチェンジ内の 1 つまたは複数のトランザクション セットが検証に失敗した場合に、BizTalk Server がインターチェンジ全体を保留するようになります。</span><span class="sxs-lookup"><span data-stu-id="d7f78-115">With this option, if one or more transaction sets in the interchange fail validation, BizTalk Server will suspend the entire interchange.</span></span>  
  
       -   <span data-ttu-id="d7f78-116">**インターチェンジの保存 - エラーのトランザクション セットを中断**– BizTalk Server がままにするインターチェンジ、バッチ インターチェンジ全体に対して XML ドキュメントを作成するかを指定するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="d7f78-116">**Preserve Interchange - suspend Transaction Sets on Error** – Select this option to specify that BizTalk Server should leave the interchange intact, creating an XML document for the entire batched interchange.</span></span> <span data-ttu-id="d7f78-117">このオプションで、インターチェンジ内の 1 つまたは複数のトランザクション セットが失敗した BizTalk Server がその他のすべてのトランザクション セットの処理を継続しながら、トランザクション セットのみを中断します。</span><span class="sxs-lookup"><span data-stu-id="d7f78-117">With this option, if one or more transaction sets in the interchange fail validation, BizTalk Server will suspend only those transaction sets, while continuing to process all other transaction sets.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="d7f78-118">上記 2 つのオプションのいずれか 1 つをオンにした場合、インターチェンジ、グループ、およびトランザクション セット セグメントのプロパティ (BizTalk Server で送信インターチェンジの ISA、GS、ST のヘッダーをどのように作成するかを決定します) は適用されません。</span><span class="sxs-lookup"><span data-stu-id="d7f78-118">If you select either of the two options mentioned above, the interchange, group, and transaction set segment properties (which determine how BizTalk Server will create the ISA, GS, and ST headers of an outgoing interchange) do not apply.</span></span> <span data-ttu-id="d7f78-119">保存されるインターチェンジに含まれているインターチェンジ、グループ、およびトランザクション セットの各ヘッダーは、送信パイプラインがインターチェンジの送信処理を行うときに保持されます。</span><span class="sxs-lookup"><span data-stu-id="d7f78-119">The interchange, group, and transaction-set headers that exist in the interchange that is being preserved are retained when the send pipeline processes it for sending.</span></span> <span data-ttu-id="d7f78-120">しかし、アグリーメントでインターチェンジに指定された値を使用する場合、`EDI.PopulateInterchangeValues` コンテクスト プロパティを true に設定します。</span><span class="sxs-lookup"><span data-stu-id="d7f78-120">However, if you do want to use the values specified for the interchange in the agreement, set the `EDI.PopulateInterchangeValues` context property to true.</span></span>  
  
2. <span data-ttu-id="d7f78-121">保存されたバッチの Visual Studio プロジェクトを次のように作成します。</span><span class="sxs-lookup"><span data-stu-id="d7f78-121">Create a Visual Studio project for the preserved batch as follows:</span></span>  
  
   1. <span data-ttu-id="d7f78-122">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、BizTalk プロジェクトを作成し、バッチ内のすべてのメッセージ用のスキーマを追加します。</span><span class="sxs-lookup"><span data-stu-id="d7f78-122">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], create a BizTalk project and add the schemas for all the messages within the batch.</span></span>  
  
   2. <span data-ttu-id="d7f78-123">プロジェクトをビルドし、配置します。</span><span class="sxs-lookup"><span data-stu-id="d7f78-123">Build and deploy the project.</span></span>  
  
3. <span data-ttu-id="d7f78-124">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、保存されたバッチを送信するための送信ポートを次のように作成します。</span><span class="sxs-lookup"><span data-stu-id="d7f78-124">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, create a send port to send preserved batches as follows:</span></span>  
  
   1.  <span data-ttu-id="d7f78-125">送信パイプラインを設定**EdiSend**または**AS2EdiSend**します。</span><span class="sxs-lookup"><span data-stu-id="d7f78-125">Set the send pipeline to **EdiSend** or **AS2EdiSend**.</span></span>  
  
   2.  <span data-ttu-id="d7f78-126">送信ポートのフィルターをコンテキスト プロパティ `EDI.ReuseEnvelope == True` に設定します。</span><span class="sxs-lookup"><span data-stu-id="d7f78-126">Set the filter of the send port to the context property `EDI.ReuseEnvelope == True`.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="d7f78-127">このフィルターを設定すると、保存されているすべてのバッチ インターチェンジに送信ポートがサブスクライブされます。</span><span class="sxs-lookup"><span data-stu-id="d7f78-127">Setting this filter ensures that the send port will subscribe to all batched interchanges that are preserved.</span></span> <span data-ttu-id="d7f78-128">EdiReceive 受信パイプラインは、インターチェンジを保存されたインターチェンジとして識別するために、コンテキスト プロパティ `EDI.ReuseEnvelope` を昇格させます。</span><span class="sxs-lookup"><span data-stu-id="d7f78-128">The EdiReceive receive pipeline promotes the context property `EDI.ReuseEnvelope` to identify the interchange as preserved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7f78-129">参照</span><span class="sxs-lookup"><span data-stu-id="d7f78-129">See Also</span></span>  
 <span data-ttu-id="d7f78-130">[EDI バッチの構成](../core/configuring-edi-batches.md) </span><span class="sxs-lookup"><span data-stu-id="d7f78-130">[Configuring EDI Batches](../core/configuring-edi-batches.md) </span></span>  
 [<span data-ttu-id="d7f78-131">送信ポートを作成する方法</span><span class="sxs-lookup"><span data-stu-id="d7f78-131">How to Create a Send Port</span></span>](../core/how-to-create-a-send-port2.md)