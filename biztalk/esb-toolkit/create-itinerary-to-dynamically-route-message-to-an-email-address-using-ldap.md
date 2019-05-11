---
title: 操作方法:LDAP クエリを使用する電子メール アドレスにメッセージを動的にルーティングするスケジュールを作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d9929dd-5e45-4b0d-90df-52a35e68b0ba
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10e9ca97e52ef901301d141a278d49e4026a2fcb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396518"
---
# <a name="how-to-create-an-itinerary-to-dynamically-route-a-message-to-an-email-address-using-an-ldap-query"></a><span data-ttu-id="714b3-102">操作方法:LDAP クエリを使用する電子メール アドレスにメッセージを動的にルーティングするスケジュールを作成します。</span><span class="sxs-lookup"><span data-stu-id="714b3-102">How to: Create an Itinerary to Dynamically Route a Message to an Email Address Using an LDAP Query</span></span>
## <a name="goal"></a><span data-ttu-id="714b3-103">[目標]</span><span class="sxs-lookup"><span data-stu-id="714b3-103">Goal</span></span>  
 <span data-ttu-id="714b3-104">このセクションでは、LDAP (ライトウェイト ディレクトリ アクセス プロトコル) 経由の電子メール アドレスを照会し、BizTalk Server の SMTP アダプターを使用してエンドポイントを解決する電子メール メッセージを送信するスケジュールを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="714b3-104">This section demonstrates how to create an itinerary that queries an e-mail address through LDAP (Lightweight Directory Access Protocol) and then sends an e-mail message to the resolved endpoint using the BizTalk Server SMTP adapter.</span></span>  
  
 <span data-ttu-id="714b3-105">このトピックでは、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="714b3-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="714b3-106">LDAP クエリを使用してメッセージを動的にルーティングするスケジュールの回覧先を作成します。</span><span class="sxs-lookup"><span data-stu-id="714b3-106">Create an itinerary routing slip to dynamically route a message using an LDAP query.</span></span>  
  
-   <span data-ttu-id="714b3-107">旅行プランのテスト用クライアントのサンプル アプリケーションを使用して、旅行プランをテストします。</span><span class="sxs-lookup"><span data-stu-id="714b3-107">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="714b3-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="714b3-108">Prerequisites</span></span>  
 <span data-ttu-id="714b3-109">この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)します。</span><span class="sxs-lookup"><span data-stu-id="714b3-109">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
 <span data-ttu-id="714b3-110">このセクションを実行するコンピューターで Microsoft Active Directory ディレクトリ サービスを構成し、実行されている必要があります (でないために必要なコンピューターがドメイン コント ローラーが、そのドメインに接続する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="714b3-110">The computer on which you will complete this section must have Microsoft Active Directory directory service configured and running (it is not required that the computer is the domain controller, but it must be connected to the domain).</span></span> <span data-ttu-id="714b3-111">SMTP サーバーを構成および実行して; にある必要がありますも、このトピックの結果をテストするために、ESB によって送信された電子メールをチェックすると、クライアントが必要です。</span><span class="sxs-lookup"><span data-stu-id="714b3-111">Also, an SMTP server must be configured and running; in order to test the outcome of this How-to topic, you must have a client with which to check the e-mail sent by the ESB.</span></span>  
  
 <span data-ttu-id="714b3-112">このセクションの手順には、globalbank.com のドメインと Active Directory 組織単位に Employees という名前 (などの自分のプロファイルで有効な電子メールアドレスを持つJohnEvansをという名前のユーザーを含むGlobalBankをという名前の組織が想定していますjohne@globalbank.com).</span><span class="sxs-lookup"><span data-stu-id="714b3-112">The instructions in this section assume an organization named Global Bank, with a domain of globalbank.com, with an Active Directory Organizational Unit named Employees that contains a user named John Evans with a valid e-mail address in his profile (such as johne@globalbank.com).</span></span> <span data-ttu-id="714b3-113">これらの環境要因をレプリケートする必要はありません。ただし、この実装で、環境を再作成するために、これらの要因を考慮してください、必要に応じて置換を行います。</span><span class="sxs-lookup"><span data-stu-id="714b3-113">It is not necessary to replicate these environmental factors; however, for purposes of recreating this implementation in your environment, please account for these factors and make substitutions as necessary.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="714b3-114">手順</span><span class="sxs-lookup"><span data-stu-id="714b3-114">Steps</span></span>  
  
#### <a name="to-create-an-esb-itinerary-domain-specific-language-dsl-model"></a><span data-ttu-id="714b3-115">ESB スケジュール オンランプ ドメイン固有言語 (DSL) モデルを作成するには</span><span class="sxs-lookup"><span data-stu-id="714b3-115">To create an ESB itinerary domain-specific language (DSL) model</span></span>  
  
1.  <span data-ttu-id="714b3-116">Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="714b3-116">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="714b3-117">ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントして、**追加**、順にクリックします**新しい行程**します。</span><span class="sxs-lookup"><span data-stu-id="714b3-117">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="714b3-118">**新しい項目の追加**ダイアログ ボックスに「 **LdapResolution**で、**名前**ボックスをクリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="714b3-118">In the **Add New Item** dialog box, type **LdapResolution** in the **Name** box, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="714b3-119">旅行プランのプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="714b3-119">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="714b3-120">Visual Studio でのデザイン画面をクリックします。 **LdapResolution.itinerary**します。</span><span class="sxs-lookup"><span data-stu-id="714b3-120">In Visual Studio, click the design surface of **LdapResolution.itinerary**.</span></span> <span data-ttu-id="714b3-121">**LdapResolution**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="714b3-121">In the **LdapResolution** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="714b3-122">**モデル エクスポーター**ドロップダウン リストでは、をクリックして**XML 行程エクスポーター**します。</span><span class="sxs-lookup"><span data-stu-id="714b3-122">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="714b3-123">下、**エクステンダー設定**セクションで、横に、**旅行プラン XML ファイル**プロパティ、省略記号ボタン (…) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="714b3-123">Under the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="714b3-124">**XML ファイルの**ダイアログ ボックスに「 **C:\HowTos\Itineraries\LdapResolution**で、**ファイル名**ボックスをクリック**保存**します。</span><span class="sxs-lookup"><span data-stu-id="714b3-124">In the **Select XML File** dialog box, type **C:\HowTos\Itineraries\LdapResolution** in the **File name** box, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="714b3-125">この手順では、旅行プランを XML としてローカル ファイルの場所にエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="714b3-125">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="714b3-126">行程データベースの代わりにスケジュールをローカル ファイルの場所にエクスポートして、ESB のテスト用クライアント アプリケーションを使用してスケジュールのテストが可能です。</span><span class="sxs-lookup"><span data-stu-id="714b3-126">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="714b3-127">この操作方法に関するトピックの後半には、このプロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="714b3-127">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="714b3-128">旅行プランの構造を定義するには</span><span class="sxs-lookup"><span data-stu-id="714b3-128">To define the structure of the itinerary</span></span>  
  
1. <span data-ttu-id="714b3-129">ツールボックスからドラッグ、**入口**デザイン サーフェイスにモデル要素。</span><span class="sxs-lookup"><span data-stu-id="714b3-129">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="714b3-130">**OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="714b3-130">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
   1.  <span data-ttu-id="714b3-131">をクリックして、**名前**プロパティ、および入力**ReceiveNAOrder**します。</span><span class="sxs-lookup"><span data-stu-id="714b3-131">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
   2.  <span data-ttu-id="714b3-132">**エクステンダー**ドロップダウン リストでは、をクリックして**入口 ESB エクステンダー**します。</span><span class="sxs-lookup"><span data-stu-id="714b3-132">In the **Extender** drop-down list, click **On-Ramp ESB Extender**.</span></span>  
  
   3.  <span data-ttu-id="714b3-133">**BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="714b3-133">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
   4.  <span data-ttu-id="714b3-134">**受信ポート**ドロップダウン リストでは、をクリックして**OnRamp.Itinerary**します。</span><span class="sxs-lookup"><span data-stu-id="714b3-134">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2. <span data-ttu-id="714b3-135">ツールボックスからドラッグ、**行程サービス**の右側に配置し、デザイン画面に要素をモデル化し、**入口**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="714b3-135">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **On-Ramp** model element.</span></span> <span data-ttu-id="714b3-136">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="714b3-136">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
   1.  <span data-ttu-id="714b3-137">をクリックして、**名前**プロパティ、および入力**RouteMessageEmail**します。</span><span class="sxs-lookup"><span data-stu-id="714b3-137">Click the **Name** property, and then type **RouteMessageEmail**.</span></span>  
  
   2.  <span data-ttu-id="714b3-138">**行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**エクステンダーのメッセージング**します。</span><span class="sxs-lookup"><span data-stu-id="714b3-138">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="714b3-139">このプロパティは、プロセスが行われる (メッセージング) パイプラインで定義します。</span><span class="sxs-lookup"><span data-stu-id="714b3-139">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="714b3-140">または、プロセスはオーケストレーション内の場所を受け取らない場合は設定、**行程サービス エクステンダー**プロパティを**オーケストレーション エクステンダー**します。</span><span class="sxs-lookup"><span data-stu-id="714b3-140">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
   3.  <span data-ttu-id="714b3-141">**コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、 をクリックし、**受信ハンドラー**。</span><span class="sxs-lookup"><span data-stu-id="714b3-141">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
   4.  <span data-ttu-id="714b3-142">**サービス名**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB.Services.Routing**します。</span><span class="sxs-lookup"><span data-stu-id="714b3-142">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
3. <span data-ttu-id="714b3-143">右クリックし、**リゾルバー**のコレクション、 **RouteMessageEmail**モデル要素をクリックして**新しいリゾルバーを追加**します。</span><span class="sxs-lookup"><span data-stu-id="714b3-143">Right-click the **Resolver** collection of the **RouteMessageEmail** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="714b3-144">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="714b3-144">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
   1.  <span data-ttu-id="714b3-145">をクリックして、**名前**プロパティ、および入力**LdapResolver**します。</span><span class="sxs-lookup"><span data-stu-id="714b3-145">Click the **Name** property, and then type **LdapResolver**.</span></span>  
  
   2.  <span data-ttu-id="714b3-146">**リゾルバーの実装**ドロップダウン リストでは、をクリックして**LDAP 競合回避モジュールの拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="714b3-146">In the **Resolver Implementation** drop-down list, click **LDAP Resolver Extension**.</span></span>  
  
   3.  <span data-ttu-id="714b3-147">**トランスポート名**ドロップダウン リストでは、をクリックして**SMTP**します。</span><span class="sxs-lookup"><span data-stu-id="714b3-147">In the **Transport Name** drop-down list, click **SMTP**.</span></span>  
  
   4.  <span data-ttu-id="714b3-148">をクリックして、**トランスポート場所**プロパティ、および入力 **{メール}**</span><span class="sxs-lookup"><span data-stu-id="714b3-148">Click the **Transport Location** property, and then type **{mail}**</span></span>  
  
   5.  <span data-ttu-id="714b3-149">をクリックして、 **SearchRoot**プロパティ、および入力**ou = 従業員、dc = globalbank、dc = com**</span><span class="sxs-lookup"><span data-stu-id="714b3-149">Click the **SearchRoot** property, and then type **ou=Employees,dc=globalbank,dc=com**</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="714b3-150">「前提条件」セクションでは、仕様に従って、環境設定が、場合は、上記プロパティ値環境に適したしたもので置き換えます。</span><span class="sxs-lookup"><span data-stu-id="714b3-150">If you have not set up your environment according to the specifications in the "Prerequisites" section, replace the values in the preceding property with ones that are appropriate for your environment.</span></span>  
  
   6.  <span data-ttu-id="714b3-151">をクリックして、**フィルター**プロパティに値を変更して **(&(objectClass=User) (&#124;(givenName = john)))**</span><span class="sxs-lookup"><span data-stu-id="714b3-151">Click the **Filter** property, and then change the value to **(&(objectClass=User)(&#124;(givenName=john)))**</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="714b3-152">既存のテキストを置き換えるには、上記の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="714b3-152">Type the preceding value to replace the existing text.</span></span>  
  
   7.  <span data-ttu-id="714b3-153">**ThrowErrorIfNotFound**ドロップダウン リストでは、をクリックして**True**します。</span><span class="sxs-lookup"><span data-stu-id="714b3-153">In the **ThrowErrorIfNotFound** drop-down list, click **True**.</span></span>  
  
4. <span data-ttu-id="714b3-154">[プロパティ] ウィンドウ、**エンドポイント構成**プロパティ、省略記号ボタン (…) を順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="714b3-154">In the Properties window, click the **Endpoint Configuration** property, and then click the ellipsis button (...).</span></span>  
  
   1. <span data-ttu-id="714b3-155">**エンドポイント構成**ダイアログ ボックスで、をクリックして、 **EmailBodyText**プロパティ、および入力**注文を処理する準備が**します。</span><span class="sxs-lookup"><span data-stu-id="714b3-155">In the **Endpoint Configuration** dialog box, click the **EmailBodyText** property, and then type **Order is ready to be processed**.</span></span>  
  
   2. <span data-ttu-id="714b3-156">をクリックして、**から**プロパティ、および入力 <strong>orders@globalbank.com</strong>します。</span><span class="sxs-lookup"><span data-stu-id="714b3-156">Click the **From** property, and then type <strong>orders@globalbank.com</strong>.</span></span>  
  
   3. <span data-ttu-id="714b3-157">をクリックして、 **MessagePartsAttachment**プロパティ、および入力**2**します。</span><span class="sxs-lookup"><span data-stu-id="714b3-157">Click the **MessagePartsAttachment** property, and then type **2**.</span></span>  
  
   4. <span data-ttu-id="714b3-158">をクリックして、**サブジェクト**プロパティ、および入力 **{givenName} ため**。</span><span class="sxs-lookup"><span data-stu-id="714b3-158">Click the **Subject** property, and then type **Order for {givenName}**.</span></span>  
  
   5. <span data-ttu-id="714b3-159">構成、 **SMTPAuthentication、SMTPHost、ユーザー名、** と**パスワード**プロパティは、ローカル環境の接続情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="714b3-159">Configure the **SMTPAuthentication, SMTPHost, UserName,** and **Password** properties using the connection information for your local environment.</span></span>  
  
   6. <span data-ttu-id="714b3-160">をクリックして**OK**を閉じる、**エンドポイント構成** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="714b3-160">Click **OK** to close the **Endpoint Configuration** dialog box.</span></span>  
  
5. <span data-ttu-id="714b3-161">右クリックし、 **LdapResolver**リゾルバー、およびクリック**テスト構成の競合回避モジュール**します。</span><span class="sxs-lookup"><span data-stu-id="714b3-161">Right-click the **LdapResolver** resolver, and then click **Test Resolver Configuration**.</span></span>  
  
6. <span data-ttu-id="714b3-162">[出力] ウィンドウで、解決のサブジェクトを確認します**エンドポイント構成**値は**john 順序**、ことを確認します、解決**トランスポート場所**が、。電子メール アドレスを Active Directory でユーザーのアカウントに関連付けられている (たとえば、 johne@globalbank.com)。</span><span class="sxs-lookup"><span data-stu-id="714b3-162">In the Output window, verify the subject in the resolved **Endpoint Configuration** value is **Order for John**, and then verify that the resolved **Transport Location** is the e-mail address associated with the user's account in Active Directory (for example, johne@globalbank.com).</span></span>  
  
7. <span data-ttu-id="714b3-163">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="714b3-163">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="714b3-164">接続をドラッグして、 **ReceiveNAOrder**モデル要素に、 **RouteMessageEmail**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="714b3-164">Drag a connection from the **ReceiveNAOrder** model element to the **RouteMessageEmail** model element.</span></span>  
  
8. <span data-ttu-id="714b3-165">ツールボックスからドラッグして、**傾斜オフ**の右側に配置し、デザイン画面に要素をモデル化し、 **RouteMessageEmail**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="714b3-165">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **RouteMessageEmail** model element.</span></span> <span data-ttu-id="714b3-166">**OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="714b3-166">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
   1.  <span data-ttu-id="714b3-167">をクリックして、**名前**プロパティ、および入力**EmailNAOrderDoc**します。</span><span class="sxs-lookup"><span data-stu-id="714b3-167">Click the **Name** property, and then type **EmailNAOrderDoc**.</span></span>  
  
   2.  <span data-ttu-id="714b3-168">**エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ ESB エクステンダー**します。</span><span class="sxs-lookup"><span data-stu-id="714b3-168">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
   3.  <span data-ttu-id="714b3-169">**BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**GlobalBank.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="714b3-169">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
   4.  <span data-ttu-id="714b3-170">**送信ポート**ドロップダウン リストでは、をクリックして**DynamicResolutionOneWay**します。</span><span class="sxs-lookup"><span data-stu-id="714b3-170">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
9. <span data-ttu-id="714b3-171">ツールボックスからドラッグ、**スケジュール サービス**モデルのデザイン画面に要素との間に配置し、 **RouteMessageEmail**モデル要素と**EmailNAOrderDoc**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="714b3-171">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **RouteMessageEmail** model element and the **EmailNAOrderDoc** model element.</span></span> <span data-ttu-id="714b3-172">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="714b3-172">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="714b3-173">をクリックして、**名前**プロパティ、および入力**SendPortFilter**します。</span><span class="sxs-lookup"><span data-stu-id="714b3-173">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="714b3-174">**行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ エクステンダー**。</span><span class="sxs-lookup"><span data-stu-id="714b3-174">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="714b3-175">**傾斜オフ**ドロップダウン リストで、展開**EmailNAOrderDoc**、順にクリックします**送信ハンドラー**します。</span><span class="sxs-lookup"><span data-stu-id="714b3-175">In the **Off-Ramp** drop-down list, expand **EmailNAOrderDoc**, and then click **Send Handlers**.</span></span>  
  
10. <span data-ttu-id="714b3-176">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="714b3-176">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="714b3-177">接続をドラッグして、 **RouteMessageEmail**モデル要素に、 **SendPortFilter**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="714b3-177">Drag a connection from the **RouteMessageEmail** model element to the **SendPortFilter** model element.</span></span>  
  
11. <span data-ttu-id="714b3-178">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="714b3-178">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="714b3-179">接続をドラッグして、 **SendPortFilter**モデル要素に、 **EmailNAOrderDoc**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="714b3-179">Drag a connection from the **SendPortFilter** model element to the **EmailNAOrderDoc** model element.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="714b3-180">旅行プランのテスト クライアントで使用するモデルをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="714b3-180">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="714b3-181">Visual Studio でのデザイン画面を右クリックし、 **LdapResolution**旅行プランをクリックして**モデルのエクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="714b3-181">In Visual Studio, right-click the design surface of the **LdapResolution** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="714b3-182">旅行プランの XML バージョンは、Visual Studio で開きます。</span><span class="sxs-lookup"><span data-stu-id="714b3-182">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="714b3-183">すべてのプロジェクト成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="714b3-183">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="714b3-184">Windows エクスプ ローラーでは、C:\HowTos\Itineraries を参照し、旅行プラン XML (LdapResolution.xml) の作成に注意してください。</span><span class="sxs-lookup"><span data-stu-id="714b3-184">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (LdapResolution.xml).</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="714b3-185">旅行プランをテストするには</span><span class="sxs-lookup"><span data-stu-id="714b3-185">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="714b3-186">中に作成されたショートカットを使用してスケジュールのテスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB します。Itinerary.Test.exe - ショートカット)。</span><span class="sxs-lookup"><span data-stu-id="714b3-186">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="714b3-187">行程テスト クライアントでオフ、 **WCF サービスを使用して**チェック ボックスをオンにし**ロード行程**。</span><span class="sxs-lookup"><span data-stu-id="714b3-187">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="714b3-188">**行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。</span><span class="sxs-lookup"><span data-stu-id="714b3-188">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="714b3-189">選択**LdapResolution.xml**、順にクリックします**オープン**旅行プランを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="714b3-189">Select **LdapResolution.xml**, and then click **Open** to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="714b3-190">をクリックして**OK**をオフに、**旅行プランは正常に読み込まれる**メッセージ。</span><span class="sxs-lookup"><span data-stu-id="714b3-190">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
5.  <span data-ttu-id="714b3-191">旅行プランのテスト クライアントで、横にある省略記号ボタン (…) をクリックします。、**ロード メッセージ**ボックス。</span><span class="sxs-lookup"><span data-stu-id="714b3-191">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="714b3-192">**を読み込む XML ドキュメントの選択** ダイアログ ボックスで、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="714b3-192">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="714b3-193">選択**NAOrderDoc.xml**、順にクリックします**オープン**テスト メッセージを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="714b3-193">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="714b3-194">をクリックして、**要求を提出**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="714b3-194">Click the **Submit Request** button.</span></span> <span data-ttu-id="714b3-195">テストが完了したら、クリックして**OK**表示される確認メッセージを無視します。</span><span class="sxs-lookup"><span data-stu-id="714b3-195">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
8.  <span data-ttu-id="714b3-196">Microsoft Outlook Express (または任意のメール クライアント) を開き John Evans の電子メールへのメッセージの配信を確認します。</span><span class="sxs-lookup"><span data-stu-id="714b3-196">Open Microsoft Outlook Express (or the mail client of your choice) and verify delivery of the message to the e-mail of John Evans.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="714b3-197">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="714b3-197">Additional Resources</span></span>  
 <span data-ttu-id="714b3-198">詳細については、次の関連項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="714b3-198">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="714b3-199">開発アクティビティ</span><span class="sxs-lookup"><span data-stu-id="714b3-199">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="714b3-200">動的な解決とルーティングを利用する</span><span class="sxs-lookup"><span data-stu-id="714b3-200">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)