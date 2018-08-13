---
title: オーケストレーションでコントラクトの型指定されたエラーを処理する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- typed fault contracts [orchestrations]
- WCF services, orchestrations
- orchestrations, typed fault contracts
- orchestrations, WCF services
ms.assetid: 5a1a7d22-b0ff-4d09-bebf-4995229784b0
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bc4226b0e8f3ea5ac025f0bb7234559a52104e7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967211"
---
# <a name="how-to-handle-typed-fault-contracts-in-orchestrations"></a><span data-ttu-id="64bf0-102">オーケストレーション内の型指定されたエラー コントラクトを処理する方法</span><span class="sxs-lookup"><span data-stu-id="64bf0-102">How to Handle Typed Fault Contracts in Orchestrations</span></span>
<span data-ttu-id="64bf0-103">このトピックでは、オーケストレーション内から WCF サービスを使用する際に、型指定されたエラー コントラクトを処理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="64bf0-103">This topic describes how to handle typed fault contracts when consuming WCF services from within orchestrations.</span></span> <span data-ttu-id="64bf0-104">オーケストレーションで型指定されたエラー例外を処理するために消費している WCF サービスがあります、 **FaultContractAttribute**サービス操作に適用されるは、エラーをスローしてを使用してそのため、 **FaultException**\<T\> T が任意の有効なデータ コントラクトまたは WCF サービスから型をシリアル化可能なをすることができます。</span><span class="sxs-lookup"><span data-stu-id="64bf0-104">To handle typed fault exceptions in orchestrations, the WCF services that you are consuming must have the **FaultContractAttribute** applied to the service operations; therefore, the faults can be thrown by using **FaultException**\<T\> where T can be any valid data contract or serializable type from the WCF services.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="64bf0-105">手順</span><span class="sxs-lookup"><span data-stu-id="64bf0-105">Procedures</span></span>  
  
#### <a name="to-handle-typed-fault-contracts-in-orchestrations"></a><span data-ttu-id="64bf0-106">オーケストレーション内の型指定されたエラー コントラクトを処理するには</span><span class="sxs-lookup"><span data-stu-id="64bf0-106">To handle typed fault contracts in orchestrations</span></span>  
  
1. <span data-ttu-id="64bf0-107">Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトをソリューション エクスプ ローラーでプロジェクトを右クリックし、をクリックして**追加**、 をクリックし、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="64bf0-107">In your Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, in Solution Explorer, right-click your project, click **Add**, and then click **Add Generated Items**.</span></span>  
  
2. <span data-ttu-id="64bf0-108">**生成した項目の追加 - \<** <em>プロジェクト名</em>**\>**  ダイアログ ボックスで、**テンプレート** セクションで、選択**Consume WCF サービス**、 をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="64bf0-108">In the **Add Generated Items - \<**<em>Project name</em>**\>** dialog box, in the **Templates** section, select **Consume WCF Service**, and then click **Add**.</span></span>  
  
3. <span data-ttu-id="64bf0-109">**BizTalk WCF サービス使用ウィザードへようこそ**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="64bf0-109">On the **Welcome to the BizTalk WCF Service Consuming Wizard** page, click **Next**.</span></span>  
  
4. <span data-ttu-id="64bf0-110">**メタデータ ソース**] ページで、[ **Metadata Exchange (MEX) エンドポイント**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="64bf0-110">On the **Metadata source** page, select **Metadata Exchange (MEX) endpoint**, and then click **Next**.</span></span>  
  
5. <span data-ttu-id="64bf0-111">**メタデータ エンドポイント**ページで、Ws-metadata Exchange または Http-get を通じてダウンロードのメタデータを提供する実行中のサービスの URL を指定 — たとえば、 http://localhost:8005 します。</span><span class="sxs-lookup"><span data-stu-id="64bf0-111">On the **Metadata Endpoint** page, specify the URL for the running service that provides metadata for download through WS-Metadata Exchange or Http-Get—for example, http://localhost:8005.</span></span> <span data-ttu-id="64bf0-112">URL からメタデータ ドキュメントを取得する次のようにクリックします。**取得**します。</span><span class="sxs-lookup"><span data-stu-id="64bf0-112">To get the metadata document from the URL, click **Get**.</span></span> <span data-ttu-id="64bf0-113">実行中のサービスには、基本認証スキームでユーザーの資格情報が必要とする場合にクリックします**編集**を開く、 **BizTalk WCF サービス使用ウィザード** ダイアログ ボックスのユーザー名を入力し、実行中のサービスにアクセスするときに使用するパスワード。</span><span class="sxs-lookup"><span data-stu-id="64bf0-113">If the running service requires a user credential with the basic authentication scheme, click **Edit** to open the **BizTalk WCF Service Consuming Wizard** dialog box in which you can supply the user name and password to use when accessing the running service.</span></span> <span data-ttu-id="64bf0-114">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64bf0-114">Click **Next**.</span></span>  
  
6. <span data-ttu-id="64bf0-115">**WCF サービス メタデータの概要のインポート**ページで、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="64bf0-115">On the **Import WCF Service Metadata Summary** page, review your settings.</span></span> <span data-ttu-id="64bf0-116">クリックすることができます**戻る**変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="64bf0-116">You can click **Back** to make any changes.</span></span> <span data-ttu-id="64bf0-117">クリックして**インポート**BizTalk アイテムと、WCF サービスを使用するために使用される型を作成します。</span><span class="sxs-lookup"><span data-stu-id="64bf0-117">Then click **Import** to create the BizTalk artifacts and types to be used for consuming the WCF service.</span></span>  
  
7. <span data-ttu-id="64bf0-118">**BizTalk WCF サービス使用ウィザードの完了**] ページで [**完了**します。</span><span class="sxs-lookup"><span data-stu-id="64bf0-118">On the **Completing the BizTalk WCF Service Consuming Wizard** page, click **Finish**.</span></span>  
  
8. <span data-ttu-id="64bf0-119">使用している WCF サービスが、次のエラー例外をスローするとします。</span><span class="sxs-lookup"><span data-stu-id="64bf0-119">Suppose that the WCF service that you are consuming throws the following fault exception:</span></span>  
  
   ```  
   throw new FaultException<MyOperationException>(divideException);  
   ```  
  
    <span data-ttu-id="64bf0-120">送信ポートでのエラー操作の種類のメッセージが必要ですが**MyOperationException**が WCF 応答メッセージには、エラー本文全体が含まれています。</span><span class="sxs-lookup"><span data-stu-id="64bf0-120">The fault operation on the send port expects a message of type **MyOperationException**, but the WCF response message contains the whole fault body.</span></span> <span data-ttu-id="64bf0-121">そのため、抽出する必要があります、 **MyOperationException**一部構成することによって、メッセージから、**受信 BizTalk メッセージ本文**トランスポートのプロパティ ダイアログ ボックスのオプション。</span><span class="sxs-lookup"><span data-stu-id="64bf0-121">Therefore, you need to extract the **MyOperationException** part from the message by configuring the **Inbound BizTalk message body** option in the transport properties dialog box.</span></span> <span data-ttu-id="64bf0-122">例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="64bf0-122">For example,</span></span>  
  
   -   <span data-ttu-id="64bf0-123">選択**パス--本文のパスで見つかったコンテンツ**します。</span><span class="sxs-lookup"><span data-stu-id="64bf0-123">Select **Path -- content located by body path**.</span></span>  
  
   -   <span data-ttu-id="64bf0-124">本文のパス式を次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="64bf0-124">Set the Body path expression to the following:</span></span>  
  
       ```  
       /*[local-name()='Fault']/*[local-name()='Detail']/* | /*[local-name()='DivideResponse']  
       ```  
  
   -   <span data-ttu-id="64bf0-125">選択**Xml**から、**ノード エンコード**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="64bf0-125">Select **Xml** from the **Node encoding** drop-down list.</span></span>  
  
9. <span data-ttu-id="64bf0-126">オーケストレーションで、1 つのスコープと 2 つの例外ハンドラを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64bf0-126">In the orchestration, you will need to add a scope and two exception handlers.</span></span> <span data-ttu-id="64bf0-127">1 つの例外ハンドラはエラー操作に似ています**MyOperationException** 、前の例に示すように、その他の例外ハンドラは汎用のキャッチ**SOAPExceptions**します。</span><span class="sxs-lookup"><span data-stu-id="64bf0-127">One exception handler is for the Fault operation, similar to **MyOperationException** shown in the preceding example; the other exception handler is for catching generic **SOAPExceptions**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64bf0-128">参照</span><span class="sxs-lookup"><span data-stu-id="64bf0-128">See Also</span></span>  
 <span data-ttu-id="64bf0-129">[WCF サービスとして公開されたオーケストレーションからエラー例外をスローする方法](../core/how-to-throw-fault-exceptions-from-orchestrations-published-as-wcf-services.md) </span><span class="sxs-lookup"><span data-stu-id="64bf0-129">[How to Throw Fault Exceptions from Orchestrations Published as WCF Services](../core/how-to-throw-fault-exceptions-from-orchestrations-published-as-wcf-services.md) </span></span>  
 [<span data-ttu-id="64bf0-130">BizTalk WCF サービス使用ウィザードを使用して WCF サービスを使用する方法</span><span class="sxs-lookup"><span data-stu-id="64bf0-130">How to Use the BizTalk WCF Service Consuming Wizard to Consume a WCF Service</span></span>](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md)