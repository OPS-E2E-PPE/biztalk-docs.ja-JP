---
title: バッチ インターチェンジの分割 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e67bef19-77fb-47a9-88f3-ee20043b3691
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1cb3c6c912985a81a2265afa11bebc636381c5a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024064"
---
# <a name="splitting-a-batched-interchange"></a><span data-ttu-id="10995-102">バッチ インターチェンジの分割</span><span class="sxs-lookup"><span data-stu-id="10995-102">Splitting a Batched Interchange</span></span>
<span data-ttu-id="10995-103">このトピックでは、バッチ EDI インターチェンジのトランザクション セットを分割して、インターチェンジを処理するアグリーメントを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="10995-103">This topic describes how to configure an agreement for processing a batched EDI interchange by splitting the transaction sets from the interchange.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="10995-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="10995-104">Prerequisites</span></span>  
 <span data-ttu-id="10995-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="10995-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-receive-a-split-edi-interchange"></a><span data-ttu-id="10995-106">分割された EDI インターチェンジを受信するには</span><span class="sxs-lookup"><span data-stu-id="10995-106">To receive a split EDI interchange</span></span>  
  
1. <span data-ttu-id="10995-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして、**パーティ**ノード。</span><span class="sxs-lookup"><span data-stu-id="10995-107">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click the **Parties** node.</span></span> <span data-ttu-id="10995-108">**パーティとビジネス プロファイル** ページで、受信したバッチ インターチェンジを解決するアグリーメントのパーティをクリックします。</span><span class="sxs-lookup"><span data-stu-id="10995-108">In the **Parties and Business Profiles** page, click the party that has the agreement that will resolve to the incoming batched interchange.</span></span> <span data-ttu-id="10995-109">**契約**セクション、ページのアグリーメントを右クリックし、をクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="10995-109">In the **Agreement** section of the page, right-click the agreement and click **Properties**.</span></span> <span data-ttu-id="10995-110">**アグリーメントのプロパティ**ダイアログ ボックスの一方向アグリーメント タブ (受信のバッチ インターチェンジが解決先) で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="10995-110">In the **Agreement Properties** dialog box, in the one-way agreement tab (to which the inbound batched interchange will resolve), do the following:</span></span>  
  
   1.  <span data-ttu-id="10995-111">**識別子** ページを受信したバッチ インターチェンジがこのアグリーメントに解決できるように、適切な値を入力するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="10995-111">In the **Identifiers** page, make sure you enter the correct values so that the incoming batched interchange resolves to this agreement.</span></span>  
  
       -   <span data-ttu-id="10995-112">場合に**X12**: 設定の ISA5、ISA6、ISA7、ISA8、します。</span><span class="sxs-lookup"><span data-stu-id="10995-112">In case of **X12**: Set ISA5, ISA6, ISA7, and ISA8.</span></span>  
  
       -   <span data-ttu-id="10995-113">場合に**Edifact**: 設定 UNB2.1、UNB2.2、UNB3.1、および [unb3.2]。</span><span class="sxs-lookup"><span data-stu-id="10995-113">In case of **Edifact**: Set UNB2.1, UNB2.2, UNB3.1, and UNB3.2.</span></span>  
  
   2.  <span data-ttu-id="10995-114">**ローカル ホスト設定**ページ (**インターチェンジの設定**) 下で、**受信者の設定**セクションの**受信バッチ処理オプション**、1 つに、次のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="10995-114">In the **Local Host Settings** page (under **Interchange Settings**), under **Receiver’s Settings** section, for the **Inbound batch processing option**, select one the following options:</span></span>  
  
       -   <span data-ttu-id="10995-115">**トランザクション セットとして分割されたインターチェンジがエラーのトランザクション セットを中断**– BizTalk Server がインターチェンジを個別の XML ドキュメントの各トランザクション セットを解析する必要がありますを指定するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="10995-115">**Split Interchange as Transaction Sets - suspend Transaction Sets on Error** – Select this option to specify that BizTalk Server should parse each transaction set in an interchange into a separate XML document.</span></span> <span data-ttu-id="10995-116">こうすることによって、適切なエンベロープがトランザクション セットに適用され、トランザクション セット ドキュメントがメッセージ ボックスにルーティングされるようになります。</span><span class="sxs-lookup"><span data-stu-id="10995-116">BizTalk Server will then apply the appropriate envelope to the transaction set and route the transaction set document to the MessageBox.</span></span> <span data-ttu-id="10995-117">このオプションを使用すると、インターチェンジ内の 1 つまたは複数のトランザクション セットが検証に失敗した場合に、BizTalk Server はこれらのトランザクション セットだけを中断します。</span><span class="sxs-lookup"><span data-stu-id="10995-117">With this option, if one or more transaction sets in the interchange fail validation, BizTalk Server will suspend only those transaction sets.</span></span>  
  
       -   <span data-ttu-id="10995-118">**トランザクション セットとして分割されたインターチェンジがエラーでインターチェンジを中断**– BizTalk Server がインターチェンジを個別の XML ドキュメントの各トランザクション セットを解析する必要がありますを指定するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="10995-118">**Split Interchange as Transaction Sets - suspend Interchange on Error** – Select this option to specify that BizTalk Server should parse each transaction set in an interchange into a separate XML document.</span></span> <span data-ttu-id="10995-119">こうすることによって、適切なエンベロープがトランザクション セットに適用され、トランザクション セット ドキュメントがメッセージ ボックスにルーティングされるようになります。</span><span class="sxs-lookup"><span data-stu-id="10995-119">BizTalk Server will then apply the appropriate envelope to the transaction set and route the transaction set document to the MessageBox.</span></span> <span data-ttu-id="10995-120">このオプションを使用すると、インターチェンジ内の 1 つまたは複数のトランザクション セットが検証に失敗した場合に、BizTalk Server がインターチェンジ全体を保留するようになります。</span><span class="sxs-lookup"><span data-stu-id="10995-120">With this option, if one or more transaction sets in the interchange fail validation, BizTalk Server will suspend the entire interchange.</span></span>  
  
2. <span data-ttu-id="10995-121">保存されたバッチの Visual Studio プロジェクトを次のように作成します。</span><span class="sxs-lookup"><span data-stu-id="10995-121">Create a Visual Studio project for the preserved batch as follows:</span></span>  
  
   1. <span data-ttu-id="10995-122">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、BizTalk プロジェクトを作成し、バッチ内のすべてのメッセージ用のスキーマを追加します。</span><span class="sxs-lookup"><span data-stu-id="10995-122">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], create a BizTalk project and add the schemas for all the messages within the batch.</span></span>  
  
   2. <span data-ttu-id="10995-123">プロジェクトをビルドし、配置します。</span><span class="sxs-lookup"><span data-stu-id="10995-123">Build and deploy the project.</span></span>  
  
3. <span data-ttu-id="10995-124">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、分割されたバッチを送信するための送信ポートを次のように作成します。</span><span class="sxs-lookup"><span data-stu-id="10995-124">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, create a send port to send split batches as follows:</span></span>  
  
   1.  <span data-ttu-id="10995-125">送信パイプラインを設定**EdiSend**または**AS2EdiSend**します。</span><span class="sxs-lookup"><span data-stu-id="10995-125">Set the send pipeline to **EdiSend** or **AS2EdiSend**.</span></span>  
  
   2.  <span data-ttu-id="10995-126">送信ポートのフィルターを、各トランザクション セットを取得するのに必要な値に設定します。たとえば、BTS.MessageType に設定します。</span><span class="sxs-lookup"><span data-stu-id="10995-126">Set the filter of the send port to the value required to pick up each transaction set, for example, to BTS.MessageType.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10995-127">参照</span><span class="sxs-lookup"><span data-stu-id="10995-127">See Also</span></span>  
 <span data-ttu-id="10995-128">[EDI バッチの構成](../core/configuring-edi-batches.md) </span><span class="sxs-lookup"><span data-stu-id="10995-128">[Configuring EDI Batches](../core/configuring-edi-batches.md) </span></span>  
 [<span data-ttu-id="10995-129">送信ポートを作成する方法</span><span class="sxs-lookup"><span data-stu-id="10995-129">How to Create a Send Port</span></span>](../core/how-to-create-a-send-port2.md)