---
title: '方法: 3.0 uddi サービスを発行レジストリ |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2c3bd0ed-e5f1-43eb-98d1-e3247a565ba2
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da3d2dc400c031ab5febda1568cb18ce5180366b
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009915"
---
# <a name="how-to-publish-a-service-to-the-uddi-30-registry"></a><span data-ttu-id="a50fb-102">方法: 3.0 uddi サービスを発行レジストリ</span><span class="sxs-lookup"><span data-stu-id="a50fb-102">How to: Publish a Service to the UDDI 3.0 Registry</span></span>
## <a name="goal"></a><span data-ttu-id="a50fb-103">[目標]</span><span class="sxs-lookup"><span data-stu-id="a50fb-103">Goal</span></span>  
 <span data-ttu-id="a50fb-104">このセクションでは、UDDI サービス サイトを使用して、ESB メッセージをルーティングするために、行程内から解決できる Web サービスのエンドポイントを公開する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a50fb-104">This section demonstrates how to use the UDDI Service site to publish a Web service endpoint that can be resolved from within an itinerary for the purpose of routing an ESB message.</span></span> <span data-ttu-id="a50fb-105">既存の PurchaseOrderSubmitOrderService サービス レジストリに現在発行が複製されます。</span><span class="sxs-lookup"><span data-stu-id="a50fb-105">You will duplicate the existing PurchaseOrderSubmitOrderService service presently published to the registry.</span></span>  
  
 <span data-ttu-id="a50fb-106">このトピックでは、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="a50fb-106">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="a50fb-107">Universal Description, Discovery, and Integration (UDDI) 3 に、サービスを発行レジストリ UDDI 発行者のツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="a50fb-107">Publish a service to the Universal Description, Discovery, and Integration (UDDI) 3 registry using the UDDI Publisher tool.</span></span>  
  
-   <span data-ttu-id="a50fb-108">UDDI3 競合回避モジュールを使用してサービス エンドポイントを解決する itinerary 回覧を使用してサービスの公開をテストします。</span><span class="sxs-lookup"><span data-stu-id="a50fb-108">Test the service publication using an itinerary routing slip that resolves the service endpoint using a UDDI3 resolver.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a50fb-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="a50fb-109">Prerequisites</span></span>  
 <span data-ttu-id="a50fb-110">この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)と (でインストールできるように、%esb インストール Folder%\Bin\ UDDI 発行者のツールの実行Microsoft.Practices.ESB.UDDIPublisher.exe)。</span><span class="sxs-lookup"><span data-stu-id="a50fb-110">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) and the execution of the UDDI Publisher tool (you can install it at %ESB Install Folder%\Bin\Microsoft.Practices.ESB.UDDIPublisher.exe).</span></span>  
  
## <a name="steps"></a><span data-ttu-id="a50fb-111">手順</span><span class="sxs-lookup"><span data-stu-id="a50fb-111">Steps</span></span>  
  
#### <a name="to-create-the-newposervice-in-the-uddi-registry"></a><span data-ttu-id="a50fb-112">UDDI レジストリで、NewPOService を作成するには</span><span class="sxs-lookup"><span data-stu-id="a50fb-112">To create the NewPOService in the UDDI registry</span></span>  
  
1.  <span data-ttu-id="a50fb-113">Internet Explorer で、UDDI サービス サイトを参照 (既定では、この URL は http://localhost/uddi)。</span><span class="sxs-lookup"><span data-stu-id="a50fb-113">In Internet Explorer, browse to the UDDI Service site (by default, the URL for this is http://localhost/uddi).</span></span>  
  
2.  <span data-ttu-id="a50fb-114">**Uddi Services** ] ページで [**発行**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-114">On the **uddi Services** page, click **Publish**.</span></span>  
  
3.  <span data-ttu-id="a50fb-115">発行のウィンドウで  **Microsoft.Practices.ESB**、順にクリック**サービスの追加**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-115">In the Publish pane, right-click **Microsoft.Practices.ESB**, and then click **Add Service**.</span></span>  
  
4.  <span data-ttu-id="a50fb-116">次のページで次のように選択します。**を使用するキーを指定**、クリックして**続行**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-116">On the following page, select **Specify a key to use**, and then click **Continue**.</span></span>  
  
5.  <span data-ttu-id="a50fb-117">次のページでは、をクリックして、 **esb**パーティション キーです。</span><span class="sxs-lookup"><span data-stu-id="a50fb-117">On the following page, click the **esb** key partition.</span></span> <span data-ttu-id="a50fb-118">**キー サフィックス**ボックスに、入力**newposervice**、クリックして**続行**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-118">In the **Key Suffix** box, type **newposervice**, and then click **Continue**.</span></span>  
  
6.  <span data-ttu-id="a50fb-119">次のページの横に (**新しいサービス名前**)、 をクリックして**編集**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-119">On the following page, next to (**New Service Name**), click **Edit**.</span></span> <span data-ttu-id="a50fb-120">サービスの名前を付けます**NewPOService**、順にクリック**更新**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-120">Name the service **NewPOService**, and then click **Update**.</span></span>  
  
7.  <span data-ttu-id="a50fb-121">をクリックして**説明の追加**、サービスの説明を入力 (たとえば、**サンプル サービス**)、順にクリック**更新**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-121">Click **Add Description**, type a description for the service (for example, **Sample Service**), and then click **Update**.</span></span>  
  
#### <a name="to-add-a-binding-for-the-newposervice"></a><span data-ttu-id="a50fb-122">NewPOService のバインディングを追加するには</span><span class="sxs-lookup"><span data-stu-id="a50fb-122">To add a binding for the NewPOService</span></span>  
  
1.  <span data-ttu-id="a50fb-123">クリックして、**バインド** タブをクリックして**バインドの追加**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-123">Click the **Bindings** tab, and then click **Add Binding**.</span></span>  
  
2.  <span data-ttu-id="a50fb-124">選択**を使用するキーを指定**、クリックして**続行**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-124">Select **Specify a key to use**, and then click **Continue**.</span></span>  
  
3.  <span data-ttu-id="a50fb-125">次のページでは、をクリックして、 **esb**パーティション キーです。</span><span class="sxs-lookup"><span data-stu-id="a50fb-125">On the following page, click the **esb** key partition.</span></span> <span data-ttu-id="a50fb-126">**キー サフィックス**ボックスに、入力**newposervicebinding**、クリックして**続行**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-126">In the **Key Suffix** box, type **newposervicebinding**, and then click **Continue**.</span></span>  
  
4.  <span data-ttu-id="a50fb-127">[**アクセス ポイント**、] をクリックして**編集**、次を完了します。</span><span class="sxs-lookup"><span data-stu-id="a50fb-127">Under **Access Point**, click **Edit**, and then complete the following:</span></span>  
  
    1.  <span data-ttu-id="a50fb-128">**アクセス ポイント**ボックスに、入力**http://localhost/ESB.CanadianServices/SubmitPOService.asmx**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-128">In the **Access Point** box, type **http://localhost/ESB.CanadianServices/SubmitPOService.asmx**.</span></span>  
  
    2.  <span data-ttu-id="a50fb-129">**の型を使用**ドロップダウン リストをクリックして**エンドポイント**、順にクリック**更新**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-129">In the **Use Type** drop-down list, click **endpoint**, and then click **Update**.</span></span>  
  
#### <a name="to-configure-the-binding-instance-information"></a><span data-ttu-id="a50fb-130">バインディングのインスタンス情報を構成するには</span><span class="sxs-lookup"><span data-stu-id="a50fb-130">To configure the binding instance information</span></span>  
  
1.  <span data-ttu-id="a50fb-131">クリックして、**インスタンス情報** タブをクリックして**インスタンス情報の追加**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-131">Click the **Instance Info** tab, and then click **Add Instance Info**.</span></span>  
  
2.  <span data-ttu-id="a50fb-132">**を含む tModel 名の検索**ボックスに、入力 **%esb**  をクリックし、**検索**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-132">In the **Search for tModel names containing** box, type **%esb%** and then click **Search**.</span></span>  
  
3.  <span data-ttu-id="a50fb-133">見つけてクリックして、 **tModel**の**transporttype**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-133">Locate and click the **tModel** for **transporttype**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a50fb-134">この手順の残りの手順を完了するには、は、1 ページ目と 2 ページ目の間で変更する必要可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a50fb-134">To complete the remaining steps in this procedure, you may be required to change between page 1 and page 2.</span></span>  
  
4.  <span data-ttu-id="a50fb-135">**説明**セクションで、**説明の追加**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-135">In the **Descriptions** section, click **Add Description**.</span></span>  
  
5.  <span data-ttu-id="a50fb-136">**説明**ボックスに、入力**ESB 行程使用するためのトランスポートの種類**、クリックして**更新**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-136">In the **Description** box, type **Transport Type for ESB Itinerary Use**, and then click **Update**.</span></span>  
  
6.  <span data-ttu-id="a50fb-137">クリックして、**インスタンスの詳細** タブをクリックして**編集**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-137">Click the **Instance Details** tab, and then click **Edit**.</span></span>  
  
7.  <span data-ttu-id="a50fb-138">**インスタンス パラメーター**ボックスに、入力**Wcf-basichttp**、クリックして**更新**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-138">In the **Instance Parameters** box, type **WCF-BasicHttp**, and then click **Update**.</span></span>  
  
8.  <span data-ttu-id="a50fb-139">**説明**セクションで、**説明の追加**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-139">In the **Descriptions** section, click **Add Description**.</span></span>  
  
9. <span data-ttu-id="a50fb-140">**説明**ボックスに、入力**HTTP トランスポートの基本的な WCF**、クリックして**更新**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-140">In the **Description** box, type **WCF Basic HTTP Transport**, and then click **Update**.</span></span>  
  
10. <span data-ttu-id="a50fb-141">[発行] ウィンドウで [ **NewPOService**、] をクリックして**http://localhost/esb.canadianservices/submitposervice.asmx**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-141">In the Publish pane, under **NewPOService**, click **http://localhost/esb.canadianservices/submitposervice.asmx**.</span></span>  
  
11. <span data-ttu-id="a50fb-142">**インスタンス情報** タブで、をクリックして**インスタンス情報の追加**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-142">On the **Instance Info** tab, click **Add Instance Info**.</span></span>  
  
12. <span data-ttu-id="a50fb-143">既に説明した手順を使用して、次の表に示した値に従って、次のインスタンス情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="a50fb-143">Using the steps described earlier, add the following instance information, according to the values shown in the following table.</span></span>  
  
    |<span data-ttu-id="a50fb-144">tModel</span><span class="sxs-lookup"><span data-stu-id="a50fb-144">tModel</span></span>|<span data-ttu-id="a50fb-145">Description</span><span class="sxs-lookup"><span data-stu-id="a50fb-145">Description</span></span>|<span data-ttu-id="a50fb-146">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a50fb-146">Parameter</span></span>|<span data-ttu-id="a50fb-147">パラメーターの説明</span><span class="sxs-lookup"><span data-stu-id="a50fb-147">Parameter description</span></span>|  
    |------------|-----------------|---------------|---------------------------|  
    |<span data-ttu-id="a50fb-148">microsoft-com:esb:runtimeresolution:messageexchangepattern</span><span class="sxs-lookup"><span data-stu-id="a50fb-148">microsoft-com:esb:runtimeresolution:messageexchangepattern</span></span>|<span data-ttu-id="a50fb-149">メッセージ交換パターン</span><span class="sxs-lookup"><span data-stu-id="a50fb-149">Message Exchange Pattern</span></span>|<span data-ttu-id="a50fb-150">双方向</span><span class="sxs-lookup"><span data-stu-id="a50fb-150">Two-Way</span></span>|<span data-ttu-id="a50fb-151">双方向の操作</span><span class="sxs-lookup"><span data-stu-id="a50fb-151">Two-way operation</span></span>|  
    |<span data-ttu-id="a50fb-152">microsoft-com:esb:runtimeresolution:cachetimeout</span><span class="sxs-lookup"><span data-stu-id="a50fb-152">microsoft-com:esb:runtimeresolution:cachetimeout</span></span>|<span data-ttu-id="a50fb-153">キャッシュのタイムアウト</span><span class="sxs-lookup"><span data-stu-id="a50fb-153">Cache Timeout</span></span>|<span data-ttu-id="a50fb-154">-1</span><span class="sxs-lookup"><span data-stu-id="a50fb-154">-1</span></span>|<span data-ttu-id="a50fb-155">現在無効になっています</span><span class="sxs-lookup"><span data-stu-id="a50fb-155">Currently disabled</span></span>|  
    |<span data-ttu-id="a50fb-156">microsoft-com:esb:runtimeresolution:jaxrpcresponse</span><span class="sxs-lookup"><span data-stu-id="a50fb-156">microsoft-com:esb:runtimeresolution:jaxrpcresponse</span></span>|<span data-ttu-id="a50fb-157">JaxRpcResponse</span><span class="sxs-lookup"><span data-stu-id="a50fb-157">JaxRpcResponse</span></span>|<span data-ttu-id="a50fb-158">オプション</span><span class="sxs-lookup"><span data-stu-id="a50fb-158">false</span></span>||  
    |<span data-ttu-id="a50fb-159">microsoft-com:esb:runtimeresolution:action</span><span class="sxs-lookup"><span data-stu-id="a50fb-159">microsoft-com:esb:runtimeresolution:action</span></span>|<span data-ttu-id="a50fb-160">サービス操作</span><span class="sxs-lookup"><span data-stu-id="a50fb-160">Service Action</span></span>|<span data-ttu-id="a50fb-161">submitOrder</span><span class="sxs-lookup"><span data-stu-id="a50fb-161">submitOrder</span></span>|<span data-ttu-id="a50fb-162">呼び出すサービス メソッドを指定します</span><span class="sxs-lookup"><span data-stu-id="a50fb-162">Specifies the service method to invoke</span></span>|  
    |<span data-ttu-id="a50fb-163">microsoft-com:esb:runtimeresolution:targetnamespace</span><span class="sxs-lookup"><span data-stu-id="a50fb-163">microsoft-com:esb:runtimeresolution:targetnamespace</span></span>|<span data-ttu-id="a50fb-164">Service Namespace</span><span class="sxs-lookup"><span data-stu-id="a50fb-164">Service Namespace</span></span>|<span data-ttu-id="a50fb-165">http://globalbank.esb.dynamicresolution.com/canadianservices</span><span class="sxs-lookup"><span data-stu-id="a50fb-165">http://globalbank.esb.dynamicresolution.com/canadianservices</span></span>|<span data-ttu-id="a50fb-166">ターゲットの名前空間</span><span class="sxs-lookup"><span data-stu-id="a50fb-166">Target namespace</span></span>|  
  
#### <a name="to-configure-the-binding-categorization"></a><span data-ttu-id="a50fb-167">バインディングの分類を構成するには</span><span class="sxs-lookup"><span data-stu-id="a50fb-167">To configure the binding categorization</span></span>  
  
1.  <span data-ttu-id="a50fb-168">[発行] ウィンドウで [ **NewPOService**、] をクリックして**http://localhost/esb.canadianservices/submitposervice.asmx**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-168">In the Publish pane, under **NewPOService**, click **http://localhost/esb.canadianservices/submitposervice.asmx**.</span></span>  
  
2.  <span data-ttu-id="a50fb-169">**カテゴリ** タブで、をクリックして**カスタム カテゴリの追加**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-169">On the **Categories** tab, click **Add Custom Category**.</span></span>  
  
3.  <span data-ttu-id="a50fb-170">**検索**ボックスに、入力 **%esb**  をクリックし、**検索**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-170">In the **Search** box, type **%esb%** and then click **Search**.</span></span>  
  
4.  <span data-ttu-id="a50fb-171">見つけてクリックして、 **microsoft-com:esb:runtimeresolution:biztalkapplication** tModel です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-171">Locate and click the **microsoft-com:esb:runtimeresolution:biztalkapplication** tModel.</span></span>  
  
5.  <span data-ttu-id="a50fb-172">**キー名**ボックスに、入力**BizTalk アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-172">In the **Key Name** box, type **BizTalk Application**.</span></span>  
  
6.  <span data-ttu-id="a50fb-173">**キー値**ボックスに、入力**Microsoft.Practices.ESB**、クリックして**カテゴリの追加**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-173">In the **Key Value** box, type **Microsoft.Practices.ESB**, and then click **Add Category**.</span></span>  
  
7.  <span data-ttu-id="a50fb-174">既に説明した手順を使用して、次の表に示した値に従って、次のカスタム カテゴリを追加します。</span><span class="sxs-lookup"><span data-stu-id="a50fb-174">Using the steps described earlier, add the following custom categories, according to the values shown in the following table.</span></span>  
  
    |<span data-ttu-id="a50fb-175">tModel</span><span class="sxs-lookup"><span data-stu-id="a50fb-175">tModel</span></span>|<span data-ttu-id="a50fb-176">キー名</span><span class="sxs-lookup"><span data-stu-id="a50fb-176">Key name</span></span>|<span data-ttu-id="a50fb-177">キーの値</span><span class="sxs-lookup"><span data-stu-id="a50fb-177">Key value</span></span>|  
    |------------|--------------|---------------|  
    |<span data-ttu-id="a50fb-178">microsoft-com:esb:runtimeresolution:portname</span><span class="sxs-lookup"><span data-stu-id="a50fb-178">microsoft-com:esb:runtimeresolution:portname</span></span>|<span data-ttu-id="a50fb-179">ポート名</span><span class="sxs-lookup"><span data-stu-id="a50fb-179">Port Name</span></span>|<span data-ttu-id="a50fb-180">NewPOService</span><span class="sxs-lookup"><span data-stu-id="a50fb-180">NewPOService</span></span>|  
    |<span data-ttu-id="a50fb-181">microsoft-com:esb:runtimeresolution:transporttype</span><span class="sxs-lookup"><span data-stu-id="a50fb-181">microsoft-com:esb:runtimeresolution:transporttype</span></span>|<span data-ttu-id="a50fb-182">トランスポートの種類</span><span class="sxs-lookup"><span data-stu-id="a50fb-182">Transport Type</span></span>|<span data-ttu-id="a50fb-183">WCF-BasicHttp</span><span class="sxs-lookup"><span data-stu-id="a50fb-183">WCF-BasicHttp</span></span>|  
  
#### <a name="to-locate-the-service-in-the-uddi-registry"></a><span data-ttu-id="a50fb-184">UDDI レジストリ内でサービスを検索するには</span><span class="sxs-lookup"><span data-stu-id="a50fb-184">To locate the service in the UDDI registry</span></span>  
  
1.  <span data-ttu-id="a50fb-185">Internet Explorer で、上、 **uddi サービス**] ページで [**検索**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-185">In Internet Explorer, on the **uddi Services** page, click **Search**.</span></span>  
  
2.  <span data-ttu-id="a50fb-186">クリックして、 **Services**タブです。</span><span class="sxs-lookup"><span data-stu-id="a50fb-186">Click the **Services** tab.</span></span>  
  
3.  <span data-ttu-id="a50fb-187">**サービス名**ボックスに、入力 **%po**、クリックして**検索**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-187">In the **Service Name** box, type **%PO%**, and then click **Search**.</span></span>  
  
4.  <span data-ttu-id="a50fb-188">**検索** ウィンドウで、**結果** タブで、をクリックして**NewPOService**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-188">In the **Search** pane, on the **Results** tab, click **NewPOService**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a50fb-189">これは、サービスがレジストリに正常に発行されたを確認します。</span><span class="sxs-lookup"><span data-stu-id="a50fb-189">This confirms the service was successfully published to the registry.</span></span>  
  
#### <a name="to-create-an-itinerary-model-to-test-the-uddi-service-publication"></a><span data-ttu-id="a50fb-190">UDDI サービスの公開をテストする itinerary モデルを作成するには</span><span class="sxs-lookup"><span data-stu-id="a50fb-190">To create an itinerary model to test the UDDI service publication</span></span>  
  
1.  <span data-ttu-id="a50fb-191">Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="a50fb-191">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="a50fb-192">ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントし、**追加**、クリックして**新しい行程**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-192">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="a50fb-193">**新しい項目の追加** ダイアログ ボックスで、**名前**ボックスに、入力**NewBindingKeySearch**、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-193">In the **Add New Item** dialog box, in the **Name** box, type **NewBindingKeySearch**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="a50fb-194">旅行計画のプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="a50fb-194">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="a50fb-195">Visual Studio でのデザイン画面をクリックして**NewBindingKeySearch.itinerary**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-195">In Visual Studio, click the design surface of **NewBindingKeySearch.itinerary**.</span></span> <span data-ttu-id="a50fb-196">**NewBindingKeySearch**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="a50fb-196">In the **NewBindingKeySearch** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a50fb-197">**は要求の応答**ドロップダウン リストをクリックして**True**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-197">In the **Is Request Response** drop-down list, click **True**.</span></span>  
  
    2.  <span data-ttu-id="a50fb-198">**モデル エクスポーター**ドロップダウン リストをクリックして**XML 行程エクスポーター**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-198">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    3.  <span data-ttu-id="a50fb-199">**Extender 設定**セクションで、横に、**行程 XML ファイル**プロパティ、省略記号ボタン (...) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a50fb-199">In the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    4.  <span data-ttu-id="a50fb-200">**[XML ファイルの**] ダイアログ ボックスで、「 **C:\HowTos\Itineraries\NewBindingKeySearch**で、**ファイル名**ボックスをクリックして**を保存**.</span><span class="sxs-lookup"><span data-stu-id="a50fb-200">In the **Select XML File** dialog box, type **C:\HowTos\Itineraries\NewBindingKeySearch** in the **File name** box, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="a50fb-201">この手順では、旅行計画をローカル ファイルの場所に XML としてエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="a50fb-201">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="a50fb-202">代わりに、ローカル ファイルの場所に日程を itinerary のデータベースにエクスポートして ESB のテスト用クライアント アプリケーションを使用して旅行計画のテストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a50fb-202">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="a50fb-203">このトピックの後半には、このプロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="a50fb-203">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="a50fb-204">旅行計画の構造を定義するには</span><span class="sxs-lookup"><span data-stu-id="a50fb-204">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="a50fb-205">ツールボックスからドラッグして、**入り口**デザイン画面にモデル要素。</span><span class="sxs-lookup"><span data-stu-id="a50fb-205">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="a50fb-206">**OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="a50fb-206">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a50fb-207">クリックして、**名前**プロパティ、および入力**ReceiveNAOrder**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-207">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="a50fb-208">**Extender**ドロップダウン リストをクリックして**入り口 ESB Extender**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-208">In the **Extender** drop-down list, click **On-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="a50fb-209">**BizTalk アプリケーション**ドロップダウン リストをクリックして**Microsoft.Practices.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-209">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="a50fb-210">**受信ポート**ドロップダウン リストをクリックして**OnRamp.Itinerary.Response**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-210">In the **Receive Port** drop-down list, click **OnRamp.Itinerary.Response**.</span></span>  
  
2.  <span data-ttu-id="a50fb-211">ツールボックスからドラッグして、**行程サービス**デザイン画面にモデル要素。</span><span class="sxs-lookup"><span data-stu-id="a50fb-211">From the Toolbox, drag an **Itinerary Service** model element to the design surface.</span></span> <span data-ttu-id="a50fb-212">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="a50fb-212">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a50fb-213">クリックして、**名前**プロパティ、および入力**TransformNAOrder**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-213">Click the **Name** property, and then type **TransformNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="a50fb-214">**行程サービス エクステンダー**ドロップダウン リストをクリックして**エクステンダーのメッセージング**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-214">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
    3.  <span data-ttu-id="a50fb-215">**コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、クリックして**受信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-215">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="a50fb-216">**サービス名**ドロップダウン リストをクリックして**Microsoft.Practices.ESB.Services.Transform**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-216">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Transform**.</span></span>  
  
3.  <span data-ttu-id="a50fb-217">右クリックし、**リゾルバー**のコレクション、 **TransformNAOrder**モデル要素をクリックして**新しいリゾルバーを追加**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-217">Right-click the **Resolver** collection of the **TransformNAOrder** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="a50fb-218">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="a50fb-218">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a50fb-219">クリックして、**名前**プロパティ、および入力**NAOrder_to_CNOrder**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-219">Click the **Name** property, and then type **NAOrder_to_CNOrder**.</span></span>  
  
    2.  <span data-ttu-id="a50fb-220">**リゾルバーの実装**ドロップダウン リストをクリックして**静的競合回避モジュールの拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="a50fb-220">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="a50fb-221">**型の変換**ドロップダウン リストをクリックして**GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-221">In the **Transform Type** drop-down list, click **GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**.</span></span>  
  
4.  <span data-ttu-id="a50fb-222">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-222">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="a50fb-223">接続をドラッグして、 **ReceiveNAOrder**モデル要素を**TransformNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="a50fb-223">Drag a connection from the **ReceiveNAOrder** model element to the **TransformNAOrder** model element.</span></span>  
  
5.  <span data-ttu-id="a50fb-224">ツールボックスからドラッグして、**行程サービス**デザイン画面にモデル要素。</span><span class="sxs-lookup"><span data-stu-id="a50fb-224">From the Toolbox, drag an **Itinerary Service** model element to the design surface.</span></span> <span data-ttu-id="a50fb-225">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="a50fb-225">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a50fb-226">クリックして、**名前**プロパティ、および入力**BindingKeyRoute**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-226">Click the **Name** property, and then type **BindingKeyRoute**.</span></span>  
  
    2.  <span data-ttu-id="a50fb-227">**行程サービス エクステンダー**ドロップダウン リストをクリックして**エクステンダーのメッセージング**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-227">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
    3.  <span data-ttu-id="a50fb-228">**コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、クリックして**受信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-228">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="a50fb-229">**サービス名**ドロップダウン リストをクリックして**Microsoft.Practices.ESB.Services.Routing**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-229">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
6.  <span data-ttu-id="a50fb-230">右クリックし、**リゾルバー**のコレクション、 **BindingKeyRoute**モデル要素をクリックして**新しいリゾルバーを追加**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-230">Right-click the **Resolver** collection of the **BindingKeyRoute** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="a50fb-231">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="a50fb-231">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a50fb-232">クリックして、**名前**プロパティ、および入力**BindingKeySearch**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-232">Click the **Name** property, and then type **BindingKeySearch**.</span></span>  
  
    2.  <span data-ttu-id="a50fb-233">**リゾルバーの実装**ドロップダウン リストをクリックして**Uddi3 競合回避モジュールの拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="a50fb-233">In the **Resolver Implementation** drop-down list, click **Uddi3 Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="a50fb-234">**リゾルバー モニカー**ドロップダウン リストをクリックして**UDDI3**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-234">In the **Resolver Moniker** drop-down list, click **UDDI3**.</span></span>  
  
    4.  <span data-ttu-id="a50fb-235">クリックして、**バインド キー**プロパティ、および入力**uddi:esb:newposervicebinding**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-235">Click the **Binding key** property, and then type **uddi:esb:newposervicebinding**.</span></span> <span data-ttu-id="a50fb-236">キーの値を見つけて http://localhost/ESB.CanadianServices/SubmitPOService.asmx、UDDI サービスをクリックして [詳細設定] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a50fb-236">To find the key value, click the http://localhost/ESB.CanadianServices/SubmitPOService.asmx service in UDDI, and then click More Details.</span></span>  
  
7.  <span data-ttu-id="a50fb-237">右クリックし、 **BindingKeySearch**リゾルバーをクリックして**テスト構成の競合回避モジュール**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-237">Right-click the **BindingKeySearch** resolver, and then click **Test Resolver Configuration**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a50fb-238">出力ウィンドウに表示される出力を確認します。</span><span class="sxs-lookup"><span data-stu-id="a50fb-238">Verify the output displayed in the Output window.</span></span>  
  
8.  <span data-ttu-id="a50fb-239">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-239">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="a50fb-240">接続をドラッグして、 **TransformNAOrder**モデル要素を**BindingKeyRoute**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="a50fb-240">Drag a connection from the **TransformNAOrder** model element to the **BindingKeyRoute** model element.</span></span>  
  
9. <span data-ttu-id="a50fb-241">ツールボックスからドラッグして、**出口**デザイン画面に要素をモデル化の右側に配置し、 **BindingKeyRoute**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="a50fb-241">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **BindingKeyRoute** model element.</span></span> <span data-ttu-id="a50fb-242">**OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="a50fb-242">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a50fb-243">クリックして、**名前**プロパティ、および入力**SendCNOrder**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-243">Click the **Name** property, and then type **SendCNOrder**.</span></span>  
  
    2.  <span data-ttu-id="a50fb-244">**Extender**ドロップダウン リストをクリックして**出口 ESB Extender**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-244">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="a50fb-245">**BizTalk アプリケーション**ドロップダウン リストをクリックして**GlobalBank.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-245">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="a50fb-246">**送信ポート**ドロップダウン リストをクリックして**DynamicResolutionSolicitResp**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-246">In the **Send Port** drop-down list, click **DynamicResolutionSolicitResp**.</span></span>  
  
10. <span data-ttu-id="a50fb-247">ツールボックスからドラッグ、**行程サービス**モデルをデザイン画面に要素との間に配置し、 **BindingKeyRoute**モデル要素と**SendCNOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="a50fb-247">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **BindingKeyRoute** model element and the **SendCNOrder** model element.</span></span> <span data-ttu-id="a50fb-248">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="a50fb-248">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a50fb-249">クリックして、**名前**プロパティ、および入力**SendPortFilter**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-249">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="a50fb-250">**行程サービス エクステンダー**ドロップダウン リストをクリックして**出口 Extender**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-250">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="a50fb-251">**出口**ドロップダウン リストで、展開**SendCNOrder**、クリックして**送信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-251">In the **Off-Ramp** drop-down list, expand **SendCNOrder**, and then click **Send Handlers**.</span></span>  
  
11. <span data-ttu-id="a50fb-252">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-252">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="a50fb-253">接続をドラッグして、 **BindingKeyRoute**モデル要素を**SendPortFilter**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="a50fb-253">Drag a connection from the **BindingKeyRoute** model element to the **SendPortFilter** model element.</span></span>  
  
12. <span data-ttu-id="a50fb-254">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-254">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="a50fb-255">接続をドラッグして、 **SendPortFilter**モデル要素を**SendNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="a50fb-255">Drag a connection from the **SendPortFilter** model element to the **SendNAOrder** model element.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="a50fb-256">行程テスト クライアントで使用するモデルをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="a50fb-256">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="a50fb-257">Visual Studio でのデザイン画面を右クリックし、 **NewBindingKeySearch**行程をクリックして**モデルのエクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-257">In Visual Studio, right-click the design surface of the **NewBindingKeySearch** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a50fb-258">旅行計画の XML バージョンは、Visual Studio で開きます。</span><span class="sxs-lookup"><span data-stu-id="a50fb-258">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="a50fb-259">すべてのプロジェクトの成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="a50fb-259">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="a50fb-260">Windows エクスプローラで、C:\HowTos\Itineraries を参照し、行程 XML (NewBindingKeySearch.xml) の作成に注意してください。</span><span class="sxs-lookup"><span data-stu-id="a50fb-260">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (NewBindingKeySearch.xml).</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="a50fb-261">旅行計画をテストするには</span><span class="sxs-lookup"><span data-stu-id="a50fb-261">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="a50fb-262">中に作成されたショートカットを使用して行程テスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB です。Itinerary.Test.exe - ショートカット)。</span><span class="sxs-lookup"><span data-stu-id="a50fb-262">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="a50fb-263">行程テスト クライアントでの**Web サービスのオプション**グループ、クリア、**を使用して WCF サービス**ボックスし、、**双方向サービス**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="a50fb-263">In the Itinerary Test Client, in the **Web Service Options** group, clear the **Use WCF Service** box and then select the **Two-Way Service** check box.</span></span>  
  
3.  <span data-ttu-id="a50fb-264">クリックして、**ロード行程**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a50fb-264">Click the **Load Itinerary** button.</span></span>  
  
4.  <span data-ttu-id="a50fb-265">**行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。</span><span class="sxs-lookup"><span data-stu-id="a50fb-265">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="a50fb-266">選択**NewBindingKeySearch.xml**、順にクリック**開く**日程を読み込めません。</span><span class="sxs-lookup"><span data-stu-id="a50fb-266">Select **NewBindingKeySearch.xml**, and then click **Open** to load the itinerary.</span></span>  
  
5.  <span data-ttu-id="a50fb-267">をクリックして**OK**をクリアする、**行程が正常に読み込まれる**メッセージ。</span><span class="sxs-lookup"><span data-stu-id="a50fb-267">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
6.  <span data-ttu-id="a50fb-268">行程テスト クライアントで、横にある省略記号ボタン (...) をクリックして、**メッセージの読み込み**ボックス。</span><span class="sxs-lookup"><span data-stu-id="a50fb-268">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
7.  <span data-ttu-id="a50fb-269">**選択読み込む XML ドキュメントを** ダイアログ ボックスで、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="a50fb-269">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="a50fb-270">選択**NAOrderDoc.xml**、順にクリック**開く**テスト メッセージを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="a50fb-270">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  
  
8.  <span data-ttu-id="a50fb-271">クリックして、**要求を提出**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a50fb-271">Click the **Submit Request** button.</span></span> <span data-ttu-id="a50fb-272">テストが完了したらをクリックして**OK**表示される確認メッセージを破棄します。</span><span class="sxs-lookup"><span data-stu-id="a50fb-272">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
9. <span data-ttu-id="a50fb-273">正しい応答メッセージが表示されることを確認してください、**結果**のテキスト ボックス、 **Itineray テスト用クライアント**です。</span><span class="sxs-lookup"><span data-stu-id="a50fb-273">Verify that the correct response message appears in the **Result** text box of the **Itineray Test Client**.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="a50fb-274">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="a50fb-274">Additional Resources</span></span>  
 <span data-ttu-id="a50fb-275">詳細については、次の関連項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a50fb-275">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="a50fb-276">方法: UDDI バインド キー検索を利用し、サービス エンドポイントを解決する</span><span class="sxs-lookup"><span data-stu-id="a50fb-276">How to: Resolve a Service Endpoint Using a UDDI Binding Key Search</span></span>](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-binding-key-search.md)  
  
-   [<span data-ttu-id="a50fb-277">方法: UDDI カテゴリ検索を利用し、サービス エンドポイントを解決する</span><span class="sxs-lookup"><span data-stu-id="a50fb-277">How to: Resolve a Service Endpoint Using a UDDI Category Search</span></span>](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-category-search.md)  
  
-   [<span data-ttu-id="a50fb-278">開発アクティビティ</span><span class="sxs-lookup"><span data-stu-id="a50fb-278">Development Activities</span></span>](../esb-toolkit/development-activities.md)