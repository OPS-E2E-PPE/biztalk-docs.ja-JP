---
title: チュートリアル 5:BizTalk Server を使用して REST インターフェイスの呼び出し |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73871ca3-abd0-45ae-b379-6df76a967a80
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4688f550c78a561a85c4ca8288ab8ef6e6d264f8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399173"
---
# <a name="tutorial-5-invoking-a-rest-interface-using-biztalk-server"></a><span data-ttu-id="4f190-102">チュートリアル 5:BizTalk Server を使用して REST インターフェイスの呼び出し</span><span class="sxs-lookup"><span data-stu-id="4f190-102">Tutorial 5: Invoking a REST Interface Using BizTalk Server</span></span>
<span data-ttu-id="4f190-103">このセクションを使用して REST エンドポイントを呼び出す方法の詳細なチュートリアルを提供する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="4f190-103">This section provides a step-by-step walkthrough on how to invoke a REST endpoint using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="4f190-104">このチュートリアルではから利用できる REST エンドポイントを呼び出す、 [!INCLUDE[winazure](../includes/winazure-md.md)] Marketplace を航空会社のフライト米国の遅延を返します。</span><span class="sxs-lookup"><span data-stu-id="4f190-104">In this tutorial you invoke a REST endpoint available from the [!INCLUDE[winazure](../includes/winazure-md.md)] Marketplace that returns the delays in flights of US air carriers.</span></span> <span data-ttu-id="4f190-105">このチュートリアルは、新しい**Wcf-webhttp**でアダプターが導入された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]REST エンドポイントを呼び出す。</span><span class="sxs-lookup"><span data-stu-id="4f190-105">The tutorial uses the new **WCF-WebHttp** adapter introduced in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to invoke the REST endpoint.</span></span>  
  
##  <a name="BKMK_Scenario"></a> <span data-ttu-id="4f190-106">このチュートリアルで使用するシナリオ</span><span class="sxs-lookup"><span data-stu-id="4f190-106">Scenario Used in This Tutorial</span></span>  
 [!INCLUDE[winazure](../includes/winazure-md.md)] <span data-ttu-id="4f190-107">Marketplace は、次を提供します米国航空会社のフライトの遅延を取得する REST リソース URL:。</span><span class="sxs-lookup"><span data-stu-id="4f190-107">Marketplace provides the following the REST resource URL to retrieve flight delays of US air carriers:</span></span>  
  
```  
https://api.datamarket.azure.com/oakleaf/US_Air_Carrier_Flight_Delays_Incr/On_Time_Performance  
```  
  
 <span data-ttu-id="4f190-108">Web ブラウザーのアドレス バーにこの URL を入力する場合は、リソースへのアクセスの資格情報を求められます。</span><span class="sxs-lookup"><span data-stu-id="4f190-108">If you enter this URL in the address bar of a Web browser, you are prompted for credentials to access the resource.</span></span> <span data-ttu-id="4f190-109">ログインした後、 [Windows Azure Marketplace](http://go.microsoft.com/fwlink/p/?LinkId=257913)から資格情報を取得することができます、**マイ アカウント**web ページのタブ。</span><span class="sxs-lookup"><span data-stu-id="4f190-109">After you have logged into the [Windows Azure Marketplace](http://go.microsoft.com/fwlink/p/?LinkId=257913), you can get the credentials from the **My Account** tab of the web page.</span></span> <span data-ttu-id="4f190-110">に対して資格情報が表示されている、**顧客 ID** (ユーザー名) と**プライマリ アカウント キー** (パスワード) ラベル。</span><span class="sxs-lookup"><span data-stu-id="4f190-110">The credentials are listed against the **Customer ID** (user name) and **Primary Account Key** (password) labels.</span></span>  
  
 <span data-ttu-id="4f190-111">このチュートリアルで使用するリソースの URL と資格情報を双方向を構成する**Wcf-webhttp**ポートを送信します。</span><span class="sxs-lookup"><span data-stu-id="4f190-111">In this tutorial, you use the resource URL and the credentials to configure a two-way **WCF-WebHttp** send port.</span></span> <span data-ttu-id="4f190-112">双方向の送信ポートの受信パイプラインは、フライトの詳細を応答メッセージを受信しは、メッセージを公開、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベースです。</span><span class="sxs-lookup"><span data-stu-id="4f190-112">The receive pipeline of the two-way send port receives the response message with the flight details and publishes the message to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] message box database.</span></span> <span data-ttu-id="4f190-113">Wcf-webhttp 送信ポートによって公開されるすべてのメッセージをサブスクライブする FILE 送信ポートを構成するとします。</span><span class="sxs-lookup"><span data-stu-id="4f190-113">You configure a FILE send port that subscribes to all the messages published by the WCF-WebHttp send port.</span></span> <span data-ttu-id="4f190-114">FILE 送信ポートからメッセージを使用する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]し、ファイルの場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="4f190-114">The FILE send port consumes the message from the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and copies it to a file location.</span></span>  
  
 <span data-ttu-id="4f190-115">実際のビジネス シナリオでは、ビジネス アプリケーションからメッセージを取得する受信場所などの大規模なビジネス プロセスに関連付けることによって、Wcf-webhttp 送信ポートをトリガーできます。</span><span class="sxs-lookup"><span data-stu-id="4f190-115">In a real-world business scenario, the WCF-WebHttp send port can be triggered by associating it with a larger business process such as a receive location that gets a message from a business application.</span></span> <span data-ttu-id="4f190-116">ただし、このチュートリアルでの焦点は、REST インターフェイスを呼び出す方法を示すためすることができますを使用して、送信ポートをトリガーするダミー メッセージを受信する単純なファイルの場所。</span><span class="sxs-lookup"><span data-stu-id="4f190-116">However, in this tutorial, because the focus is on demonstrating how to invoke a REST interface, you can use a simple FILE location that receives a dummy message to trigger the send port.</span></span>  
  
 <span data-ttu-id="4f190-117">そのため、要約すると、このソリューションを構成するのには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f190-117">So, to summarize, you must perform the following steps to configure this solution:</span></span>  
  
1.  <span data-ttu-id="4f190-118">ファイルを構成する受信場所をダミー要求メッセージを選択します。</span><span class="sxs-lookup"><span data-stu-id="4f190-118">Configure a FILE receive location to pick a dummy request message.</span></span>  
  
2.  <span data-ttu-id="4f190-119">REST リソース URL を呼び出すし、応答を受信する双方向の Wcf-webhttp 送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="4f190-119">Configure a two-way WCF-WebHttp send port to invoke the REST resource URL and receive a response.</span></span>  
  
3.  <span data-ttu-id="4f190-120">フライトの詳細を含む応答メッセージを使用し、ファイルの場所にコピーする一方向 FILE 送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="4f190-120">Configure a one-way FILE send port to consume the response message with the flight details and copy it to a file location.</span></span>  
  
## <a name="set-up-your-includewinazureincludeswinazure-mdmd-marketplace-account"></a><span data-ttu-id="4f190-121">セットアップ、 [!INCLUDE[winazure](../includes/winazure-md.md)] Marketplace アカウント</span><span class="sxs-lookup"><span data-stu-id="4f190-121">Set up Your [!INCLUDE[winazure](../includes/winazure-md.md)] Marketplace Account</span></span>  
 <span data-ttu-id="4f190-122">REST エンドポイントを介して公開されているフライト遅延データにアクセスするには、まず、US Air Carrier Flight Delays サンプル データ フィードを購読する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f190-122">To access the flight delay data exposed through the REST endpoint, you must first subscribe to the US Air Carrier Flight Delays sample data feed.</span></span> <span data-ttu-id="4f190-123">そのためには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4f190-123">Perform the following steps to do so:</span></span>  
  
#### <a name="to-subscribe-to-the-data-feed"></a><span data-ttu-id="4f190-124">データ フィードを購読するには</span><span class="sxs-lookup"><span data-stu-id="4f190-124">To subscribe to the data feed</span></span>  
  
1. <span data-ttu-id="4f190-125">ログイン、 [!INCLUDE[winazure](../includes/winazure-md.md)] Marketplace が Microsoft アカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="4f190-125">Log in to the [!INCLUDE[winazure](../includes/winazure-md.md)] Marketplace using your Microsoft account.</span></span>  
  
2. <span data-ttu-id="4f190-126">**データ** タブを見つけて、クリックして、 **US Air Carrier Flight Delays**サービス。</span><span class="sxs-lookup"><span data-stu-id="4f190-126">In the **Data** tab, locate and click the **US Air Carrier Flight Delays** service.</span></span>  
  
3. <span data-ttu-id="4f190-127">データ サービス ページで、次のようにクリックします。**サインアップ**します。</span><span class="sxs-lookup"><span data-stu-id="4f190-127">On the data service page, click **Sign Up**.</span></span> <span data-ttu-id="4f190-128">[サインアップ] ページで、契約の条項に同意し、**サインアップ**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="4f190-128">On the Sign Up page, accept the terms of agreement and then click **Sign up** again.</span></span>  
  
4. <span data-ttu-id="4f190-129">**マイ アカウント** タブで、データ サービスにアクセスする資格情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="4f190-129">In the **My Account** tab, retrieve the credentials to access the data service.</span></span> <span data-ttu-id="4f190-130">に対して資格情報が表示されている、**顧客 ID** (ユーザー名) と**プライマリ アカウント キー** (パスワード) ラベル。</span><span class="sxs-lookup"><span data-stu-id="4f190-130">The credentials are listed against the **Customer ID** (user name) and **Primary Account Key** (password) labels.</span></span> <span data-ttu-id="4f190-131">これらの資格情報を構成するときに必要があります、 **Wcf-webhttp**ポートを送信します。</span><span class="sxs-lookup"><span data-stu-id="4f190-131">You will need these credentials while configuring the **WCF-WebHttp** send port.</span></span>  
  
## <a name="set-up-your-computer"></a><span data-ttu-id="4f190-132">コンピューターをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="4f190-132">Set up Your Computer</span></span>  
 <span data-ttu-id="4f190-133">このチュートリアルが必要で使用するシナリオを構成する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]お使いのコンピューターにインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="4f190-133">To configure the scenario used in this tutorial you must have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installed and configured on your computer.</span></span> <span data-ttu-id="4f190-134">プロビジョニングする場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]にある指示に従って、Windows Azure VM 上のコンピューター [Azure VM での BizTalk Server の構成](http://msdn.microsoft.com/library/azure/jj248689.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="4f190-134">If you want to provision a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer on a Windows Azure VM, follow the instructions at [Configuring BizTalk Server on an Azure VM](http://msdn.microsoft.com/library/azure/jj248689.aspx).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4f190-135">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4f190-135">In This Section</span></span>  
  
-   [<span data-ttu-id="4f190-136">ステップ 1: ファイルを構成する受信場所</span><span class="sxs-lookup"><span data-stu-id="4f190-136">Step 1: Configure a FILE Receive Location</span></span>](../core/step-1-configure-a-file-receive-location.md)  
  
-   [<span data-ttu-id="4f190-137">手順 2:双方向の Wcf-webhttp 送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="4f190-137">Step 2: Configure a Two-way WCF-WebHttp Send Port</span></span>](../core/step-2-configure-a-two-way-wcf-webhttp-send-port.md)  
  
-   [<span data-ttu-id="4f190-138">ステップ 3:一方向 FILE 送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="4f190-138">Step 3: Configure a One-way FILE Send Port</span></span>](../core/step-3-configure-a-one-way-file-send-port.md)  
  
-   [<span data-ttu-id="4f190-139">手順 4:ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="4f190-139">Step 4: Test the Solution</span></span>](../core/step-4-test-the-solution.md)