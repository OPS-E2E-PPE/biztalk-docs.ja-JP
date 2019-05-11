---
title: Web サービスの配列を使用する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP adapters, Web services
- Web services, arrays
- orchestrations, Web services
- orchestrations, Web ports
ms.assetid: 29ecaaed-aa8a-4cf9-a7c8-4b0d6dd412ac
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f783c8521d1fbfbf3ffa9297f970ab54e90ce313
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385671"
---
# <a name="how-to-consume-web-service-arrays"></a><span data-ttu-id="c5801-102">Web サービスの配列を使用する方法</span><span class="sxs-lookup"><span data-stu-id="c5801-102">How to Consume Web Service Arrays</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="c5801-103">BizTalk オーケストレーションから Web サービスで公開されている配列を使用する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="c5801-103">provides the ability to consume arrays that are exposed in Web services from a BizTalk Orchestration.</span></span>  
  
 <span data-ttu-id="c5801-104">**Web サービスで公開される配列を使用するオーケストレーションを構成するには。**</span><span class="sxs-lookup"><span data-stu-id="c5801-104">**To configure an Orchestration to consume an array exposed in a Web service:**</span></span>  
  
 <span data-ttu-id="c5801-105">配列を公開する Web サービスの URL を決定します。</span><span class="sxs-lookup"><span data-stu-id="c5801-105">Determine the URL for the Web service that exposes arrays.</span></span> <span data-ttu-id="c5801-106">これは、通常、Web サービスでサポートされる操作を一覧表示する asmx Web ページです。</span><span class="sxs-lookup"><span data-stu-id="c5801-106">This is typically an asmx Web page that lists the operations supported by the Web service.</span></span> <span data-ttu-id="c5801-107">たとえば、「 http://localhost/ArrayWS/ArraySvc.asmx」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="c5801-107">For example: http://localhost/ArrayWS/ArraySvc.asmx.</span></span>  
  
1.  <span data-ttu-id="c5801-108">オーケストレーションを含む Visual Studio プロジェクトでこの URL に Web 参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="c5801-108">Add a Web reference to this URL in the Visual Studio project that contains your orchestration:</span></span>  
  
    -   <span data-ttu-id="c5801-109">ソリューション エクスプ ローラーで右クリックして**参照**、 をクリック**サービス参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="c5801-109">In the Solution Explorer, right-click **References**, and click **Add Service Reference**.</span></span>  
  
    -   <span data-ttu-id="c5801-110">**サービス参照の追加**ダイアログ ボックスで、をクリックして**詳細**します。</span><span class="sxs-lookup"><span data-stu-id="c5801-110">In the **Add Service Reference** dialog box, click **Advanced**.</span></span>  
  
    -   <span data-ttu-id="c5801-111">**サービス参照設定**ダイアログ ボックスで、をクリックして**Web 参照の追加**で、**互換性**セクション。</span><span class="sxs-lookup"><span data-stu-id="c5801-111">In the **Service Reference Settings** dialog box, click **Add Web Reference** in the **Compatibility** section.</span></span>  
  
    -   <span data-ttu-id="c5801-112">**Web 参照の追加** ダイアログ ボックスに Web サービスの URL を入力、 **URL**テキスト ボックスをクリック**移動**。</span><span class="sxs-lookup"><span data-stu-id="c5801-112">In the **Add Web Reference** dialog box, enter the URL for the Web service into the **URL** text box and then click **Go**.</span></span>  
  
    -   <span data-ttu-id="c5801-113">Web 参照の名前を入力、 **Web 参照名**テキスト ボックスをクリックして、**参照の追加**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c5801-113">Enter a name for the Web reference into the **Web reference name** text box and click the **Add Reference** button.</span></span>  
  
    -   <span data-ttu-id="c5801-114">Web 参照は、下に表示されます**Web 参照**ソリューション エクスプ ローラー。</span><span class="sxs-lookup"><span data-stu-id="c5801-114">The Web reference will appear under **Web References** in the Solution Explorer.</span></span>  
  
        > [!TIP]
        >  <span data-ttu-id="c5801-115">Web 参照をプロジェクトに追加した後、 **Web 参照の追加**プロジェクト名を右クリックすると、コマンドは直接利用または**参照**または**のWeb参照**.</span><span class="sxs-lookup"><span data-stu-id="c5801-115">Once you have a Web reference added to the project, the **Add Web Reference** command is directly available when you right-click the project name or **References** or **Web References**.</span></span>  
  
2.  <span data-ttu-id="c5801-116">Web ポートをオーケストレーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="c5801-116">Add a Web port to your orchestration:</span></span>  
  
    -   <span data-ttu-id="c5801-117">ドラッグ、**ポート**を起動するには、オーケストレーション デザイナーで、ツールボックスから図形をポートのいずれかを明らかになります、**ポート構成ウィザード**します。</span><span class="sxs-lookup"><span data-stu-id="c5801-117">Drag a **Port** shape from the toolbox to one of the port surfaces in the Orchestration Designer to launch the **Port Configuration Wizard**.</span></span> <span data-ttu-id="c5801-118">をクリックして、**次**ボタン、**ポート構成ウィザード**を表示する、**ポートのプロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="c5801-118">Click the **Next** button in the **Port Configuration Wizard** to display the **Port Properties** dialog.</span></span>  
  
    -   <span data-ttu-id="c5801-119">値を入力、**名前**、ポートを特定し、をクリックするテキスト ボックス、 **[次へ]** を表示するボタン、**ポートの種類を選択**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="c5801-119">Enter a value into the **Name** text box to identify the port, and click the **Next** button to display the **Select a Port Type** dialog.</span></span>  
  
    -   <span data-ttu-id="c5801-120">オプションを選択して**既存のポートの種類を使用して**、Web に対応する型参照を追加して、をクリックして、Web ポートの選択、 **[次へ]** を表示するボタン、**ポートのバインド**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="c5801-120">Select the option to **Use an existing Port Type**, select the Web Port type that corresponds to the Web reference you added, and click the **Next** button to display the **Port Binding** dialog.</span></span>  
  
    -   <span data-ttu-id="c5801-121">**ポートのバインド**ダイアログは、適切な選択**ポートのバインド**オプションを選択し、をクリックして、**次**、クリックして、**完了**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c5801-121">In the **Port Binding** dialog select the appropriate **Port binding** option and click the **Next** button, then click the **Finish** button.</span></span> <span data-ttu-id="c5801-122">これで、Web サービスでサポートされている操作を含むオーケストレーション デザイナーに表示される Web ポートが必要です。</span><span class="sxs-lookup"><span data-stu-id="c5801-122">You should now have a Web port displayed in the Orchestration Designer that includes the operations supported by the Web service.</span></span>  
  
3.  <span data-ttu-id="c5801-123">追加**送信**と**受信**を適切なオーケストレーションに図形。</span><span class="sxs-lookup"><span data-stu-id="c5801-123">Add **Send** and **Receive** shapes to your Orchestration as appropriate:</span></span>  
  
    -   <span data-ttu-id="c5801-124">ドラッグ、**送信**Web ポートに要求メッセージを送信するオーケストレーションを構成するオーケストレーション デザイナー画面の区分線にツールボックスから図形。</span><span class="sxs-lookup"><span data-stu-id="c5801-124">Drag a **Send** shape from the toolbox to a connecting line in the Orchestration Designer surface to configure the orchestration to send a request message to the Web port.</span></span> <span data-ttu-id="c5801-125">接続する場合、**送信**図形をいずれかの Web ポートの要求メッセージ コネクタ、BizTalk は自動的にこのポートに要求メッセージを送信するときに使用するには、適切な種類のメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="c5801-125">If you connect the **Send** shape to one of the Web port request message connectors, BizTalk will automatically create a message of the appropriate type to be used when sending a request message to this port.</span></span>  
  
    -   <span data-ttu-id="c5801-126">ドラッグ、**受信**Web ポートから応答メッセージを受信するオーケストレーションを構成するオーケストレーション デザイナー画面の区分線にツールボックスから図形。</span><span class="sxs-lookup"><span data-stu-id="c5801-126">Drag a **Receive** shape from the toolbox to a connecting line in the Orchestration Designer surface to configure the orchestration to receive a response message from the Web port.</span></span> <span data-ttu-id="c5801-127">接続する場合、**受信**図形を Web ポートの応答メッセージ コネクタのいずれかが自動的に作成され、このポートから応答メッセージを受信するときに使用するには、適切な種類のメッセージ。</span><span class="sxs-lookup"><span data-stu-id="c5801-127">If you connect the **Receive** shape to one of the Web port response message connectors, BizTalk will automatically create a message of the appropriate type to be used when receiving a response message from this port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c5801-128">メッセージを送信または Web サービスからメッセージを受信するには、SOAP アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="c5801-128">Use the SOAP Adapter to send messages to or receive messages from a Web service.</span></span> <span data-ttu-id="c5801-129">SOAP アダプターの構成の詳細については、次を参照してください。 [SOAP アダプターを構成する](../core/configuring-the-soap-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="c5801-129">For more information about configuring the SOAP Adapter see [Configuring the SOAP Adapter](../core/configuring-the-soap-adapter.md).</span></span>  
  
 <span data-ttu-id="c5801-130">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]オーケストレーション エンジンは、両方のいずれかの Web サービスによって公開されている次元配列およびジャグ配列を使用するためのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="c5801-130">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Orchestration Engine provides support for consuming both one dimensional and jagged arrays that are exposed by Web services.</span></span> <span data-ttu-id="c5801-131">配列を公開する Web サービスへの Web 参照を追加する場合、オーケストレーション デザイナーは、配列を記述した Web メッセージの種類を生成します。</span><span class="sxs-lookup"><span data-stu-id="c5801-131">If you add a Web reference to a Web service that exposes arrays, the Orchestration Designer will generate a Web message type that describes the array.</span></span> <span data-ttu-id="c5801-132">送信し、他のメッセージと同様、この種類のメッセージを受信できます。</span><span class="sxs-lookup"><span data-stu-id="c5801-132">You can then send and receive messages of this type like any other message.</span></span> <span data-ttu-id="c5801-133">BizTalk Server では、Web ポートだけに配列を含む Web メッセージの送信は制限されません。</span><span class="sxs-lookup"><span data-stu-id="c5801-133">BizTalk Server does not limit the sending of Web messages containing arrays to only Web ports.</span></span>  
  
 <span data-ttu-id="c5801-134">Web サービスの配列を使用する例を参照してください、SDK サンプル「Web サービスを使用する"と"消費 Web サービスの配列パラメーター" [ http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)します。</span><span class="sxs-lookup"><span data-stu-id="c5801-134">For an example of consuming Web service arrays, see the SDK sample "Consume Web Services" and "Consuming Web Services with Array Parameters" at [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5801-135">参照</span><span class="sxs-lookup"><span data-stu-id="c5801-135">See Also</span></span>  
 [<span data-ttu-id="c5801-136">オーケストレーションでのメッセージの使用</span><span class="sxs-lookup"><span data-stu-id="c5801-136">Using Messages in Orchestrations</span></span>](../core/using-messages-in-orchestrations.md)