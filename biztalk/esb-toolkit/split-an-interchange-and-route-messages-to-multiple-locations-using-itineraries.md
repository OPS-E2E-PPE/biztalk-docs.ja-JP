---
title: 操作方法:インターチェンジを分割し、個別のスケジュールを使用して複数のファイルの場所に作成されるメッセージをルーティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccd46bee-e4a1-4846-8bde-b0460bda1e72
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36287f22290f30b687e90e9a111a3ae79aa53d5e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65268905"
---
# <a name="how-to-split-an-interchange-and-route-the-resulting-messages-to-multiple-file-locations-using-distinct-itineraries"></a><span data-ttu-id="6aa88-102">操作方法:インターチェンジを分割し、個別のスケジュールを使用して複数のファイルの場所に作成されるメッセージをルーティング</span><span class="sxs-lookup"><span data-stu-id="6aa88-102">How to: Split an Interchange and Route the Resulting Messages to Multiple File Locations Using Distinct Itineraries</span></span>
## <a name="goal"></a><span data-ttu-id="6aa88-103">[目標]</span><span class="sxs-lookup"><span data-stu-id="6aa88-103">Goal</span></span>  
 <span data-ttu-id="6aa88-104">このセクションでは、ESB 入り口を使用するを作成する方法を示します、 **ItinerarySelectReceiveXml**の明細のパイプラインと受信インターチェンジを分割し、適切なルーティングを選択するパイプラインのコンポーネントを構成する方法メッセージごとに結果として得られる、メッセージ コンテキストに基づきます。</span><span class="sxs-lookup"><span data-stu-id="6aa88-104">This section demonstrates how to create an ESB on-ramp that uses the **ItinerarySelectReceiveXml** pipeline and how to configure the pipeline's components to split an inbound interchange and select the appropriate routing slip for each resulting message, based on message context.</span></span> <span data-ttu-id="6aa88-105">スケジュールの選択は、ビジネス ルール ポリシーを使用して解決して、顧客が存在するリージョンに基づいて異なる方法でメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="6aa88-105">Itinerary selection will be resolved using a business rules policy, and messages will be routed differently based on the region in which the customer resides.</span></span>  
  
 <span data-ttu-id="6aa88-106">このトピックでは、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="6aa88-106">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="6aa88-107">ESB 入り口 XML インターチェンジを分割するを作成します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-107">Create an ESB on-ramp that splits an XML interchange.</span></span>  
  
-   <span data-ttu-id="6aa88-108">ビジネス ルール ポリシーを使用して、適切なスケジュールを選択するスケジュール セレクターのパイプライン コンポーネントを構成します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-108">Configure the Itinerary Selector pipeline component to use a business rules policy to select the appropriate itinerary.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6aa88-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="6aa88-109">Prerequisites</span></span>  
 <span data-ttu-id="6aa88-110">この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-110">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="6aa88-111">はじめに</span><span class="sxs-lookup"><span data-stu-id="6aa88-111">Before You Begin</span></span>  
 <span data-ttu-id="6aa88-112">この操作方法に関するトピックの後半の手順を実行する前に、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-112">Complete the following tasks before you perform the steps later in this How-to topic:</span></span>  
  
-   <span data-ttu-id="6aa88-113">必要なアーティファクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-113">Create the required artifacts.</span></span>  
  
-   <span data-ttu-id="6aa88-114">パターンのソリューションをスキーマ プロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-114">Add a schemas project to the Patterns solution.</span></span>  
  
-   <span data-ttu-id="6aa88-115">成果物をスキーマ プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-115">Add the artifacts to the Schemas project.</span></span>  
  
-   <span data-ttu-id="6aa88-116">カスタム メッセージ プロパティを使用するスケジュールを選択する BRE ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-116">Create a BRE policy to select an itinerary using custom message properties.</span></span>  
  
-   <span data-ttu-id="6aa88-117">GlobalBank 西部の顧客の選択規則を追加します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-117">Add a selection rule for customer GlobalBank West.</span></span>  
  
-   <span data-ttu-id="6aa88-118">GlobalBank 東部の顧客の選択規則を追加します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-118">Add a selection rule for customer GlobalBank East.</span></span>  
  
-   <span data-ttu-id="6aa88-119">発行し、ポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-119">Publish and deploy the policy.</span></span>  
  
-   <span data-ttu-id="6aa88-120">GlobalBank 西部メッセージの ESB オンランプ ドメイン固有言語 (DSL) モデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-120">Create an ESB itinerary domain-specific language (DSL) model for GlobalBank West messages.</span></span>  
  
-   <span data-ttu-id="6aa88-121">GlobalBank 西部スケジュールのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-121">Configure the properties of the GlobalBank West itinerary.</span></span>  
  
-   <span data-ttu-id="6aa88-122">GlobalBank 西部旅行プランの構造を定義します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-122">Define the structure of the GlobalBank West itinerary.</span></span>  
  
-   <span data-ttu-id="6aa88-123">行程データベースを GlobalBank 西部モデルをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="6aa88-123">Export the GlobalBank West model to the itinerary database.</span></span>  
  
-   <span data-ttu-id="6aa88-124">GlobalBank 東部メッセージの ESB 行程 DSL モデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-124">Create an ESB itinerary DSL model for GlobalBank East messages.</span></span>  
  
-   <span data-ttu-id="6aa88-125">GlobalBank 東部スケジュールのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-125">Configure the properties of the GlobalBank East itinerary.</span></span>  
  
-   <span data-ttu-id="6aa88-126">GlobalBank 東部旅行プランの構造を定義します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-126">Define the structure of the GlobalBank East itinerary.</span></span>  
  
-   <span data-ttu-id="6aa88-127">行程データベースを GlobalBank 東部モデルをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="6aa88-127">Export the GlobalBank East model to the itinerary database.</span></span>  
  
     <span data-ttu-id="6aa88-128">次の手順では、これらの各方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-128">The following procedures describe how to do each of these.</span></span>  
  
#### <a name="to-create-the-required-artifacts"></a><span data-ttu-id="6aa88-129">必要なアーティファクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="6aa88-129">To create the required artifacts</span></span>  
  
1.  <span data-ttu-id="6aa88-130">Windows エクスプ ローラーでは、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-130">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="6aa88-131">OrderDocEnvelope.xsd という名前の新しいテキスト ドキュメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-131">Create a new text document named OrderDocEnvelope.xsd.</span></span>  
  
3.  <span data-ttu-id="6aa88-132">OrderDocEnvelope.xsd スキーマは、メモ帳で開きます。</span><span class="sxs-lookup"><span data-stu-id="6aa88-132">Open the OrderDocEnvelope.xsd schema in Notepad.</span></span>  
  
4.  <span data-ttu-id="6aa88-133">次のコードを使用してドキュメントを編集します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-133">Edit the document using the following code.</span></span>  
  
    ```  
    <?xml version="1.0" ?>  
    <xs:schema xmlns:ns0="http://globalbank.esb.dynamicresolution.com/northamericanservices/" xmlns:b="http://schemas.microsoft.com/BizTalk/2003" xmlns="http://ESB.BizUnit.Map.Test" targetNamespace="http://ESB.BizUnit.Map.Test" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  
      <xs:import schemaLocation="GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc" namespace="http://globalbank.esb.dynamicresolution.com/northamericanservices/" />  
      <xs:annotation>  
        <xs:appinfo>  
          <b:schemaInfo is_envelope="yes" xmlns:b="http://schemas.microsoft.com/BizTalk/2003" />  
          <b:references>  
            <b:reference targetNamespace="http://globalbank.esb.dynamicresolution.com/northamericanservices/" />  
          </b:references>  
        </xs:appinfo>  
      </xs:annotation>  
      <xs:element name="OrderEnvelope">  
        <xs:annotation>  
          <xs:appinfo>  
            <b:recordInfo body_xpath="/*[local-name()='OrderEnvelope' and namespace-uri()='http://ESB.BizUnit.Map.Test']" />  
          </xs:appinfo>  
        </xs:annotation>  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element ref="ns0:OrderDoc" />  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:schema>  
    ```  
  
5.  <span data-ttu-id="6aa88-134">OrderDocEnvelope.xsd を utf-8 として保存し、メモ帳を終了します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-134">Save OrderDocEnvelope.xsd as UTF-8, and then close Notepad.</span></span>  
  
6.  <span data-ttu-id="6aa88-135">C:\HowTos フォルダーでは、Batch.xml という名前の新しいテキスト ドキュメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-135">In the C:\HowTos folder, create a new text document named Batch.xml.</span></span>  
  
7.  <span data-ttu-id="6aa88-136">メモ帳で Batch.xml を開きます。</span><span class="sxs-lookup"><span data-stu-id="6aa88-136">In Notepad, open Batch.xml.</span></span>  
  
8.  <span data-ttu-id="6aa88-137">次のコードを使用してドキュメントを編集します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-137">Edit the document using the following code.</span></span>  
  
    ```  
    <?xml version="1.0" ?>  
    <ns0:OrderEnvelope xmlns:ns0="http://ESB.BizUnit.Map.Test">  
      <ns0:OrderDoc xmlns:ns0="http://globalbank.esb.dynamicresolution.com/northamericanservices/">  
        <ns0:customerName>GlobalBankWest</ns0:customerName>  
        <ns0:ID>ns0:ID_0</ns0:ID>  
        <ns0:requestType>10</ns0:requestType>  
      </ns0:OrderDoc>  
      <ns0:OrderDoc xmlns:ns0="http://globalbank.esb.dynamicresolution.com/northamericanservices/">  
        <ns0:customerName>GlobalBankEast</ns0:customerName>  
        <ns0:ID>ns0:ID_0</ns0:ID>  
        <ns0:requestType>11</ns0:requestType>  
      </ns0:OrderDoc>  
      <ns0:OrderDoc xmlns:ns0="http://globalbank.esb.dynamicresolution.com/northamericanservices/">  
        <ns0:customerName>GlobalBankEast</ns0:customerName>  
        <ns0:ID>ns0:ID_0</ns0:ID>  
        <ns0:requestType>12</ns0:requestType>  
      </ns0:OrderDoc>  
    </ns0:OrderEnvelope>  
    ```  
  
9. <span data-ttu-id="6aa88-138">保存して Batch.xml を閉じます。</span><span class="sxs-lookup"><span data-stu-id="6aa88-138">Save and close Batch.xml.</span></span>  
  
#### <a name="to-add-a-schemas-project-to-the-patterns-solution"></a><span data-ttu-id="6aa88-139">パターンのソリューションにスキーマ プロジェクトを追加するには</span><span class="sxs-lookup"><span data-stu-id="6aa88-139">To add a schemas project to the Patterns solution</span></span>  
  
1.  <span data-ttu-id="6aa88-140">Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="6aa88-140">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="6aa88-141">ソリューション エクスプ ローラーで右クリック**ソリューション 'パターン'**、 をポイント**追加**、 をクリックし、**新しいプロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-141">In Solution Explorer, right-click **Solution 'Patterns'**, point to **Add**, and then click **New Project**.</span></span>  
  
3.  <span data-ttu-id="6aa88-142">**新しいプロジェクトの追加** ダイアログ ボックスで、プロジェクトの種類 ペインで、をクリックして**BizTalk プロジェクト**、し、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6aa88-142">In the **Add New Project** dialog box, in the Project types pane, click **BizTalk Projects**, and then do the following:</span></span>  
  
    1.  <span data-ttu-id="6aa88-143">[テンプレート] ペインで次のようにクリックします。**空の BizTalk Server プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-143">In the Templates pane, click **Empty BizTalk Server Project**.</span></span>  
  
    2.  <span data-ttu-id="6aa88-144">**名前**ボックスに「 **Patterns.Schemas**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-144">In the **Name** box, type **Patterns.Schemas**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="6aa88-145">ソリューション エクスプ ローラーで右クリックして**Patterns.Schemas**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-145">In Solution Explorer, right-click **Patterns.Schemas**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="6aa88-146">[プロパティ] ウィンドウで、**署名**] タブで、[、**アセンブリに署名**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="6aa88-146">In the Properties window, on the **Signing** tab, select the **Sign the assembly** check box.</span></span>  
  
6.  <span data-ttu-id="6aa88-147">**厳密な名前キー ファイルを選択して**ドロップダウン リストでは、をクリックして**\<新規.\>**.</span><span class="sxs-lookup"><span data-stu-id="6aa88-147">In the **Choose a strong name key file** drop-down list, click **\<New...\>**.</span></span>  
  
7.  <span data-ttu-id="6aa88-148">**厳密な名前キーの作成** ダイアログ ボックスで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-148">In the **Create Strong Name Key** dialog box, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="6aa88-149">**キー ファイル名**ボックスに「**分割**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-149">In the **Key file name** box, type **Splitting**.</span></span>  
  
    2.  <span data-ttu-id="6aa88-150">クリア、**キーファイルをパスワードで保護する**チェック ボックスをオンにし**OK**。</span><span class="sxs-lookup"><span data-stu-id="6aa88-150">Clear the **Protect my key file with a password** check box, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="6aa88-151">プロパティ ウィンドウでの**展開** タブで、**アプリケーション名**ボックスに「 **Microsoft.Practices.ESB**。</span><span class="sxs-lookup"><span data-stu-id="6aa88-151">In the Properties window, on the **Deployment** tab, in the **Application Name** box, type **Microsoft.Practices.ESB**.</span></span>  
  
9. <span data-ttu-id="6aa88-152">[プロパティ] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="6aa88-152">Close the Properties window.</span></span>  
  
#### <a name="to-add-the-artifacts-to-the-schemas-project"></a><span data-ttu-id="6aa88-153">スキーマ プロジェクトにアイテムを追加するには</span><span class="sxs-lookup"><span data-stu-id="6aa88-153">To add the artifacts to the Schemas project</span></span>  
  
1.  <span data-ttu-id="6aa88-154">ソリューション エクスプ ローラーで右クリックして**Patterns.Schemas**、 をクリックし、**参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-154">In Solution Explorer, right-click **Patterns.Schemas**, and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="6aa88-155">**参照**のタブ、**参照の追加**ダイアログ ボックスで 参照 と C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB します。クリックして、DynamicResolution.Schemas\bin\Debug\GlobalBank.ESB.DynamicResolution.Schemas.dll **OK**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-155">On the **Browse** tab of the **Add Reference** dialog box, browse to and select C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB.DynamicResolution.Schemas\bin\Debug\GlobalBank.ESB.DynamicResolution.Schemas.dll, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="6aa88-156">ソリューション エクスプ ローラーで右クリック**Patterns.Schemas**、 をポイント**追加**、 をクリックし、**既存項目の**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-156">In Solution Explorer, right-click **Patterns.Schemas**, point to **Add**, and then click **Existing Item**.</span></span>  
  
4.  <span data-ttu-id="6aa88-157">**既存項目の追加**C:\HowTos\OrderDocEnvelope.xsd を選択しをクリックし、[参照] ダイアログ ボックスで、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-157">In the **Add Existing Item** dialog box, browse to and select C:\HowTos\OrderDocEnvelope.xsd, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="6aa88-158">すべてのソリューションの成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-158">Save all solution artifacts.</span></span>  
  
6.  <span data-ttu-id="6aa88-159">ソリューション エクスプ ローラーで右クリックして**Patterns.Schemas**、 をクリックし、**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-159">In Solution Explorer, right-click **Patterns.Schemas**, and then click **Deploy**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6aa88-160">このトピックで作成されたものと同じビジネス ルール ポリシーとスケジュールを使用して、[方法。ビジネス ルール ポリシーを使用するスケジュールを選択します。](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)トピック。</span><span class="sxs-lookup"><span data-stu-id="6aa88-160">This How-to topic uses the same business rules policy and itineraries as those created in the [How to: Select an Itinerary Using a Business Rules Policy](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md) topic.</span></span> <span data-ttu-id="6aa88-161">そのセクションを既に完了しなかった場合は、次の手順を完了してください。</span><span class="sxs-lookup"><span data-stu-id="6aa88-161">If you have not already completed that section, please complete the following additional steps.</span></span> <span data-ttu-id="6aa88-162">そのセクションを完了すると場合、は、「手順」セクションに直接進みます。</span><span class="sxs-lookup"><span data-stu-id="6aa88-162">If you have completed that section, continue directly to the "Steps" section.</span></span>  
  
#### <a name="to-create-a-business-rules-engine-bre-policy-to-select-an-itinerary-using-custom-message-properties"></a><span data-ttu-id="6aa88-163">カスタム メッセージ プロパティを使用するスケジュールを選択するビジネス ルール エンジン (BRE) ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="6aa88-163">To create a Business Rules Engine (BRE) policy to select an itinerary using custom message properties</span></span>  
  
1.  <span data-ttu-id="6aa88-164">クリックして**開始**タスク バーで、をポイント**すべてのプログラム**、 をポイント**BizTalk Server**、順にクリックします**ビジネス ルール作成ツール**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-164">Click **Start** on the taskbar, point to **All Programs**, point to **BizTalk Server**, and then click **Business Rule Composer**.</span></span>  
  
2.  <span data-ttu-id="6aa88-165">ポリシー エクスプ ローラーで右クリック**ポリシー**、 をクリックし、**新しいポリシーの追加**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-165">In Policy Explorer, right-click **Policies**, and then click **Add New Policy**.</span></span> <span data-ttu-id="6aa88-166">ポリシーの名前**ResolveItineraryBasedOnCustomer**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-166">Name the policy **ResolveItineraryBasedOnCustomer**.</span></span>  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-west"></a><span data-ttu-id="6aa88-167">GlobalBank 西部の顧客の選択規則を追加するには</span><span class="sxs-lookup"><span data-stu-id="6aa88-167">To add a selection rule for customer GlobalBank West</span></span>  
  
1.  <span data-ttu-id="6aa88-168">**ResolveItineraryBasedOnCustomer**ポリシーを右クリックして**バージョン 1.0 (未保存)**、順にクリックします**新しいルールの追加**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-168">In the **ResolveItineraryBasedOnCustomer** policy, right-click **Version 1.0 (not saved)**, and then click **Add New Rule**.</span></span> <span data-ttu-id="6aa88-169">ルールの名前として**SetGlobalBankWestItinerary**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-169">Name the rule **SetGlobalBankWestItinerary**.</span></span>  
  
2.  <span data-ttu-id="6aa88-170">ファクト エクスプ ローラーでクリックして、 **XML スキーマ** タブを右クリックして**スキーマ**、順にクリックします**参照**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-170">In Facts Explorer, click the **XML Schemas** tab, right-click **Schemas**, and then click **Browse**.</span></span>  
  
3.  <span data-ttu-id="6aa88-171">**スキーマ ファイル** ダイアログ ボックスで、C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB を参照します。DynamicResolution.Schemas が NAOrderDoc.xsd を選択し、クリックして**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-171">In the **Schema Files** dialog box, browse to C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB.DynamicResolution.Schemas, select NAOrderDoc.xsd, and then click **Open**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6aa88-172">テストに使用する西部と東部のメッセージを作成するために使用された NAOrderDoc.xml メッセージを定義するスキーマです。</span><span class="sxs-lookup"><span data-stu-id="6aa88-172">This is the schema that defines the NAOrderDoc.xml message, which was used to create the West and East messages you will use for testing.</span></span>  
  
4.  <span data-ttu-id="6aa88-173">ファクト エクスプ ローラーで NAOrderDoc.xsd をクリックして、**ドキュメントの種類**プロパティのプロパティ ウィンドウと入力し、 **GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-173">In Facts Explorer, click NAOrderDoc.xsd, click the **Document Type** property in the Properties pane, and then type **GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6aa88-174">これは、スキーマの完全修飾名です。</span><span class="sxs-lookup"><span data-stu-id="6aa88-174">This is the fully qualified name of the schema.</span></span>  
  
5.  <span data-ttu-id="6aa88-175">ファクト エクスプ ローラーで、 **NAOrderDoc.xsd**、順に展開**OrderDoc**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-175">In Facts Explorer, expand **NAOrderDoc.xsd**, and then expand **OrderDoc**.</span></span>  
  
6.  <span data-ttu-id="6aa88-176">ルール ウィンドウで、右クリック**条件**、 をポイント**述語**、 をクリックし、**等しい**。</span><span class="sxs-lookup"><span data-stu-id="6aa88-176">In the Rule window, right-click **Conditions**, point to **Predicates**, and then click **Equal**.</span></span>  
  
7.  <span data-ttu-id="6aa88-177">ファクト エクスプ ローラーからドラッグして、 **customerName**要素を **[引数 1]** ノードの下**条件**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-177">From Facts Explorer, drag the **customerName** element to the **argument1** node under **Conditions**.</span></span>  
  
8.  <span data-ttu-id="6aa88-178">をクリックして、 **[引数 2]** ノード、および入力**GlobalBankWest**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-178">Click the **argument2** node, and then type **GlobalBankWest**.</span></span>  
  
9. <span data-ttu-id="6aa88-179">ファクト エクスプ ローラーでクリックして、**ボキャブラリ**タブ。展開、 **ESB します。旅行プラン**ボキャブラリ、展開**バージョン 1.1**、し、ドラッグ、**旅行プラン名の設定**の定義を**アクション**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-179">In Facts Explorer, click the **Vocabularies** tab. Expand the **ESB.Itinerary** vocabulary, expand **Version 1.1**, and then drag the **Set Itinerary Name** definition to **Actions**.</span></span>  
  
10. <span data-ttu-id="6aa88-180">クリックして**\<空の文字列\>** し入力**GlobalBankWestItinerary**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-180">Click **\<empty string\>** and then type **GlobalBankWestItinerary**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6aa88-181">このトピックの後半では、GlobalBank 西部からメッセージを処理するこの旅行プランが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6aa88-181">Later in this How-to topic, you will create this itinerary to process messages from GlobalBank West.</span></span>  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-east"></a><span data-ttu-id="6aa88-182">GlobalBank 東部の顧客の選択規則を追加するには</span><span class="sxs-lookup"><span data-stu-id="6aa88-182">To add a selection rule for customer GlobalBank East</span></span>  
  
1.  <span data-ttu-id="6aa88-183">ポリシー エクスプ ローラーで右クリックし、 **SetGlobalBankWestItinerary**ルールは、クリックして**コピー**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-183">In Policy Explorer, right-click the **SetGlobalBankWestItinerary** rule, and then click **Copy**.</span></span>  
  
2.  <span data-ttu-id="6aa88-184">右クリック**バージョン 1.0 (未保存)**、 をクリックし、**貼り付け**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-184">Right-click **Version 1.0 (not saved)**, and then click **Paste**.</span></span>  
  
3.  <span data-ttu-id="6aa88-185">**新しいルール名**ダイアログ ボックスに「 **SetGlobalBankEastItinerary**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-185">In the **New Rule Name** dialog box, type **SetGlobalBankEastItinerary**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="6aa88-186">ポリシー エクスプ ローラーでクリックして、 **SetGlobalBankEastItinerary**ルール。</span><span class="sxs-lookup"><span data-stu-id="6aa88-186">In Policy Explorer, click the **SetGlobalBankEastItinerary** rule.</span></span>  
  
5.  <span data-ttu-id="6aa88-187">**条件**セクションを右クリックして**GlobalBankWest**、 をクリックし、**引数の再設定**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-187">In the **Conditions** section, right-click **GlobalBankWest**, and then click **Reset argument**.</span></span>  
  
6.  <span data-ttu-id="6aa88-188">クリックして **[引数 2]**、し、入力**GlobalBankEast**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-188">Click **argument2**, and then type **GlobalBankEast**.</span></span>  
  
7.  <span data-ttu-id="6aa88-189">**アクション**セクションで、右クリック**GlobalBankWestItinerary**、 をクリックし、**引数の再設定**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-189">In the **Actions** section, right-click **GlobalBankWestItinerary**, and then click **Reset argument**.</span></span>  
  
8.  <span data-ttu-id="6aa88-190">クリックして**\<空の文字列\>** し入力**GlobalBankEastItinerary します。**</span><span class="sxs-lookup"><span data-stu-id="6aa88-190">Click **\<empty string\>** and then type **GlobalBankEastItinerary.**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6aa88-191">このトピックの後半では、GlobalBank 東部からメッセージを処理するこの旅行プランが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6aa88-191">Later in this How-to topic, you will create this itinerary to process messages from GlobalBank East.</span></span>  
  
#### <a name="to-publish-and-deploy-the-policy"></a><span data-ttu-id="6aa88-192">発行して、ポリシーをデプロイするには</span><span class="sxs-lookup"><span data-stu-id="6aa88-192">To publish and deploy the policy</span></span>  
  
1.  <span data-ttu-id="6aa88-193">ポリシー エクスプ ローラーで 、 **ResolveItineraryBasedOnCustomer**ポリシー、をクリックして**バージョン 1.0 (未保存)**、順にクリックします**発行**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-193">In Policy Explorer, under the **ResolveItineraryBasedOnCustomer** policy, click **Version 1.0 (not saved)**, and then click **Publish**.</span></span>  
  
2.  <span data-ttu-id="6aa88-194">ポリシー エクスプ ローラーで 、 **ResolveItineraryBasedOnCustomer**ポリシー、をクリックして**バージョン 1.0 - 公開済み**、順にクリックします**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-194">In Policy Explorer, under the **ResolveItineraryBasedOnCustomer** policy, click **Version 1.0 - Published**, and then click **Deploy**.</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model-for-globalbank-west-messages"></a><span data-ttu-id="6aa88-195">GlobalBank 西部メッセージの ESB 行程 DSL モデルを作成するには</span><span class="sxs-lookup"><span data-stu-id="6aa88-195">To create an ESB itinerary DSL model for GlobalBank West messages</span></span>  
  
1.  <span data-ttu-id="6aa88-196">**Visual Studio**C:\HowTos\Patterns\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="6aa88-196">In **Visual Studio**, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="6aa88-197">ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントして、**追加**、順にクリックします**新しい行程**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-197">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="6aa88-198">**新しい項目の追加**ダイアログ ボックスの [テンプレート] ペインで、クリックして**ItineraryDsl**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-198">In the **Add New Item** dialog box, in the Templates pane, click **ItineraryDsl**.</span></span>  
  
4.  <span data-ttu-id="6aa88-199">**名前**ボックスに「 **GlobalBankWestItinerary**、 をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-199">In the **Name** box, type **GlobalBankWestItinerary**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-globalbank-west-itinerary"></a><span data-ttu-id="6aa88-200">GlobalBank 西部スケジュールのプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="6aa88-200">To configure the properties of the GlobalBank West itinerary</span></span>  
  
1.  <span data-ttu-id="6aa88-201">Visual Studio でのデザイン画面をクリックします。 **GlobalBankWestItinerary.itinerary**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-201">In Visual Studio, click the design surface of **GlobalBankWestItinerary.itinerary**.</span></span> <span data-ttu-id="6aa88-202">**GlobalBankWestItinerary**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-202">In the **GlobalBankWestItinerary** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="6aa88-203">**モデル エクスポーター**ドロップダウン リストでは、をクリックして**データベース行程エクスポーター**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-203">In the **Model Exporter** drop-down list, click **Database Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="6aa88-204">横にある省略記号ボタン (…) をクリックして、**行程データベース**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="6aa88-204">Click the ellipsis button (...) next to the **Itinerary Database** property.</span></span>  
  
    3.  <span data-ttu-id="6aa88-205">**接続プロパティ**ダイアログ ボックスは itinerary リポジトリ データベースをホストする SQL Server を選択し、データベースの名前を指定し (既定の名前は**EsbItineraryDb**)。</span><span class="sxs-lookup"><span data-stu-id="6aa88-205">In the **Connection Properties** dialog box, choose the SQL Server that hosts the itinerary repository database, and then specify the name of the database (the default name is **EsbItineraryDb**).</span></span>  
  
2.  <span data-ttu-id="6aa88-206">**行程状態**ドロップダウン リストでは、をクリックして**配置済み**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-206">In the **Itinerary Status** drop-down list, click **Deployed**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6aa88-207">この手順では、旅行プランを中央のリポジトリにエクスポートできます。スケジュールを選択し、メッセージが受信したときに、このリポジトリからアタッチします。</span><span class="sxs-lookup"><span data-stu-id="6aa88-207">This step enables you to export the itinerary to a central repository; itineraries can be selected and attached from this repository when messages are received.</span></span> <span data-ttu-id="6aa88-208">後で BRI 競合回避モジュールを使用して、受信メッセージを評価し、このリポジトリから適切な旅行プランを選択するスケジュール セレクターのパイプライン コンポーネントを構成します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-208">You will later configure the Itinerary Selector pipeline component to use the BRI resolver to evaluate inbound messages and select the appropriate itinerary from this repository.</span></span>  
  
#### <a name="to-define-the-structure-of-the-globalbank-west-itinerary"></a><span data-ttu-id="6aa88-209">GlobalBank 西部旅行プランの構造を定義するには</span><span class="sxs-lookup"><span data-stu-id="6aa88-209">To define the structure of the GlobalBank West itinerary</span></span>  
  
1.  <span data-ttu-id="6aa88-210">ツールボックスからドラッグ、**入口**デザイン サーフェイスにモデル要素。</span><span class="sxs-lookup"><span data-stu-id="6aa88-210">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="6aa88-211">**OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-211">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="6aa88-212">をクリックして、**名前**プロパティ、および入力**ReceiveNAOrder**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-212">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="6aa88-213">**エクステンダー**ドロップダウン リストでは、をクリックして**ESB サービス拡張機能の導入**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-213">In the **Extender** drop-down list, click **On-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="6aa88-214">**BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-214">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="6aa88-215">**受信ポート**ドロップダウン リストでは、をクリックして**OnRamp.Itinerary**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-215">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="6aa88-216">ツールボックスからドラッグして、**傾斜オフ**の右側に配置し、デザイン画面に要素をモデル化し、 **ReceiveNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="6aa88-216">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **ReceiveNAOrder** model element.</span></span> <span data-ttu-id="6aa88-217">**OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-217">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="6aa88-218">をクリックして、**名前**プロパティ、および入力**SendNAOrder**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-218">Click the **Name** property, and then type **SendNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="6aa88-219">**エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ ESB サービス拡張**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-219">In the **Extender** drop-down list, click **Off-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="6aa88-220">**BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**GlobalBank.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-220">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="6aa88-221">**送信ポート**ドロップダウン リストでは、をクリックして**DynamicResolutionOneWay**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-221">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
3.  <span data-ttu-id="6aa88-222">ツールボックスからドラッグ、**スケジュール サービス**モデルのデザイン画面に要素との間に配置し、 **ReceiveNAOrder**モデル要素と**SendNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="6aa88-222">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **ReceiveNAOrder** model element and the **SendNAOrder** model element.</span></span> <span data-ttu-id="6aa88-223">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-223">In the **ItineraryService1** properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="6aa88-224">をクリックして、**名前**プロパティ、および入力**RouteMessage**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-224">Click the **Name** property, and then type **RouteMessage**.</span></span>  
  
    2.  <span data-ttu-id="6aa88-225">**旅行プラン サービスのエクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ旅行プラン サービスの拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-225">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Itinerary Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="6aa88-226">**傾斜オフ**ドロップダウン リストで、展開**SendNAOrder**、順にクリックします**送信ハンドラー**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-226">In the **Off-Ramp** drop-down list, expand **SendNAOrder**, and then click **Send Handlers**.</span></span>  
  
4.  <span data-ttu-id="6aa88-227">右クリックし、**リゾルバー**のコレクション、 **RouteMessage**モデル要素をクリックして**新しいリゾルバーを追加**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-227">Right-click the **Resolver** collection of the **RouteMessage** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="6aa88-228">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-228">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="6aa88-229">をクリックして、**名前**プロパティ、および入力**StaticResolver**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-229">Click the **Name** property, and then type **StaticResolver**.</span></span>  
  
    2.  <span data-ttu-id="6aa88-230">**リゾルバーの実装**ドロップダウン リストでは、をクリックして**静的な競合回避モジュール拡張**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-230">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="6aa88-231">**トランスポート名**ドロップダウン リストでは、をクリックして**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-231">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="6aa88-232">をクリックして、**トランスポート場所**プロパティ、および入力**C:\HowTos\Out\West%MessageID%.xml**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-232">Click the **Transport Location** property, and then type **C:\HowTos\Out\West%MessageID%.xml**.</span></span>  
  
5.  <span data-ttu-id="6aa88-233">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-233">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="6aa88-234">接続をドラッグして、 **ReceiveNAOrder**モデル要素に、 **RouteMessage**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="6aa88-234">Drag a connection from the **ReceiveNAOrder** model element to the  **RouteMessage** model element.</span></span>  
  
6.  <span data-ttu-id="6aa88-235">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-235">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="6aa88-236">接続をドラッグして、 **RouteMessage**モデル要素に、 **SendNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="6aa88-236">Drag a connection from the **RouteMessage** model element to the **SendNAOrder** model element.</span></span>  
  
#### <a name="to-export-the-globalbank-west-model-to-the-itinerary-database"></a><span data-ttu-id="6aa88-237">GlobalBank 西部モデル行程データベースをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="6aa88-237">To export the GlobalBank West model to the itinerary database</span></span>  
  
1.  <span data-ttu-id="6aa88-238">Visual Studio でのデザイン画面を右クリックし、 **GlobalBankWestItinerary**旅行プランをクリックして**モデルのエクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-238">In Visual Studio, right-click the design surface of the **GlobalBankWestItinerary** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6aa88-239">旅行プランは、行程データベースをエクスポートされ、スケジュール セレクター コンポーネントで使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="6aa88-239">The itinerary has been exported to the itinerary database and can now be used by the Itinerary Selector component.</span></span>  
  
2.  <span data-ttu-id="6aa88-240">すべてのプロジェクト成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-240">Save all project artifacts.</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model-for-globalbank-east-message"></a><span data-ttu-id="6aa88-241">GlobalBank 東部メッセージの ESB 行程 DSL モデルを作成するには</span><span class="sxs-lookup"><span data-stu-id="6aa88-241">To create an ESB itinerary DSL model for GlobalBank East message</span></span>  
  
1.  <span data-ttu-id="6aa88-242">**Visual Studio**C:\HowTos\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="6aa88-242">In **Visual Studio**, open C:\HowTos\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="6aa88-243">ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントして、**追加**、順にクリックします**新しい行程**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-243">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="6aa88-244">**新しい項目の追加**ダイアログ ボックスの [テンプレート] ペインで、クリックして**ItineraryDsl**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-244">In the **Add New Item** dialog box, in the Templates pane, click **ItineraryDsl**.</span></span>  
  
4.  <span data-ttu-id="6aa88-245">**名前**ボックスに「 **GlobalBankEastItinerary**、 をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-245">In the **Name** box, type **GlobalBankEastItinerary**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-globalbank-east-itinerary"></a><span data-ttu-id="6aa88-246">GlobalBank 東部スケジュールのプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="6aa88-246">To configure the properties of the GlobalBank East itinerary</span></span>  
  
1.  <span data-ttu-id="6aa88-247">Visual Studio でのデザイン画面をクリックします。 **GlobalBankEastItinerary.itinerary**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-247">In Visual Studio, click the design surface of **GlobalBankEastItinerary.itinerary**.</span></span> <span data-ttu-id="6aa88-248">**GlobalBankEastItinerary**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-248">In the **GlobalBankEastItinerary** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="6aa88-249">**モデル エクスポーター**ドロップダウン リストでは、をクリックして**データベース行程エクスポーター**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-249">In the **Model Exporter** drop-down list, click **Database Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="6aa88-250">横にある省略記号ボタン (…) をクリックして、**行程データベース**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="6aa88-250">Click the ellipsis button (...) next to the **Itinerary Database** property.</span></span>  
  
    3.  <span data-ttu-id="6aa88-251">**接続プロパティ**ダイアログ ボックスは itinerary リポジトリ データベースをホストする SQL Server を選択し、データベースの名前を指定し (既定の名前は**EsbItineraryDb**)。</span><span class="sxs-lookup"><span data-stu-id="6aa88-251">In the **Connection Properties** dialog box, choose the SQL Server that hosts the itinerary repository database, and then specify the name of the database (the default name is **EsbItineraryDb**).</span></span>  
  
2.  <span data-ttu-id="6aa88-252">**行程状態**ドロップダウン リストでは、をクリックして**配置済み**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-252">In the **Itinerary Status** drop-down list, click **Deployed**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6aa88-253">この手順では、旅行プランを中央のリポジトリにエクスポートできます。スケジュールを選択し、メッセージが受信したときに、このリポジトリからアタッチします。</span><span class="sxs-lookup"><span data-stu-id="6aa88-253">This step enables you to export the itinerary to a central repository; itineraries can be selected and attached from this repository when messages are received.</span></span> <span data-ttu-id="6aa88-254">後で BRI 競合回避モジュールを使用して、受信メッセージを評価し、このリポジトリから適切な旅行プランを選択するスケジュール セレクターのパイプライン コンポーネントを構成します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-254">You will later configure the Itinerary Selector pipeline component to use the BRI resolver to evaluate inbound messages and select the appropriate itinerary from this repository.</span></span>  
  
#### <a name="to-define-the-structure-of-the-globalbank-east-itinerary"></a><span data-ttu-id="6aa88-255">GlobalBank 東部旅行プランの構造を定義するには</span><span class="sxs-lookup"><span data-stu-id="6aa88-255">To define the structure of the GlobalBank East itinerary</span></span>  
  
1.  <span data-ttu-id="6aa88-256">ツールボックスからドラッグ、**入口**デザイン サーフェイスにモデル要素。</span><span class="sxs-lookup"><span data-stu-id="6aa88-256">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="6aa88-257">**OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-257">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="6aa88-258">をクリックして、**名前**プロパティ、および入力**ReceiveNAOrder**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-258">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="6aa88-259">**エクステンダー**ドロップダウン リストでは、をクリックして**ESB サービス拡張機能の導入**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-259">In the **Extender** drop-down list, click **On-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="6aa88-260">**BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-260">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="6aa88-261">**受信ポート**ドロップダウン リストでは、をクリックして**OnRamp.Itinerary**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-261">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="6aa88-262">ツールボックスからドラッグして、**傾斜オフ**の右側に配置し、デザイン画面に要素をモデル化し、 **ReceiveNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="6aa88-262">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **ReceiveNAOrder** model element.</span></span> <span data-ttu-id="6aa88-263">**OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-263">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="6aa88-264">をクリックして、**名前**プロパティ、および入力**SendNAOrder**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-264">Click the **Name** property, and then type **SendNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="6aa88-265">**エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ ESB サービス拡張**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-265">In the **Extender** drop-down list, click **Off-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="6aa88-266">**BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**GlobalBank.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-266">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="6aa88-267">**送信ポート**ドロップダウン リストでは、をクリックして**DynamicResolutionOneWay**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-267">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
3.  <span data-ttu-id="6aa88-268">ツールボックスからドラッグ、**スケジュール サービス**モデルのデザイン画面に要素との間に配置し、 **ReceiveNAOrder**モデル要素と**SendNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="6aa88-268">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **ReceiveNAOrder** model element and the **SendNAOrder** model element.</span></span> <span data-ttu-id="6aa88-269">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-269">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="6aa88-270">をクリックして、**名前**プロパティ、および入力**RouteMessage**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-270">Click the **Name** property, and then type **RouteMessage**.</span></span>  
  
    2.  <span data-ttu-id="6aa88-271">**旅行プラン サービスのエクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ旅行プラン サービスの拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-271">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Itinerary Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="6aa88-272">**傾斜オフ**ドロップダウン リストで、展開**SendNAOrder**、順にクリックします**送信ハンドラー**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-272">In the **Off-Ramp** drop-down list, expand **SendNAOrder**, and then click **Send Handlers**.</span></span>  
  
4.  <span data-ttu-id="6aa88-273">右クリックし、**リゾルバー**のコレクション、 **RouteMessage**モデル要素をクリックして**新しいリゾルバーを追加**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-273">Right-click the **Resolver** collection of the **RouteMessage** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="6aa88-274">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-274">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="6aa88-275">をクリックして、**名前**プロパティ、および入力**StaticResolver**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-275">Click the **Name** property, and then type **StaticResolver**.</span></span>  
  
    2.  <span data-ttu-id="6aa88-276">**リゾルバーの実装**ドロップダウン リストでは、をクリックして**静的な競合回避モジュール拡張**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-276">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="6aa88-277">**トランスポート名**ドロップダウン リストでは、をクリックして**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-277">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="6aa88-278">をクリックして、**トランスポート場所**プロパティ、および入力**C:\HowTos\Out\East%MessageID%.xml**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-278">Click the **Transport Location** property, and then type **C:\HowTos\Out\East%MessageID%.xml**.</span></span>  
  
5.  <span data-ttu-id="6aa88-279">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-279">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="6aa88-280">接続をドラッグして、 **ReceiveNAOrder**モデル要素に、 **RouteMessage**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="6aa88-280">Drag a connection from the **ReceiveNAOrder** model element to the **RouteMessage** model element.</span></span>  
  
6.  <span data-ttu-id="6aa88-281">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-281">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="6aa88-282">接続をドラッグして、 **RouteMessage**モデル要素に、 **SendNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="6aa88-282">Drag a connection from the **RouteMessage** model element to the **SendNAOrder** model element.</span></span>  
  
#### <a name="to-export-the-globalbank-east-model-to-the-itinerary-database"></a><span data-ttu-id="6aa88-283">GlobalBank 東部モデル行程データベースをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="6aa88-283">To export the GlobalBank East model to the itinerary database</span></span>  
  
1.  <span data-ttu-id="6aa88-284">Visual Studio でのデザイン画面を右クリックし、 **GlobalBankEastItinerary**旅行プランをクリックして**モデルのエクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-284">In Visual Studio, right-click the design surface of the **GlobalBankEastItinerary** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6aa88-285">旅行プランは、行程データベースをエクスポートされ、スケジュール セレクター コンポーネントで使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="6aa88-285">The itinerary has been exported to the itinerary database and can now be used by the Itinerary Selector component.</span></span>  
  
2.  <span data-ttu-id="6aa88-286">すべてのプロジェクト成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-286">Save all project artifacts.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="6aa88-287">手順</span><span class="sxs-lookup"><span data-stu-id="6aa88-287">Steps</span></span>  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a><span data-ttu-id="6aa88-288">作成および ESB 入り口を構成するには</span><span class="sxs-lookup"><span data-stu-id="6aa88-288">To create and configure an ESB on-ramp</span></span>  
  
1.  <span data-ttu-id="6aa88-289">クリックして**開始**タスク バーで、をポイント**すべてのプログラム**、 をポイント**BizTalk Server**、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-289">Click **Start** on the taskbar, point to **All Programs**, point to **BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="6aa88-290">BizTalk Server 管理コンソールで  **BizTalk グループ**、展開**アプリケーション**、順に展開**Microsoft.Practices.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-290">In the BizTalk Server Administration Console, expand **BizTalk Group**, expand **Applications**, and then expand **Microsoft.Practices.ESB**.</span></span>  
  
3.  <span data-ttu-id="6aa88-291">右クリック**受信場所**、 をポイント**新規**、 をクリックし、**一方向の受信場所**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-291">Right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
4.  <span data-ttu-id="6aa88-292">**受信ポートの選択**ダイアログ ボックスで、をクリックして**OnRamp.Itinerary**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="6aa88-292">In the **Select a Receive Port** dialog box, click **OnRamp.Itinerary**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="6aa88-293">**受信場所のプロパティ** ダイアログ ボックスで、**名前**ボックスに「 **OnRamp.Itinerary.HowTo**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-293">In the **Receive Location Properties** dialog box, in the **Name** box, type **OnRamp.Itinerary.HowTo**.</span></span>  
  
6.  <span data-ttu-id="6aa88-294">**型**ドロップダウン リストでは、をクリックして**ファイル、** 順にクリックします**構成**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-294">In the **Type** drop-down list, click **FILE,** and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="6aa88-295">**FILE トランスポートのプロパティ** ダイアログ ボックスで、**受信フォルダー**ボックスに「 **C:\HowTos\DropFolder**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-295">In the **FILE Transport Properties** dialog box, in the **Receive folder** box, type **C:\HowTos\DropFolder**, and then click **OK**.</span></span>  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a><span data-ttu-id="6aa88-296">旅行プラン セレクターのパイプライン コンポーネントを構成するには</span><span class="sxs-lookup"><span data-stu-id="6aa88-296">To configure the Itinerary Selector pipeline component</span></span>  
  
1.  <span data-ttu-id="6aa88-297">**受信場所のプロパティ**ダイアログ ボックスで、をクリックして**ItinerarySelectReceiveXml**で、**受信パイプライン**ドロップダウン ボックスの一覧し、省略記号ボタン (…) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6aa88-297">In the **Receive Location Properties** dialog box, click **ItinerarySelectReceiveXml** in the **Receive pipeline** drop-down list, and then click the ellipsis button (...).</span></span>  
  
2.  <span data-ttu-id="6aa88-298">使用して、**パイプラインの構成**、以下の構成 ダイアログ ボックス**スケジュール セレクター**コンポーネントのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="6aa88-298">Use the **Configure Pipeline** dialog box to configure the following **Itinerary Selector** component properties:</span></span>  
  
    1.  <span data-ttu-id="6aa88-299">をクリックして、 **ItineraryFactKey**プロパティ、および入力**Resolver.Itinerary**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-299">Click the **ItineraryFactKey** property, and then type **Resolver.Itinerary**.</span></span>  
  
    2.  <span data-ttu-id="6aa88-300">をクリックして、 **ResolverConnectionString**プロパティ、および入力**BRI:\\\policy=ResolveItineraryBasedOnCustomer;useMsg=true;recognizeMessageFormat=true;**</span><span class="sxs-lookup"><span data-stu-id="6aa88-300">Click the **ResolverConnectionString** property, and then type **BRI:\\\policy=ResolveItineraryBasedOnCustomer;useMsg=true;recognizeMessageFormat=true;**</span></span>  
  
    3.  <span data-ttu-id="6aa88-301">クリックして**OK**を閉じる、**パイプラインの構成** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="6aa88-301">Click **OK** to close the **Configure Pipeline** dialog box.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="6aa88-302">この受信場所が、XML インターチェンジを逆アセンブル、XML 逆アセンブラー コンポーネントの構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6aa88-302">Because this receive location is disassembling an XML interchange, no XML Disassembler component configuration is required.</span></span>  
  
3.  <span data-ttu-id="6aa88-303">クリックして**OK**を閉じる、**受信場所のプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="6aa88-303">Click **OK** to close the **Receive Location Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="6aa88-304">右クリックし、BizTalk Server 管理コンソールで、 **OnRamp.Itinerary.HowTo**受信場所をクリックして**を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-304">In the BizTalk Server Administration Console, right-click the **OnRamp.Itinerary.HowTo** receive location, and then click **Enable**.</span></span>  
  
#### <a name="to-test-the-itinerary-selector-and-business-rules"></a><span data-ttu-id="6aa88-305">旅行プラン セレクターとビジネス ルールをテストするには</span><span class="sxs-lookup"><span data-stu-id="6aa88-305">To test the Itinerary Selector and business rules</span></span>  
  
1.  <span data-ttu-id="6aa88-306">Windows エクスプ ローラーでは、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-306">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="6aa88-307">コピー (移動しないでください) Batch.xml DropFolder フォルダーにします。</span><span class="sxs-lookup"><span data-stu-id="6aa88-307">Copy (do not move) Batch.xml to the DropFolder folder.</span></span>  
  
3.  <span data-ttu-id="6aa88-308">C:\HowTos\Out に移動します。1 つの West%MessageID%.xml メッセージと East%MessageID%.xml の 2 つのメッセージがディレクトリに書き込まれたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-308">Browse to C:\HowTos\Out. Verify that one West%MessageID%.xml message and two East%MessageID%.xml messages have been written to the directory.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6aa88-309">メッセージは customer 要素の値を除いて同一ですが、異なる日程表、日程セレクターのパイプライン コンポーネントの解像度に基づくを使用して処理されました。</span><span class="sxs-lookup"><span data-stu-id="6aa88-309">Although the messages are identical except for the value of the customer element, they were processed using different itineraries, based on the resolution of the Itinerary Selector pipeline component.</span></span>  
  
4.  <span data-ttu-id="6aa88-310">BizTalk Server 管理コンソールで受信場所を右クリックして、OnRamp.Itinerary.HowTo と無効をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6aa88-310">In the BizTalk Server Administration Console, right-click the OnRamp.Itinerary.HowTo receive location, and then click Disable.</span></span>  
  
5.  <span data-ttu-id="6aa88-311">後に、 **OnRamp.Itinerary.HowTo**受信場所が無効になっている、右クリックし、 をクリックし、**削除**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-311">After the **OnRamp.Itinerary.HowTo** receive location is disabled, right-click it, and then click **Delete**.</span></span> <span data-ttu-id="6aa88-312">**削除の確認の受信場所**ダイアログ ボックスで、をクリックして**はい**します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-312">In the **Confirm delete receive location** dialog box, click **Yes**.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="6aa88-313">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="6aa88-313">Additional Resources</span></span>  
 <span data-ttu-id="6aa88-314">詳細については、次の関連項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6aa88-314">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="6aa88-315">方法: ビジネス ルール ポリシーを使用するスケジュールを選択します。</span><span class="sxs-lookup"><span data-stu-id="6aa88-315">How to: Select an Itinerary Using a Business Rules Policy</span></span>](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [<span data-ttu-id="6aa88-316">開発アクティビティ</span><span class="sxs-lookup"><span data-stu-id="6aa88-316">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="6aa88-317">動的解決サンプルをインストールし、実行する</span><span class="sxs-lookup"><span data-stu-id="6aa88-317">Installing and Running the Dynamic Resolution Sample</span></span>](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)  
  
-   [<span data-ttu-id="6aa88-318">動的な解決とルーティングを利用する</span><span class="sxs-lookup"><span data-stu-id="6aa88-318">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)  
  
-   [<span data-ttu-id="6aa88-319">メッセージ ルーティング パターン</span><span class="sxs-lookup"><span data-stu-id="6aa88-319">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)