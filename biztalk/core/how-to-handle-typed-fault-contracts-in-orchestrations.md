---
title: オーケストレーションでコントラクトの型指定されたエラーを処理する方法 |Microsoft ドキュメント
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
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a7643c4a39785018368572d721eed3ef6545c6b
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
---
# <a name="how-to-handle-typed-fault-contracts-in-orchestrations"></a><span data-ttu-id="1f245-102">オーケストレーション内の型指定されたエラー コントラクトを処理する方法</span><span class="sxs-lookup"><span data-stu-id="1f245-102">How to Handle Typed Fault Contracts in Orchestrations</span></span>
<span data-ttu-id="1f245-103">このトピックでは、オーケストレーション内から WCF サービスを使用する際に、型指定されたエラー コントラクトを処理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1f245-103">This topic describes how to handle typed fault contracts when consuming WCF services from within orchestrations.</span></span> <span data-ttu-id="1f245-104">WCF サービスを使用している必要があります、オーケストレーションで型指定されたエラー例外を処理する、 **FaultContractAttribute**サービス操作に適用される以外の場合は、エラーをスローしてを使用してそのため、 **FaultException**\<T\> T が任意の有効なデータ コントラクトまたは WCF サービスからのシリアル化可能な型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1f245-104">To handle typed fault exceptions in orchestrations, the WCF services that you are consuming must have the **FaultContractAttribute** applied to the service operations; therefore, the faults can be thrown by using **FaultException**\<T\> where T can be any valid data contract or serializable type from the WCF services.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="1f245-105">手順</span><span class="sxs-lookup"><span data-stu-id="1f245-105">Procedures</span></span>  
  
#### <a name="to-handle-typed-fault-contracts-in-orchestrations"></a><span data-ttu-id="1f245-106">オーケストレーション内の型指定されたエラー コントラクトを処理するには</span><span class="sxs-lookup"><span data-stu-id="1f245-106">To handle typed fault contracts in orchestrations</span></span>  
  
1.  <span data-ttu-id="1f245-107">Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクト、ソリューション エクスプ ローラーでプロジェクトを右クリックし、をクリックして**追加**、クリックして**生成した項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="1f245-107">In your Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, in Solution Explorer, right-click your project, click **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="1f245-108">**生成した項目の追加 - \<***プロジェクト名***\>**   ダイアログ ボックスで、**テンプレート**セクションで、 **WCF の使用サービス**、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="1f245-108">In the **Add Generated Items - \<***Project name***\>** dialog box, in the **Templates** section, select **Consume WCF Service**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="1f245-109">**BizTalk WCF サービス使用ウィザードへようこそ** ] ページで [ **次**します。</span><span class="sxs-lookup"><span data-stu-id="1f245-109">On the **Welcome to the BizTalk WCF Service Consuming Wizard** page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="1f245-110">**メタデータ ソース**  ページで、 **Metadata Exchange (MEX) エンドポイント**, 、 をクリックし、 **次**します。</span><span class="sxs-lookup"><span data-stu-id="1f245-110">On the **Metadata source** page, select **Metadata Exchange (MEX) endpoint**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="1f245-111">**メタデータ エンドポイント** ページで、Ws-metadata Exchange または Http-get を通じてダウンロードのメタデータを提供する実行中のサービスの URL を指定: http://localhost:8005 などです。</span><span class="sxs-lookup"><span data-stu-id="1f245-111">On the **Metadata Endpoint** page, specify the URL for the running service that provides metadata for download through WS-Metadata Exchange or Http-Get—for example, http://localhost:8005.</span></span> <span data-ttu-id="1f245-112">URL からメタデータ ドキュメントを取得するにはクリックして **取得**します。</span><span class="sxs-lookup"><span data-stu-id="1f245-112">To get the metadata document from the URL, click **Get**.</span></span> <span data-ttu-id="1f245-113">実行中のサービスは、基本的な認証方式を使用したユーザーの資格情報を必要とする場合はクリックして **編集** を開くには、 **BizTalk WCF サービス使用ウィザード**  ダイアログ ボックスのユーザー名と実行中のサービスにアクセスするときに使用するパスワードを指定できます。</span><span class="sxs-lookup"><span data-stu-id="1f245-113">If the running service requires a user credential with the basic authentication scheme, click **Edit** to open the **BizTalk WCF Service Consuming Wizard** dialog box in which you can supply the user name and password to use when accessing the running service.</span></span> <span data-ttu-id="1f245-114">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f245-114">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="1f245-115">**WCF サービス メタデータの概要のインポート**  ページで、設定内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="1f245-115">On the **Import WCF Service Metadata Summary** page, review your settings.</span></span> <span data-ttu-id="1f245-116">クリックして **戻る** に変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="1f245-116">You can click **Back** to make any changes.</span></span> <span data-ttu-id="1f245-117">クリックして **インポート** BizTalk アイテムと、WCF サービスを使用するために使用されている型を作成します。</span><span class="sxs-lookup"><span data-stu-id="1f245-117">Then click **Import** to create the BizTalk artifacts and types to be used for consuming the WCF service.</span></span>  
  
7.  <span data-ttu-id="1f245-118">**BizTalk WCF サービス使用ウィザードを完了する** ] ページで [ **完了**します。</span><span class="sxs-lookup"><span data-stu-id="1f245-118">On the **Completing the BizTalk WCF Service Consuming Wizard** page, click **Finish**.</span></span>  
  
8.  <span data-ttu-id="1f245-119">使用している WCF サービスが、次のエラー例外をスローするとします。</span><span class="sxs-lookup"><span data-stu-id="1f245-119">Suppose that the WCF service that you are consuming throws the following fault exception:</span></span>  
  
    ```  
    throw new FaultException<MyOperationException>(divideException);  
    ```  
  
     <span data-ttu-id="1f245-120">送信ポートでのエラー操作には、型のメッセージが想定して **MyOperationException**, が WCF 応答メッセージには、エラー本文全体が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1f245-120">The fault operation on the send port expects a message of type **MyOperationException**, but the WCF response message contains the whole fault body.</span></span> <span data-ttu-id="1f245-121">そのため、抽出する必要があります、 **MyOperationException** 構成して、メッセージから、 **受信 BizTalk メッセージ本文** トランスポートのプロパティ ダイアログ ボックスでオプションです。</span><span class="sxs-lookup"><span data-stu-id="1f245-121">Therefore, you need to extract the **MyOperationException** part from the message by configuring the **Inbound BizTalk message body** option in the transport properties dialog box.</span></span> <span data-ttu-id="1f245-122">例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1f245-122">For example,</span></span>  
  
    -   <span data-ttu-id="1f245-123">選択 **パス--本文のパスで見つかったコンテンツ**します。</span><span class="sxs-lookup"><span data-stu-id="1f245-123">Select **Path -- content located by body path**.</span></span>  
  
    -   <span data-ttu-id="1f245-124">本文のパス式を次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="1f245-124">Set the Body path expression to the following:</span></span>  
  
        ```  
        /*[local-name()='Fault']/*[local-name()='Detail']/* | /*[local-name()='DivideResponse']  
        ```  
  
    -   <span data-ttu-id="1f245-125">選択 **Xml** から、 **ノード エンコード** ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="1f245-125">Select **Xml** from the **Node encoding** drop-down list.</span></span>  
  
9. <span data-ttu-id="1f245-126">オーケストレーションで、1 つのスコープと 2 つの例外ハンドラを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f245-126">In the orchestration, you will need to add a scope and two exception handlers.</span></span> <span data-ttu-id="1f245-127">1 つの例外ハンドラはのようなエラー処理 **MyOperationException** 前の例に示すように、その他の例外ハンドラーは、ジェネリックをキャッチするため、 **SOAPExceptions**します。</span><span class="sxs-lookup"><span data-stu-id="1f245-127">One exception handler is for the Fault operation, similar to **MyOperationException** shown in the preceding example; the other exception handler is for catching generic **SOAPExceptions**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f245-128">参照</span><span class="sxs-lookup"><span data-stu-id="1f245-128">See Also</span></span>  
 <span data-ttu-id="1f245-129">[WCF サービスとして公開されたオーケストレーションからエラー例外をスローする方法](../core/how-to-throw-fault-exceptions-from-orchestrations-published-as-wcf-services.md) </span><span class="sxs-lookup"><span data-stu-id="1f245-129">[How to Throw Fault Exceptions from Orchestrations Published as WCF Services](../core/how-to-throw-fault-exceptions-from-orchestrations-published-as-wcf-services.md) </span></span>  
 [<span data-ttu-id="1f245-130">BizTalk WCF サービス使用ウィザードを使用して WCF サービスを使用する方法</span><span class="sxs-lookup"><span data-stu-id="1f245-130">How to Use the BizTalk WCF Service Consuming Wizard to Consume a WCF Service</span></span>](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md)