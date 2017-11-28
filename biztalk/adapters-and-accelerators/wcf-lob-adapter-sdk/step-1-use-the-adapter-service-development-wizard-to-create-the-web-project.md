---
title: "手順 1: Web プロジェクトを作成するアダプター サービス開発ウィザードを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7ea0e33c-0d8d-4656-a6f0-3008b90f93f8
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a63953b0928915a8fea5b357722cd4e34f1b900c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-use-the-adapter-service-development-wizard-to-create-the-web-project"></a><span data-ttu-id="52289-102">手順 1: Web プロジェクトを作成するアダプター サービス開発ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="52289-102">Step 1: Use the Adapter Service Development Wizard to Create the Web Project</span></span>
<span data-ttu-id="52289-103">![4 のステップ 1](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span><span class="sxs-lookup"><span data-stu-id="52289-103">![Step 1 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span></span>  
  
 <span data-ttu-id="52289-104">**所要時間:** 10 分</span><span class="sxs-lookup"><span data-stu-id="52289-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="52289-105">この手順では、Visual Studio を使用してプロジェクトを作成し、[!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="52289-105">In this step, you create a project using Visual Studio and the [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)].</span></span> <span data-ttu-id="52289-106">[!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]アダプター、操作、およびエンドポイントの構成に関する情報を収集し、IIS に展開できる、Web プロジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="52289-106">The [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)] collects information about the adapter, operations, and endpoint configurations, and generates a Web project that can then be deployed to IIS.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="52289-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="52289-107">Prerequisites</span></span>  
 <span data-ttu-id="52289-108">ビルドおよびで説明されている Echo サンプルを配置する必要があります[チュートリアル 1: エコー アダプターを開発](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)このチュートリアルを開始する前にします。</span><span class="sxs-lookup"><span data-stu-id="52289-108">You must build and deploy the Echo sample described in [Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) before beginning this tutorial.</span></span>  
  
### <a name="to-start-the-adapter-service-development-wizard"></a><span data-ttu-id="52289-109">アダプター サービス開発ウィザードを開始するには</span><span class="sxs-lookup"><span data-stu-id="52289-109">To start the Adapter Service Development Wizard</span></span>  
  
1.  <span data-ttu-id="52289-110">Visual Studio を起動し、**ファイル** メニューのをポイント**新規**、クリックして**Web サイト**です。</span><span class="sxs-lookup"><span data-stu-id="52289-110">Start Visual Studio and then on the **File** menu, point to **New**, and then click **Web Site**.</span></span>  
  
2.  <span data-ttu-id="52289-111">**新しい Web サイト** ダイアログ ボックスで、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="52289-111">In the **New Web Site** dialog box, perform the following actions:</span></span>  
  
    |<span data-ttu-id="52289-112">プロパティ</span><span class="sxs-lookup"><span data-stu-id="52289-112">Use this</span></span>|<span data-ttu-id="52289-113">目的</span><span class="sxs-lookup"><span data-stu-id="52289-113">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="52289-114">**言語**</span><span class="sxs-lookup"><span data-stu-id="52289-114">**Language**</span></span>|<span data-ttu-id="52289-115">をクリックして**Visual c#**です。</span><span class="sxs-lookup"><span data-stu-id="52289-115">Click **Visual C#**.</span></span>|  
    |<span data-ttu-id="52289-116">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="52289-116">**Templates**</span></span>|<span data-ttu-id="52289-117">をクリックして**WCF アダプタ サービス**です。</span><span class="sxs-lookup"><span data-stu-id="52289-117">Click **WCF Adapter Service**.</span></span>|  
    |<span data-ttu-id="52289-118">**場所**</span><span class="sxs-lookup"><span data-stu-id="52289-118">**Location**</span></span>|<span data-ttu-id="52289-119">選択**ファイル システム**、し、入力**C:\Tutorials\EchoWeb**パスとして。</span><span class="sxs-lookup"><span data-stu-id="52289-119">Select **File System**, and then type **C:\Tutorials\EchoWeb** as the path.</span></span>|  
  
3.  <span data-ttu-id="52289-120">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52289-120">Click **OK**.</span></span>  
  
4.  <span data-ttu-id="52289-121">**へようこそ ページ**、 をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="52289-121">On the **Welcome page**, click **Next**.</span></span>  
  
### <a name="to-select-the-adapter-and-uri"></a><span data-ttu-id="52289-122">アダプターと URI を選択するには</span><span class="sxs-lookup"><span data-stu-id="52289-122">To select the adapter and URI</span></span>  
  
1.  <span data-ttu-id="52289-123">**サービス コントラクトを生成する操作を選択して**] ページで、[ **echoAdapterBindingV2**から、**バインディングを選択**ドロップダウン ボックスの一覧、および [ ]をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="52289-123">On the **Choose the operations to generate a service contract** page, select **echoAdapterBindingV2** from the **Select a binding** drop-down list, and then click **Configure**.</span></span>  
  
2.  <span data-ttu-id="52289-124">**セキュリティ**のタブ、**アダプターの構成**ダイアログ ボックスで、セット**クライアント資格情報の種類**に**ユーザー名**、を設定**ユーザー名資格情報**次のようにします。</span><span class="sxs-lookup"><span data-stu-id="52289-124">On the **Security** tab of the **Configure Adapter** dialog box, set **Client Credential type** to **Username**, and then set the **User name credentials** as follows:</span></span>  
  
    |<span data-ttu-id="52289-125">プロパティ</span><span class="sxs-lookup"><span data-stu-id="52289-125">Property</span></span>|<span data-ttu-id="52289-126">値</span><span class="sxs-lookup"><span data-stu-id="52289-126">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="52289-127">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="52289-127">**User name**</span></span>|<span data-ttu-id="52289-128">username</span><span class="sxs-lookup"><span data-stu-id="52289-128">username</span></span>|  
    |<span data-ttu-id="52289-129">**Password**</span><span class="sxs-lookup"><span data-stu-id="52289-129">**Password**</span></span>|<span data-ttu-id="52289-130">パスワード</span><span class="sxs-lookup"><span data-stu-id="52289-130">password</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="52289-131">ユーザー名とパスワードをここに入力は、ウィザードの手順を実行中に、アダプターへの接続にのみ使用し、ウィザードの完了後は保持されません。</span><span class="sxs-lookup"><span data-stu-id="52289-131">The user name and password entered here are only used to connect to the adapter while performing the steps in the wizard, and are not preserved after the wizard completes.</span></span>  
  
3.  <span data-ttu-id="52289-132">クリックして、 **URI プロパティ**タブをクリックし、次のようにプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="52289-132">Click the **URI Properties** tab, and then set the properties as follows:</span></span>  
  
    |<span data-ttu-id="52289-133">プロパティ</span><span class="sxs-lookup"><span data-stu-id="52289-133">Property</span></span>|<span data-ttu-id="52289-134">値</span><span class="sxs-lookup"><span data-stu-id="52289-134">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="52289-135">**アプリケーション**</span><span class="sxs-lookup"><span data-stu-id="52289-135">**Application**</span></span>|<span data-ttu-id="52289-136">LobApplication</span><span class="sxs-lookup"><span data-stu-id="52289-136">LobApplication</span></span>|  
    |<span data-ttu-id="52289-137">**EnableAuthentication**</span><span class="sxs-lookup"><span data-stu-id="52289-137">**EnableAuthentication**</span></span>|<span data-ttu-id="52289-138">True</span><span class="sxs-lookup"><span data-stu-id="52289-138">True</span></span>|  
    |<span data-ttu-id="52289-139">**ホスト名**</span><span class="sxs-lookup"><span data-stu-id="52289-139">**Hostname**</span></span>|<span data-ttu-id="52289-140">lobhostname</span><span class="sxs-lookup"><span data-stu-id="52289-140">lobhostname</span></span>|  
    |<span data-ttu-id="52289-141">**EchoInUpperCase**</span><span class="sxs-lookup"><span data-stu-id="52289-141">**EchoInUpperCase**</span></span>|<span data-ttu-id="52289-142">False</span><span class="sxs-lookup"><span data-stu-id="52289-142">False</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="52289-143">ここで選択した URI のプロパティは、作成に使用する、 \<**クライアント**>\<**エンドポイント**> web.config ファイル内の要素。</span><span class="sxs-lookup"><span data-stu-id="52289-143">The URI properties selected here will be used to create the \<**client**>\<**endpoint**> elements in the web.config file.</span></span>  
  
4.  <span data-ttu-id="52289-144">クリックして、**バインド プロパティ**タブです。クリックして、既定値に注意してください**OK**です。</span><span class="sxs-lookup"><span data-stu-id="52289-144">Click the **Binding Properties** tab. Note the default values, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="52289-145">バインディングの値の生成に使用される、 \<**バインド**>\<**echoAdapterBindingV2**> web.config ファイル内の要素。</span><span class="sxs-lookup"><span data-stu-id="52289-145">The binding values will be used to generate the \<**bindings**>\<**echoAdapterBindingV2**> elements in the web.config file.</span></span>  
  
### <a name="to-select-the-contract-and-operations"></a><span data-ttu-id="52289-146">コントラクトと操作を選択するには</span><span class="sxs-lookup"><span data-stu-id="52289-146">To select the contract and operations</span></span>  
  
1.  <span data-ttu-id="52289-147">**サービス コントラクトを生成する操作を選択して** ページで、をクリックして**接続**です。</span><span class="sxs-lookup"><span data-stu-id="52289-147">On the **Choose the operations to generate a service contract** page, click **Connect**.</span></span>  
  
2.  <span data-ttu-id="52289-148">**カテゴリを選択**ツリーで、選択**メイン カテゴリ**です。</span><span class="sxs-lookup"><span data-stu-id="52289-148">In the **Select a category** tree, select **Main Category**.</span></span> <span data-ttu-id="52289-149">これによって、**利用可能なカテゴリと操作** ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="52289-149">This populates the **Available categories and operations** list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="52289-150">検索用語を入力することも、**カテゴリで検索**検索用語が含まれているすべての操作を検索するフィールドです。</span><span class="sxs-lookup"><span data-stu-id="52289-150">You can also enter a search term in the **Search in category** field to find any operations that contain the search term.</span></span>  
  
3.  <span data-ttu-id="52289-151">**利用可能なカテゴリと操作**一覧で、[ **EchoGreetings** ] をクリック**追加**です。</span><span class="sxs-lookup"><span data-stu-id="52289-151">In the **Available categories and operations** list, select **EchoGreetings** and click **Add**.</span></span> <span data-ttu-id="52289-152">これにより、EchoGreetings 操作に、移動、**カテゴリと操作を追加** ボックスの一覧。</span><span class="sxs-lookup"><span data-stu-id="52289-152">This moves the EchoGreetings operation to the **Added categories and operations** list.</span></span> <span data-ttu-id="52289-153">ここで選択した操作は、ウィザードによって生成されたクライアント プロキシ コードをクライアント アプリケーションに公開されます。</span><span class="sxs-lookup"><span data-stu-id="52289-153">The operations selected here will be exposed to client applications through the client proxy code generated by the wizard.</span></span>  
  
     <span data-ttu-id="52289-154">![コントラクトと操作の選択](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/de497b32-c820-480f-84f3-a9d0d2ded86b.gif "de497b32-c820-480f-84f3-a9d0d2ded86b")</span><span class="sxs-lookup"><span data-stu-id="52289-154">![Select Contract and Operations](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/de497b32-c820-480f-84f3-a9d0d2ded86b.gif "de497b32-c820-480f-84f3-a9d0d2ded86b")</span></span>  
  
4.  <span data-ttu-id="52289-155">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52289-155">Click **Next**.</span></span>  
  
### <a name="to-configure-service-and-endpoint-behavior"></a><span data-ttu-id="52289-156">サービスとエンドポイントの動作を構成するには</span><span class="sxs-lookup"><span data-stu-id="52289-156">To configure service and endpoint behavior</span></span>  
  
1.  <span data-ttu-id="52289-157">**サービスとエンドポイント動作を構成する** ページで、次の値を入力**サービス動作構成**:</span><span class="sxs-lookup"><span data-stu-id="52289-157">On the **Configure service and endpoint behaviors** page, enter the following values for **Service Behavior Configuration**:</span></span>  
  
    |<span data-ttu-id="52289-158">プロパティ</span><span class="sxs-lookup"><span data-stu-id="52289-158">Property</span></span>|<span data-ttu-id="52289-159">値</span><span class="sxs-lookup"><span data-stu-id="52289-159">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="52289-160">**EnableMetadataExchange**</span><span class="sxs-lookup"><span data-stu-id="52289-160">**EnableMetadataExchange**</span></span>|<span data-ttu-id="52289-161">True</span><span class="sxs-lookup"><span data-stu-id="52289-161">True</span></span>|  
    |<span data-ttu-id="52289-162">**IncludeExceptionDetailsinFault**</span><span class="sxs-lookup"><span data-stu-id="52289-162">**IncludeExceptionDetailsinFault**</span></span>|<span data-ttu-id="52289-163">True</span><span class="sxs-lookup"><span data-stu-id="52289-163">True</span></span>|  
    |<span data-ttu-id="52289-164">**名前**</span><span class="sxs-lookup"><span data-stu-id="52289-164">**Name**</span></span>|<span data-ttu-id="52289-165">customServiceBehavior</span><span class="sxs-lookup"><span data-stu-id="52289-165">customServiceBehavior</span></span>|  
    |<span data-ttu-id="52289-166">**UseServiceCertificate**</span><span class="sxs-lookup"><span data-stu-id="52289-166">**UseServiceCertificate**</span></span>|<span data-ttu-id="52289-167">False</span><span class="sxs-lookup"><span data-stu-id="52289-167">False</span></span>|  
  
     <span data-ttu-id="52289-168">これらの値が、使用、 \< **serviceBehaviors**>。</span><span class="sxs-lookup"><span data-stu-id="52289-168">These values are used to populate the \<**serviceBehaviors**>.</span></span>  
  
2.  <span data-ttu-id="52289-169">次の値を入力**エンドポイント動作の構成**:</span><span class="sxs-lookup"><span data-stu-id="52289-169">Enter the following values for **Endpoint Behavior Configuration**:</span></span>  
  
    |<span data-ttu-id="52289-170">プロパティ</span><span class="sxs-lookup"><span data-stu-id="52289-170">Property</span></span>|<span data-ttu-id="52289-171">値</span><span class="sxs-lookup"><span data-stu-id="52289-171">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="52289-172">**名前**</span><span class="sxs-lookup"><span data-stu-id="52289-172">**Name**</span></span>|<span data-ttu-id="52289-173">customEndpointBehavior</span><span class="sxs-lookup"><span data-stu-id="52289-173">customEndpointBehavior</span></span>|  
    |<span data-ttu-id="52289-174">**AuthenticationType**</span><span class="sxs-lookup"><span data-stu-id="52289-174">**AuthenticationType**</span></span>|<span data-ttu-id="52289-175">**HTTPUsernamePassword**</span><span class="sxs-lookup"><span data-stu-id="52289-175">**HTTPUsernamePassword**</span></span>|  
    |<span data-ttu-id="52289-176">**UsernameHeader**</span><span class="sxs-lookup"><span data-stu-id="52289-176">**UsernameHeader**</span></span>|<span data-ttu-id="52289-177">MyUserHeader</span><span class="sxs-lookup"><span data-stu-id="52289-177">MyUserHeader</span></span>|  
    |<span data-ttu-id="52289-178">**PasswordHeader**</span><span class="sxs-lookup"><span data-stu-id="52289-178">**PasswordHeader**</span></span>|<span data-ttu-id="52289-179">MyPassHeader</span><span class="sxs-lookup"><span data-stu-id="52289-179">MyPassHeader</span></span>|  
  
     <span data-ttu-id="52289-180">これらの値を指定するため、 **adapterSecurityBridgeType**で、<**endpointBehaviors** web.confg 内の要素。</span><span class="sxs-lookup"><span data-stu-id="52289-180">These values will be used to specify the **adapterSecurityBridgeType** in the <**endpointBehaviors** element in web.confg.</span></span>  
  
     <span data-ttu-id="52289-181">![エンドポイント構成](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/3fd5784c-64e5-47c1-9a6f-10f12f77f726.gif "3fd5784c-64e5-47c1-9a6f-10f12f77f726")</span><span class="sxs-lookup"><span data-stu-id="52289-181">![Endpoint Configuration](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/3fd5784c-64e5-47c1-9a6f-10f12f77f726.gif "3fd5784c-64e5-47c1-9a6f-10f12f77f726")</span></span>  
  
3.  <span data-ttu-id="52289-182">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52289-182">Click **Next**</span></span>  
  
### <a name="to-configure-the-binding"></a><span data-ttu-id="52289-183">バインドを設定する</span><span class="sxs-lookup"><span data-stu-id="52289-183">To configure the binding</span></span>  
  
1.  <span data-ttu-id="52289-184">**サービス エンドポイントのバインディングとアドレスを構成する**] ページで、[、 **BindingConfiguration**内のエントリ**されたコントラクトのバインディングとアドレスを構成する**、および省略記号ボタンをクリックし、(**.**) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="52289-184">On the **Configure the service endpoint binding and address** page, select the **BindingConfiguration** entry in **Configure the address and binding for the contract**, and then click the ellipsis (**…**) button.</span></span>  
  
2.  <span data-ttu-id="52289-185">**のバインドのカスタマイズ**ダイアログ ボックスで、セット**モード**に**TransportWithMessageCredential**、クリックして**[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="52289-185">In the **Customize Binding** dialog box, set **Mode** to **TransportWithMessageCredential**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="52289-186">をクリックして**適用**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="52289-186">Click **Apply**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="52289-187">**概要**ページで、コントラクトと操作をこのプロジェクトの選択を確認し、をクリックして**完了**です。</span><span class="sxs-lookup"><span data-stu-id="52289-187">On the **Summary** page, review the contracts and operations selected for this project, and then click **Finish**.</span></span> <span data-ttu-id="52289-188">によって作成されたプロジェクト ファイルを含んでいる EchoWeb ソリューションが表示されるが、[!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52289-188">You will be presented with the EchoWeb solution, which contains the project files created by the [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="52289-189">でしただけは何ですか。</span><span class="sxs-lookup"><span data-stu-id="52289-189">What did I just do?</span></span>  
 <span data-ttu-id="52289-190">このステップで使用して、 [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)] Web を生成する、IIS に発行されると、プロジェクトでは、ホストで開発されたエコー アダプター[チュートリアル 1: エコー アダプターを開発](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)IIS で処理します。</span><span class="sxs-lookup"><span data-stu-id="52289-190">In this step, you used the [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)] to generate a Web project that, when published to IIS, will host the Echo Adapter developed in [Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) in the IIS process.</span></span> <span data-ttu-id="52289-191">作成された Web プロジェクトでは、選択した操作にアクセスする Web サービスと WCF のクライアントを許可します。</span><span class="sxs-lookup"><span data-stu-id="52289-191">The resulting Web project allows Web Services and WCF clients to access the selected operations.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="52289-192">次の手順</span><span class="sxs-lookup"><span data-stu-id="52289-192">Next Steps</span></span>  
 <span data-ttu-id="52289-193">をビルドし、Web プロジェクトの配置を続行[手順 2: Web プロジェクトの配置](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-deploy-the-web-project.md)</span><span class="sxs-lookup"><span data-stu-id="52289-193">To build and deploy the Web project, proceed to [Step 2: Deploy the Web Project](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-deploy-the-web-project.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52289-194">参照</span><span class="sxs-lookup"><span data-stu-id="52289-194">See Also</span></span>  
 [<span data-ttu-id="52289-195">チュートリアル 1: エコー アダプターを開発します。</span><span class="sxs-lookup"><span data-stu-id="52289-195">Tutorial 1: Develop the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)