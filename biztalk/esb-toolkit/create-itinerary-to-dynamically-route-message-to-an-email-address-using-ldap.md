---
title: "方法: 動的に LDAP クエリを使用する電子メール アドレスにメッセージをルーティングする日程を作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6d9929dd-5e45-4b0d-90df-52a35e68b0ba
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 751eaf381b762372652bb77ddf6f00ffe43971c2
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-create-an-itinerary-to-dynamically-route-a-message-to-an-email-address-using-an-ldap-query"></a><span data-ttu-id="099c5-102">方法: 動的に LDAP クエリを使用する電子メール アドレスにメッセージをルーティングする日程を作成します。</span><span class="sxs-lookup"><span data-stu-id="099c5-102">How to: Create an Itinerary to Dynamically Route a Message to an Email Address Using an LDAP Query</span></span>
## <a name="goal"></a><span data-ttu-id="099c5-103">[目標]</span><span class="sxs-lookup"><span data-stu-id="099c5-103">Goal</span></span>  
 <span data-ttu-id="099c5-104">このセクションでは、LDAP (ライトウェイト ディレクトリ アクセス プロトコル) 経由での電子メール アドレスにクエリを実行し、BizTalk Server SMTP アダプタを使用してエンドポイントを解決する電子メール メッセージを送信する旅程を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="099c5-104">This section demonstrates how to create an itinerary that queries an e-mail address through LDAP (Lightweight Directory Access Protocol) and then sends an e-mail message to the resolved endpoint using the BizTalk Server SMTP adapter.</span></span>  
  
 <span data-ttu-id="099c5-105">このトピックでは、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="099c5-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="099c5-106">LDAP クエリを使用してメッセージを動的にルーティングする itinerary 回覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="099c5-106">Create an itinerary routing slip to dynamically route a message using an LDAP query.</span></span>  
  
-   <span data-ttu-id="099c5-107">行程テスト用クライアントのサンプル アプリケーションを使用して旅程をテストします。</span><span class="sxs-lookup"><span data-stu-id="099c5-107">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="099c5-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="099c5-108">Prerequisites</span></span>  
 <span data-ttu-id="099c5-109">この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)です。</span><span class="sxs-lookup"><span data-stu-id="099c5-109">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
 <span data-ttu-id="099c5-110">このセクションを完了するが、コンピューターに Microsoft Active Directory ディレクトリ サービスを構成しを実行している必要があります (にないために必要なコンピューターがドメイン コント ローラーがドメインに接続されている必要があります)。</span><span class="sxs-lookup"><span data-stu-id="099c5-110">The computer on which you will complete this section must have Microsoft Active Directory directory service configured and running (it is not required that the computer is the domain controller, but it must be connected to the domain).</span></span> <span data-ttu-id="099c5-111">また、SMTP サーバーがあります構成され、実行中です。このトピックの結果をテストするために、ESB によって送信された電子メールをチェックすると、クライアントが必要です。</span><span class="sxs-lookup"><span data-stu-id="099c5-111">Also, an SMTP server must be configured and running; in order to test the outcome of this How-to topic, you must have a client with which to check the e-mail sent by the ESB.</span></span>  
  
 <span data-ttu-id="099c5-112">このセクションの手順には、組織 globalbank.com のドメインと、Active Directory Employees という名前を含む組織単位 (など、プロファイル内の有効な電子メールアドレスにJohnEvansをという名前のユーザーとグローバルBankをという名前が想定していますjohne@globalbank.com).</span><span class="sxs-lookup"><span data-stu-id="099c5-112">The instructions in this section assume an organization named Global Bank, with a domain of globalbank.com, with an Active Directory Organizational Unit named Employees that contains a user named John Evans with a valid e-mail address in his profile (such as johne@globalbank.com).</span></span> <span data-ttu-id="099c5-113">これらの環境的要因をレプリケートする必要はありません。ただし、環境内には、この実装を再作成するためには、これらの要因を考慮してください、必要に応じて置換を行います。</span><span class="sxs-lookup"><span data-stu-id="099c5-113">It is not necessary to replicate these environmental factors; however, for purposes of recreating this implementation in your environment, please account for these factors and make substitutions as necessary.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="099c5-114">手順</span><span class="sxs-lookup"><span data-stu-id="099c5-114">Steps</span></span>  
  
#### <a name="to-create-an-esb-itinerary-domain-specific-language-dsl-model"></a><span data-ttu-id="099c5-115">ESB itinerary ドメイン固有言語 (DSL) モデルを作成するには</span><span class="sxs-lookup"><span data-stu-id="099c5-115">To create an ESB itinerary domain-specific language (DSL) model</span></span>  
  
1.  <span data-ttu-id="099c5-116">Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="099c5-116">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="099c5-117">ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントし、**追加**、クリックして**新しい行程**です。</span><span class="sxs-lookup"><span data-stu-id="099c5-117">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="099c5-118">**新しい項目の追加** ダイアログ ボックスで、「 **LdapResolution**で、**名前**ボックスをクリックしてして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="099c5-118">In the **Add New Item** dialog box, type **LdapResolution** in the **Name** box, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="099c5-119">旅行計画のプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="099c5-119">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="099c5-120">Visual Studio でのデザイン画面をクリックして**LdapResolution.itinerary**です。</span><span class="sxs-lookup"><span data-stu-id="099c5-120">In Visual Studio, click the design surface of **LdapResolution.itinerary**.</span></span> <span data-ttu-id="099c5-121">**LdapResolution**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="099c5-121">In the **LdapResolution** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="099c5-122">**モデル エクスポーター**ドロップダウン リストをクリックして**XML 行程エクスポーター**です。</span><span class="sxs-lookup"><span data-stu-id="099c5-122">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="099c5-123">下にある、 **Extender の設定**セクションで、次に、**行程 XML ファイル**プロパティ、省略記号ボタン (...) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="099c5-123">Under the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="099c5-124">**[XML ファイルの**] ダイアログ ボックスで、「 **C:\HowTos\Itineraries\LdapResolution**で、**ファイル名**ボックスをクリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="099c5-124">In the **Select XML File** dialog box, type **C:\HowTos\Itineraries\LdapResolution** in the **File name** box, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="099c5-125">この手順では、旅行計画をローカル ファイルの場所に XML としてエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="099c5-125">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="099c5-126">代わりに、ローカル ファイルの場所に日程を itinerary のデータベースにエクスポートして ESB のテスト用クライアント アプリケーションを使用して旅行計画のテストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="099c5-126">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="099c5-127">このトピックの後半には、このプロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="099c5-127">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="099c5-128">旅行計画の構造を定義するには</span><span class="sxs-lookup"><span data-stu-id="099c5-128">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="099c5-129">ツールボックスからドラッグして、**入り口**デザイン画面にモデル要素。</span><span class="sxs-lookup"><span data-stu-id="099c5-129">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="099c5-130">**OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="099c5-130">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="099c5-131">クリックして、**名前**プロパティ、および入力**ReceiveNAOrder**です。</span><span class="sxs-lookup"><span data-stu-id="099c5-131">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="099c5-132">**Extender**ドロップダウン リストをクリックして**入り口 ESB Extender**です。</span><span class="sxs-lookup"><span data-stu-id="099c5-132">In the **Extender** drop-down list, click **On-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="099c5-133">**BizTalk アプリケーション**ドロップダウン リストをクリックして**Microsoft.Practices.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="099c5-133">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="099c5-134">**受信ポート**ドロップダウン リストをクリックして**OnRamp.Itinerary**です。</span><span class="sxs-lookup"><span data-stu-id="099c5-134">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="099c5-135">ツールボックスからドラッグ、**行程サービス**デザイン画面に要素をモデル化の右側に配置し、**入り口**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="099c5-135">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **On-Ramp** model element.</span></span> <span data-ttu-id="099c5-136">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="099c5-136">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="099c5-137">クリックして、**名前**プロパティ、および入力**RouteMessageEmail**です。</span><span class="sxs-lookup"><span data-stu-id="099c5-137">Click the **Name** property, and then type **RouteMessageEmail**.</span></span>  
  
    2.  <span data-ttu-id="099c5-138">**行程サービス エクステンダー**ドロップダウン リストをクリックして**エクステンダーのメッセージング**です。</span><span class="sxs-lookup"><span data-stu-id="099c5-138">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="099c5-139">このプロパティは、あるプロセスで行われます (メッセージング) パイプラインを定義します。</span><span class="sxs-lookup"><span data-stu-id="099c5-139">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="099c5-140">または、プロセスは、オーケストレーションで行われます、設定、**行程サービス エクステンダー**プロパティを**オーケストレーション Extender**です。</span><span class="sxs-lookup"><span data-stu-id="099c5-140">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="099c5-141">**コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、クリックして**受信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="099c5-141">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="099c5-142">**サービス名**ドロップダウン リストをクリックして**Microsoft.Practices.ESB.Services.Routing**です。</span><span class="sxs-lookup"><span data-stu-id="099c5-142">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
3.  <span data-ttu-id="099c5-143">右クリックし、**リゾルバー**のコレクション、 **RouteMessageEmail**モデル要素をクリックして**新しいリゾルバーを追加**です。</span><span class="sxs-lookup"><span data-stu-id="099c5-143">Right-click the **Resolver** collection of the **RouteMessageEmail** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="099c5-144">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="099c5-144">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="099c5-145">クリックして、**名前**プロパティ、および入力**LdapResolver**です。</span><span class="sxs-lookup"><span data-stu-id="099c5-145">Click the **Name** property, and then type **LdapResolver**.</span></span>  
  
    2.  <span data-ttu-id="099c5-146">**リゾルバーの実装**ドロップダウン リストをクリックして**LDAP 競合回避モジュールの拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="099c5-146">In the **Resolver Implementation** drop-down list, click **LDAP Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="099c5-147">**トランスポート名**ドロップダウン リストをクリックして**SMTP**です。</span><span class="sxs-lookup"><span data-stu-id="099c5-147">In the **Transport Name** drop-down list, click **SMTP**.</span></span>  
  
    4.  <span data-ttu-id="099c5-148">クリックして、**トランスポート場所**プロパティ、および入力**{メール}**</span><span class="sxs-lookup"><span data-stu-id="099c5-148">Click the **Transport Location** property, and then type **{mail}**</span></span>  
  
    5.  <span data-ttu-id="099c5-149">クリックして、 **SearchRoot**プロパティ、および入力**ou = 従業員、dc = globalbank、dc = com**</span><span class="sxs-lookup"><span data-stu-id="099c5-149">Click the **SearchRoot** property, and then type **ou=Employees,dc=globalbank,dc=com**</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="099c5-150">「前提条件」セクションで、仕様に従って環境を設定してされていない場合は、環境に適しているもので、上記プロパティ値を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="099c5-150">If you have not set up your environment according to the specifications in the "Prerequisites" section, replace the values in the preceding property with ones that are appropriate for your environment.</span></span>  
  
    6.  <span data-ttu-id="099c5-151">をクリックして、**フィルター**プロパティに値を変更し、 **(&(objectClass=User) (&#124;(givenName=john)))**</span><span class="sxs-lookup"><span data-stu-id="099c5-151">Click the **Filter** property, and then change the value to **(&(objectClass=User)(&#124;(givenName=john)))**</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="099c5-152">既存のテキストを置き換える前の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="099c5-152">Type the preceding value to replace the existing text.</span></span>  
  
    7.  <span data-ttu-id="099c5-153">**ThrowErrorIfNotFound**ドロップダウン リストをクリックして**True**です。</span><span class="sxs-lookup"><span data-stu-id="099c5-153">In the **ThrowErrorIfNotFound** drop-down list, click **True**.</span></span>  
  
4.  <span data-ttu-id="099c5-154">[プロパティ] ウィンドウでをクリックして、**エンドポイント構成**プロパティ、省略記号ボタン (...) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="099c5-154">In the Properties window, click the **Endpoint Configuration** property, and then click the ellipsis button (...).</span></span>  
  
    1.  <span data-ttu-id="099c5-155">**エンドポイント構成**ダイアログ ボックスで、をクリックして、 **EmailBodyText**プロパティ、および入力**注文を処理する準備が**です。</span><span class="sxs-lookup"><span data-stu-id="099c5-155">In the **Endpoint Configuration** dialog box, click the **EmailBodyText** property, and then type **Order is ready to be processed**.</span></span>  
  
    2.  <span data-ttu-id="099c5-156">クリックして、**から**プロパティ、および入力 **orders@globalbank.com**です。</span><span class="sxs-lookup"><span data-stu-id="099c5-156">Click the **From** property, and then type **orders@globalbank.com**.</span></span>  
  
    3.  <span data-ttu-id="099c5-157">クリックして、 **MessagePartsAttachment**プロパティ、および入力**2**です。</span><span class="sxs-lookup"><span data-stu-id="099c5-157">Click the **MessagePartsAttachment** property, and then type **2**.</span></span>  
  
    4.  <span data-ttu-id="099c5-158">クリックして、**サブジェクト**プロパティ、および入力**{givenName} の順序**です。</span><span class="sxs-lookup"><span data-stu-id="099c5-158">Click the **Subject** property, and then type **Order for {givenName}**.</span></span>  
  
    5.  <span data-ttu-id="099c5-159">構成、 **SMTPAuthentication、smtphost の各ユーザー名、**と**パスワード**プロパティは、ローカル環境の接続情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="099c5-159">Configure the **SMTPAuthentication, SMTPHost, UserName,** and **Password** properties using the connection information for your local environment.</span></span>  
  
    6.  <span data-ttu-id="099c5-160">をクリックして**OK**を閉じる、**エンドポイント構成** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="099c5-160">Click **OK** to close the **Endpoint Configuration** dialog box.</span></span>  
  
5.  <span data-ttu-id="099c5-161">右クリックし、 **LdapResolver**リゾルバーをクリックして**テスト構成の競合回避モジュール**です。</span><span class="sxs-lookup"><span data-stu-id="099c5-161">Right-click the **LdapResolver** resolver, and then click **Test Resolver Configuration**.</span></span>  
  
6.  <span data-ttu-id="099c5-162">[出力] ウィンドウで、解決済みの対象者を確認してください**エンドポイント構成**値は**john 順序**、ことを確認は解決された**トランスポート場所**は、。電子メール アドレスを Active Directory のユーザーのアカウントに関連付けられている (たとえば、 johne@globalbank.com)。</span><span class="sxs-lookup"><span data-stu-id="099c5-162">In the Output window, verify the subject in the resolved **Endpoint Configuration** value is **Order for John**, and then verify that the resolved **Transport Location** is the e-mail address associated with the user's account in Active Directory (for example, johne@globalbank.com).</span></span>  
  
7.  <span data-ttu-id="099c5-163">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="099c5-163">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="099c5-164">接続をドラッグして、 **ReceiveNAOrder**モデル要素を**RouteMessageEmail**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="099c5-164">Drag a connection from the **ReceiveNAOrder** model element to the **RouteMessageEmail** model element.</span></span>  
  
8.  <span data-ttu-id="099c5-165">ツールボックスからドラッグして、**出口**デザイン画面に要素をモデル化の右側に配置し、 **RouteMessageEmail**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="099c5-165">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **RouteMessageEmail** model element.</span></span> <span data-ttu-id="099c5-166">**OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="099c5-166">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="099c5-167">クリックして、**名前**プロパティ、および入力**EmailNAOrderDoc**です。</span><span class="sxs-lookup"><span data-stu-id="099c5-167">Click the **Name** property, and then type **EmailNAOrderDoc**.</span></span>  
  
    2.  <span data-ttu-id="099c5-168">**Extender**ドロップダウン リストをクリックして**出口 ESB Extender**です。</span><span class="sxs-lookup"><span data-stu-id="099c5-168">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="099c5-169">**BizTalk アプリケーション**ドロップダウン リストをクリックして**GlobalBank.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="099c5-169">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="099c5-170">**送信ポート**ドロップダウン リストをクリックして**DynamicResolutionOneWay**です。</span><span class="sxs-lookup"><span data-stu-id="099c5-170">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
9. <span data-ttu-id="099c5-171">ツールボックスからドラッグ、**行程サービス**モデルをデザイン画面に要素との間に配置し、 **RouteMessageEmail**モデル要素と**EmailNAOrderDoc**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="099c5-171">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **RouteMessageEmail** model element and the **EmailNAOrderDoc** model element.</span></span> <span data-ttu-id="099c5-172">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="099c5-172">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="099c5-173">クリックして、**名前**プロパティ、および入力**SendPortFilter**です。</span><span class="sxs-lookup"><span data-stu-id="099c5-173">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="099c5-174">**行程サービス エクステンダー**ドロップダウン リストをクリックして**出口 Extender**です。</span><span class="sxs-lookup"><span data-stu-id="099c5-174">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="099c5-175">**出口**ドロップダウン リストで、展開**EmailNAOrderDoc**、クリックして**送信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="099c5-175">In the **Off-Ramp** drop-down list, expand **EmailNAOrderDoc**, and then click **Send Handlers**.</span></span>  
  
10. <span data-ttu-id="099c5-176">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="099c5-176">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="099c5-177">接続をドラッグして、 **RouteMessageEmail**モデル要素を**SendPortFilter**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="099c5-177">Drag a connection from the **RouteMessageEmail** model element to the **SendPortFilter** model element.</span></span>  
  
11. <span data-ttu-id="099c5-178">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="099c5-178">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="099c5-179">接続をドラッグして、 **SendPortFilter**モデル要素を**EmailNAOrderDoc**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="099c5-179">Drag a connection from the **SendPortFilter** model element to the **EmailNAOrderDoc** model element.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="099c5-180">行程テスト クライアントで使用するモデルをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="099c5-180">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="099c5-181">Visual Studio でのデザイン画面を右クリックし、 **LdapResolution**行程をクリックして**モデルのエクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="099c5-181">In Visual Studio, right-click the design surface of the **LdapResolution** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="099c5-182">旅行計画の XML バージョンは、Visual Studio で開きます。</span><span class="sxs-lookup"><span data-stu-id="099c5-182">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="099c5-183">すべてのプロジェクトの成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="099c5-183">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="099c5-184">Windows エクスプローラで、C:\HowTos\Itineraries を参照し、行程 XML (LdapResolution.xml) の作成に注意してください。</span><span class="sxs-lookup"><span data-stu-id="099c5-184">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (LdapResolution.xml).</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="099c5-185">旅行計画をテストするには</span><span class="sxs-lookup"><span data-stu-id="099c5-185">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="099c5-186">中に作成されたショートカットを使用して行程テスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB です。Itinerary.Test.exe - ショートカット)。</span><span class="sxs-lookup"><span data-stu-id="099c5-186">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="099c5-187">行程テスト クライアントで、クリア、**を使用して WCF サービス**チェック ボックスをクリックして**ロード行程**です。</span><span class="sxs-lookup"><span data-stu-id="099c5-187">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="099c5-188">**行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。</span><span class="sxs-lookup"><span data-stu-id="099c5-188">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="099c5-189">選択**LdapResolution.xml**、順にクリック**開く**日程を読み込めません。</span><span class="sxs-lookup"><span data-stu-id="099c5-189">Select **LdapResolution.xml**, and then click **Open** to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="099c5-190">をクリックして**OK**をクリアする、**行程が正常に読み込まれる**メッセージ。</span><span class="sxs-lookup"><span data-stu-id="099c5-190">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
5.  <span data-ttu-id="099c5-191">行程テスト クライアントで、横にある省略記号ボタン (...) をクリックして、**メッセージの読み込み**ボックス。</span><span class="sxs-lookup"><span data-stu-id="099c5-191">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="099c5-192">**選択読み込む XML ドキュメントを** ダイアログ ボックスで、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="099c5-192">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="099c5-193">選択**NAOrderDoc.xml**、順にクリック**開く**テスト メッセージを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="099c5-193">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="099c5-194">クリックして、**要求を提出**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="099c5-194">Click the **Submit Request** button.</span></span> <span data-ttu-id="099c5-195">テストが完了したらをクリックして**OK**表示される確認メッセージを破棄します。</span><span class="sxs-lookup"><span data-stu-id="099c5-195">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
8.  <span data-ttu-id="099c5-196">Microsoft Outlook Express (または任意のメール クライアント) を開くし、John Evans の電子メールへのメッセージの配信を確認してください。</span><span class="sxs-lookup"><span data-stu-id="099c5-196">Open Microsoft Outlook Express (or the mail client of your choice) and verify delivery of the message to the e-mail of John Evans.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="099c5-197">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="099c5-197">Additional Resources</span></span>  
 <span data-ttu-id="099c5-198">詳細については、次の関連項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="099c5-198">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="099c5-199">開発アクティビティ</span><span class="sxs-lookup"><span data-stu-id="099c5-199">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="099c5-200">動的な解決とルーティングを利用する</span><span class="sxs-lookup"><span data-stu-id="099c5-200">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)