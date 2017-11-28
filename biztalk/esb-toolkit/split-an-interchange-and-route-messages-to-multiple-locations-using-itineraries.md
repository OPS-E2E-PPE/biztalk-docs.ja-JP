---
title: "方法: インターチェンジを分割し、個別の日程を使用して複数のファイルの場所に結果のメッセージをルーティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ccd46bee-e4a1-4846-8bde-b0460bda1e72
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c752c4b98f6a68e0a86ba4a418eab0705a7c513
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-split-an-interchange-and-route-the-resulting-messages-to-multiple-file-locations-using-distinct-itineraries"></a><span data-ttu-id="a0105-102">方法: インターチェンジを分割し、結果として得られるメッセージをルーティング、個別の日程を使用して複数のファイルの場所</span><span class="sxs-lookup"><span data-stu-id="a0105-102">How to: Split an Interchange and Route the Resulting Messages to Multiple File Locations Using Distinct Itineraries</span></span>
## <a name="goal"></a><span data-ttu-id="a0105-103">[目標]</span><span class="sxs-lookup"><span data-stu-id="a0105-103">Goal</span></span>  
 <span data-ttu-id="a0105-104">このセクションでは、ESB 入り口を使用するを作成する方法を示します、 **ItinerarySelectReceiveXml**の明細のパイプラインと受信インターチェンジを分割し、適切なルーティングを選択するパイプラインのコンポーネントを構成する方法各結果のメッセージ、メッセージ コンテキストに基づきます。</span><span class="sxs-lookup"><span data-stu-id="a0105-104">This section demonstrates how to create an ESB on-ramp that uses the **ItinerarySelectReceiveXml** pipeline and how to configure the pipeline's components to split an inbound interchange and select the appropriate routing slip for each resulting message, based on message context.</span></span> <span data-ttu-id="a0105-105">Itinerary 選択は、ビジネス ルール ポリシーを使用して解決して、顧客が存在する地域に基づいて、異なる方法でメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="a0105-105">Itinerary selection will be resolved using a business rules policy, and messages will be routed differently based on the region in which the customer resides.</span></span>  
  
 <span data-ttu-id="a0105-106">このトピックでは、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="a0105-106">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="a0105-107">ESB 入り口、XML インターチェンジを分割するを作成します。</span><span class="sxs-lookup"><span data-stu-id="a0105-107">Create an ESB on-ramp that splits an XML interchange.</span></span>  
  
-   <span data-ttu-id="a0105-108">ビジネス ルール ポリシーを使用して、適切な旅程を選択、行程セレクター パイプライン コンポーネントを構成します。</span><span class="sxs-lookup"><span data-stu-id="a0105-108">Configure the Itinerary Selector pipeline component to use a business rules policy to select the appropriate itinerary.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a0105-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="a0105-109">Prerequisites</span></span>  
 <span data-ttu-id="a0105-110">この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)です。</span><span class="sxs-lookup"><span data-stu-id="a0105-110">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="a0105-111">はじめに</span><span class="sxs-lookup"><span data-stu-id="a0105-111">Before You Begin</span></span>  
 <span data-ttu-id="a0105-112">このトピックの「操作方法に関する手順を実行する前に、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="a0105-112">Complete the following tasks before you perform the steps later in this How-to topic:</span></span>  
  
-   <span data-ttu-id="a0105-113">必要なアイテムを作成します。</span><span class="sxs-lookup"><span data-stu-id="a0105-113">Create the required artifacts.</span></span>  
  
-   <span data-ttu-id="a0105-114">Schemas プロジェクトをパターンのソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="a0105-114">Add a schemas project to the Patterns solution.</span></span>  
  
-   <span data-ttu-id="a0105-115">成果物をスキーマ プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="a0105-115">Add the artifacts to the Schemas project.</span></span>  
  
-   <span data-ttu-id="a0105-116">カスタム メッセージ プロパティを使用して、日程を選択する BRE ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="a0105-116">Create a BRE policy to select an itinerary using custom message properties.</span></span>  
  
-   <span data-ttu-id="a0105-117">顧客 GlobalBank 西部の選択ルールを追加します。</span><span class="sxs-lookup"><span data-stu-id="a0105-117">Add a selection rule for customer GlobalBank West.</span></span>  
  
-   <span data-ttu-id="a0105-118">GlobalBank 東部の顧客の選択ルールを追加します。</span><span class="sxs-lookup"><span data-stu-id="a0105-118">Add a selection rule for customer GlobalBank East.</span></span>  
  
-   <span data-ttu-id="a0105-119">発行し、ポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="a0105-119">Publish and deploy the policy.</span></span>  
  
-   <span data-ttu-id="a0105-120">GlobalBank 西部メッセージの ESB itinerary ドメイン固有言語 (DSL) モデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="a0105-120">Create an ESB itinerary domain-specific language (DSL) model for GlobalBank West messages.</span></span>  
  
-   <span data-ttu-id="a0105-121">GlobalBank 西部旅行計画のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="a0105-121">Configure the properties of the GlobalBank West itinerary.</span></span>  
  
-   <span data-ttu-id="a0105-122">GlobalBank 西部行程の構造を定義します。</span><span class="sxs-lookup"><span data-stu-id="a0105-122">Define the structure of the GlobalBank West itinerary.</span></span>  
  
-   <span data-ttu-id="a0105-123">行程データベース GlobalBank 西部モデルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="a0105-123">Export the GlobalBank West model to the itinerary database.</span></span>  
  
-   <span data-ttu-id="a0105-124">GlobalBank 東部メッセージの ESB itinerary DSL モデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="a0105-124">Create an ESB itinerary DSL model for GlobalBank East messages.</span></span>  
  
-   <span data-ttu-id="a0105-125">GlobalBank 東部旅行計画のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="a0105-125">Configure the properties of the GlobalBank East itinerary.</span></span>  
  
-   <span data-ttu-id="a0105-126">GlobalBank 東部行程の構造を定義します。</span><span class="sxs-lookup"><span data-stu-id="a0105-126">Define the structure of the GlobalBank East itinerary.</span></span>  
  
-   <span data-ttu-id="a0105-127">行程データベース GlobalBank 東部モデルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="a0105-127">Export the GlobalBank East model to the itinerary database.</span></span>  
  
     <span data-ttu-id="a0105-128">次の手順では、これらの各を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a0105-128">The following procedures describe how to do each of these.</span></span>  
  
#### <a name="to-create-the-required-artifacts"></a><span data-ttu-id="a0105-129">必要なアイテムを作成するには</span><span class="sxs-lookup"><span data-stu-id="a0105-129">To create the required artifacts</span></span>  
  
1.  <span data-ttu-id="a0105-130">Windows エクスプローラで、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="a0105-130">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="a0105-131">OrderDocEnvelope.xsd をという名前の新しいテキスト ドキュメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="a0105-131">Create a new text document named OrderDocEnvelope.xsd.</span></span>  
  
3.  <span data-ttu-id="a0105-132">OrderDocEnvelope.xsd スキーマをメモ帳で開きます。</span><span class="sxs-lookup"><span data-stu-id="a0105-132">Open the OrderDocEnvelope.xsd schema in Notepad.</span></span>  
  
4.  <span data-ttu-id="a0105-133">次のコードを使用してドキュメントを編集します。</span><span class="sxs-lookup"><span data-stu-id="a0105-133">Edit the document using the following code.</span></span>  
  
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
  
5.  <span data-ttu-id="a0105-134">Utf-8 として OrderDocEnvelope.xsd を保存し、メモ帳を閉じます。</span><span class="sxs-lookup"><span data-stu-id="a0105-134">Save OrderDocEnvelope.xsd as UTF-8, and then close Notepad.</span></span>  
  
6.  <span data-ttu-id="a0105-135">C:\HowTos フォルダーでは、Batch.xml をという名前の新しいテキスト ドキュメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="a0105-135">In the C:\HowTos folder, create a new text document named Batch.xml.</span></span>  
  
7.  <span data-ttu-id="a0105-136">メモ帳で、Batch.xml を開きます。</span><span class="sxs-lookup"><span data-stu-id="a0105-136">In Notepad, open Batch.xml.</span></span>  
  
8.  <span data-ttu-id="a0105-137">次のコードを使用してドキュメントを編集します。</span><span class="sxs-lookup"><span data-stu-id="a0105-137">Edit the document using the following code.</span></span>  
  
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
  
9. <span data-ttu-id="a0105-138">保存して Batch.xml を閉じます。</span><span class="sxs-lookup"><span data-stu-id="a0105-138">Save and close Batch.xml.</span></span>  
  
#### <a name="to-add-a-schemas-project-to-the-patterns-solution"></a><span data-ttu-id="a0105-139">Schemas プロジェクト ソリューションを追加する、パターン</span><span class="sxs-lookup"><span data-stu-id="a0105-139">To add a schemas project to the Patterns solution</span></span>  
  
1.  <span data-ttu-id="a0105-140">[!INCLUDE[vs2010](../includes/vs2010-md.md)]C:\HowTos\Patterns\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="a0105-140">In [!INCLUDE[vs2010](../includes/vs2010-md.md)], open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="a0105-141">ソリューション エクスプ ローラーで右クリック**ソリューション 'パターン'**、 をポイント**追加**、クリックして**新しいプロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-141">In Solution Explorer, right-click **Solution 'Patterns'**, point to **Add**, and then click **New Project**.</span></span>  
  
3.  <span data-ttu-id="a0105-142">**新しいプロジェクトの追加**ダイアログ ボックスで、プロジェクトの種類 ペインで、をクリックして**BizTalk プロジェクト**、し、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a0105-142">In the **Add New Project** dialog box, in the Project types pane, click **BizTalk Projects**, and then do the following:</span></span>  
  
    1.  <span data-ttu-id="a0105-143">テンプレート ウィンドウで **空の BizTalk Server プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-143">In the Templates pane, click **Empty BizTalk Server Project**.</span></span>  
  
    2.  <span data-ttu-id="a0105-144">**名前**ボックスに、入力**Patterns.Schemas**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-144">In the **Name** box, type **Patterns.Schemas**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="a0105-145">ソリューション エクスプ ローラーで右クリック**Patterns.Schemas**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-145">In Solution Explorer, right-click **Patterns.Schemas**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="a0105-146">プロパティ ウィンドウでの**署名** タブで、**アセンブリに署名** チェック ボックスです。</span><span class="sxs-lookup"><span data-stu-id="a0105-146">In the Properties window, on the **Signing** tab, select the **Sign the assembly** check box.</span></span>  
  
6.  <span data-ttu-id="a0105-147">**厳密な名前キー ファイルを選択して**ドロップダウン リストをクリックして**\<新規作成 ...> >**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-147">In the **Choose a strong name key file** drop-down list, click **\<New...>**.</span></span>  
  
7.  <span data-ttu-id="a0105-148">**厳密な名前キーの作成** ダイアログ ボックスで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="a0105-148">In the **Create Strong Name Key** dialog box, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a0105-149">**キー ファイル名**ボックスに、入力**分割**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-149">In the **Key file name** box, type **Splitting**.</span></span>  
  
    2.  <span data-ttu-id="a0105-150">クリア、**キーファイルをパスワードで保護する**チェック ボックスをクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-150">Clear the **Protect my key file with a password** check box, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="a0105-151">プロパティ ウィンドウで 、**展開** タブの 、**アプリケーション名**ボックスに、入力**Microsoft.Practices.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-151">In the Properties window, on the **Deployment** tab, in the **Application Name** box, type **Microsoft.Practices.ESB**.</span></span>  
  
9. <span data-ttu-id="a0105-152">[プロパティ] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="a0105-152">Close the Properties window.</span></span>  
  
#### <a name="to-add-the-artifacts-to-the-schemas-project"></a><span data-ttu-id="a0105-153">スキーマ プロジェクトにアイテムを追加するには</span><span class="sxs-lookup"><span data-stu-id="a0105-153">To add the artifacts to the Schemas project</span></span>  
  
1.  <span data-ttu-id="a0105-154">ソリューション エクスプ ローラーで右クリック**Patterns.Schemas**、クリックして**参照の追加**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-154">In Solution Explorer, right-click **Patterns.Schemas**, and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="a0105-155">**参照**のタブ、**参照の追加** ダイアログ ボックスを参照して選択 C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB です。クリックして、DynamicResolution.Schemas\bin\Debug\GlobalBank.ESB.DynamicResolution.Schemas.dll **OK**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-155">On the **Browse** tab of the **Add Reference** dialog box, browse to and select C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB.DynamicResolution.Schemas\bin\Debug\GlobalBank.ESB.DynamicResolution.Schemas.dll, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="a0105-156">ソリューション エクスプ ローラーで右クリック**Patterns.Schemas**、 をポイント**追加**、クリックして**既存項目の**します。</span><span class="sxs-lookup"><span data-stu-id="a0105-156">In Solution Explorer, right-click **Patterns.Schemas**, point to **Add**, and then click **Existing Item**.</span></span>  
  
4.  <span data-ttu-id="a0105-157">**既存項目の追加**ダイアログ ボックスで、[参照] を C:\HowTos\OrderDocEnvelope.xsd を選択し、をクリックし、**追加**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-157">In the **Add Existing Item** dialog box, browse to and select C:\HowTos\OrderDocEnvelope.xsd, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="a0105-158">すべてのソリューションの成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="a0105-158">Save all solution artifacts.</span></span>  
  
6.  <span data-ttu-id="a0105-159">ソリューション エクスプ ローラーで右クリック**Patterns.Schemas**、クリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-159">In Solution Explorer, right-click **Patterns.Schemas**, and then click **Deploy**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a0105-160">この操作方法に関するトピックでは、同じビジネス ルール ポリシーと旅程で作成された、[する方法: ビジネス ルール ポリシーを使用して、日程を選択して](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)トピックです。</span><span class="sxs-lookup"><span data-stu-id="a0105-160">This How-to topic uses the same business rules policy and itineraries as those created in the [How to: Select an Itinerary Using a Business Rules Policy](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md) topic.</span></span> <span data-ttu-id="a0105-161">そのセクションを既に完了がいない場合は、次の手順を完了してください。</span><span class="sxs-lookup"><span data-stu-id="a0105-161">If you have not already completed that section, please complete the following additional steps.</span></span> <span data-ttu-id="a0105-162">そのセクションを完了している場合は、「手順セクションに直接進みます。</span><span class="sxs-lookup"><span data-stu-id="a0105-162">If you have completed that section, continue directly to the "Steps" section.</span></span>  
  
#### <a name="to-create-a-business-rules-engine-bre-policy-to-select-an-itinerary-using-custom-message-properties"></a><span data-ttu-id="a0105-163">カスタム メッセージ プロパティを使用して、日程を選択するビジネス ルール エンジン (BRE) ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="a0105-163">To create a Business Rules Engine (BRE) policy to select an itinerary using custom message properties</span></span>  
  
1.  <span data-ttu-id="a0105-164">をクリックして**開始**タスク バーで、をポイント**すべてのプログラム**、 をポイント **[!INCLUDE[prague](../includes/prague-md.md)]** 、順にクリック**ビジネス ルール作成ツール**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-164">Click **Start** on the taskbar, point to **All Programs**, point to **[!INCLUDE[prague](../includes/prague-md.md)]**, and then click **Business Rule Composer**.</span></span>  
  
2.  <span data-ttu-id="a0105-165">ポリシー エクスプ ローラーで右クリック**ポリシー**、クリックして**新しいポリシーの追加**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-165">In Policy Explorer, right-click **Policies**, and then click **Add New Policy**.</span></span> <span data-ttu-id="a0105-166">ポリシーに名前**ResolveItineraryBasedOnCustomer**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-166">Name the policy **ResolveItineraryBasedOnCustomer**.</span></span>  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-west"></a><span data-ttu-id="a0105-167">GlobalBank 西部の顧客の選択ルールを追加するには</span><span class="sxs-lookup"><span data-stu-id="a0105-167">To add a selection rule for customer GlobalBank West</span></span>  
  
1.  <span data-ttu-id="a0105-168">**ResolveItineraryBasedOnCustomer**ポリシーを右クリックして**バージョン 1.0 (未保存)**、順にクリック**新しいルールの追加**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-168">In the **ResolveItineraryBasedOnCustomer** policy, right-click **Version 1.0 (not saved)**, and then click **Add New Rule**.</span></span> <span data-ttu-id="a0105-169">ルールの名前として**SetGlobalBankWestItinerary**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-169">Name the rule **SetGlobalBankWestItinerary**.</span></span>  
  
2.  <span data-ttu-id="a0105-170">ファクト エクスプ ローラーで、をクリックして、 **XML スキーマ** タブを右クリックして**スキーマ**、クリックして**参照**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-170">In Facts Explorer, click the **XML Schemas** tab, right-click **Schemas**, and then click **Browse**.</span></span>  
  
3.  <span data-ttu-id="a0105-171">**スキーマ ファイル** ダイアログ ボックスで、C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB を参照します。DynamicResolution.Schemas、NAOrderDoc.xsd を選択し、クリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-171">In the **Schema Files** dialog box, browse to C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB.DynamicResolution.Schemas, select NAOrderDoc.xsd, and then click **Open**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a0105-172">これは、テストに使用する左右のメッセージを作成するために使用された NAOrderDoc.xml メッセージを定義するスキーマです。</span><span class="sxs-lookup"><span data-stu-id="a0105-172">This is the schema that defines the NAOrderDoc.xml message, which was used to create the West and East messages you will use for testing.</span></span>  
  
4.  <span data-ttu-id="a0105-173">ファクト エクスプ ローラーで、NAOrderDoc.xsd をクリックし、**ドキュメントの種類**のプロパティ ウィンドウと 入力プロパティ**GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-173">In Facts Explorer, click NAOrderDoc.xsd, click the **Document Type** property in the Properties pane, and then type **GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a0105-174">これは、スキーマの完全修飾名です。</span><span class="sxs-lookup"><span data-stu-id="a0105-174">This is the fully qualified name of the schema.</span></span>  
  
5.  <span data-ttu-id="a0105-175">ファクト エクスプ ローラーで、 **NAOrderDoc.xsd**の順に展開および**OrderDoc**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-175">In Facts Explorer, expand **NAOrderDoc.xsd**, and then expand **OrderDoc**.</span></span>  
  
6.  <span data-ttu-id="a0105-176">ルール ウィンドウで、右クリック**条件**、 をポイント**述語**、順にクリック**等しい**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-176">In the Rule window, right-click **Conditions**, point to **Predicates**, and then click **Equal**.</span></span>  
  
7.  <span data-ttu-id="a0105-177">ファクト エクスプ ローラーからドラッグして、 **customerName**要素を**argument1**ノードの下**条件**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-177">From Facts Explorer, drag the **customerName** element to the **argument1** node under **Conditions**.</span></span>  
  
8.  <span data-ttu-id="a0105-178">をクリックして、 **argument2**ノード、および入力**GlobalBankWest**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-178">Click the **argument2** node, and then type **GlobalBankWest**.</span></span>  
  
9. <span data-ttu-id="a0105-179">ファクト エクスプ ローラーで、をクリックして、**ボキャブラリ**タブです。展開して、 **ESB です。行程**ボキャブラリ、展開**バージョン 1.1**、し、ドラッグ、**行程名の設定**定義**アクション**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-179">In Facts Explorer, click the **Vocabularies** tab. Expand the **ESB.Itinerary** vocabulary, expand **Version 1.1**, and then drag the **Set Itinerary Name** definition to **Actions**.</span></span>  
  
10. <span data-ttu-id="a0105-180">をクリックして**\<空の文字列 >**し入力**GlobalBankWestItinerary**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-180">Click **\<empty string>** and then type **GlobalBankWestItinerary**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a0105-181">このトピックの後半 GlobalBank 西からメッセージを処理するこの日程を作成します。</span><span class="sxs-lookup"><span data-stu-id="a0105-181">Later in this How-to topic, you will create this itinerary to process messages from GlobalBank West.</span></span>  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-east"></a><span data-ttu-id="a0105-182">GlobalBank 東部の顧客の選択ルールを追加するには</span><span class="sxs-lookup"><span data-stu-id="a0105-182">To add a selection rule for customer GlobalBank East</span></span>  
  
1.  <span data-ttu-id="a0105-183">ポリシー エクスプ ローラーで右クリックし、 **SetGlobalBankWestItinerary**ルールは、クリックして**コピー**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-183">In Policy Explorer, right-click the **SetGlobalBankWestItinerary** rule, and then click **Copy**.</span></span>  
  
2.  <span data-ttu-id="a0105-184">右クリック**バージョン 1.0 (未保存)**、クリックして**貼り付け**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-184">Right-click **Version 1.0 (not saved)**, and then click **Paste**.</span></span>  
  
3.  <span data-ttu-id="a0105-185">**新しいルールの名前** ダイアログ ボックスで、「 **SetGlobalBankEastItinerary**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-185">In the **New Rule Name** dialog box, type **SetGlobalBankEastItinerary**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="a0105-186">ポリシー エクスプ ローラーで、をクリックして、 **SetGlobalBankEastItinerary**ルール。</span><span class="sxs-lookup"><span data-stu-id="a0105-186">In Policy Explorer, click the **SetGlobalBankEastItinerary** rule.</span></span>  
  
5.  <span data-ttu-id="a0105-187">**条件**セクションを右クリックして**GlobalBankWest**、クリックして**引数の再設定**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-187">In the **Conditions** section, right-click **GlobalBankWest**, and then click **Reset argument**.</span></span>  
  
6.  <span data-ttu-id="a0105-188">をクリックして**argument2**、し、入力**GlobalBankEast**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-188">Click **argument2**, and then type **GlobalBankEast**.</span></span>  
  
7.  <span data-ttu-id="a0105-189">**アクション**セクションを右クリックして**GlobalBankWestItinerary**、クリックして**引数の再設定**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-189">In the **Actions** section, right-click **GlobalBankWestItinerary**, and then click **Reset argument**.</span></span>  
  
8.  <span data-ttu-id="a0105-190">をクリックして**\<空の文字列 >**し入力**GlobalBankEastItinerary です。**</span><span class="sxs-lookup"><span data-stu-id="a0105-190">Click **\<empty string>** and then type **GlobalBankEastItinerary.**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a0105-191">このトピックの後半 GlobalBank 東部からメッセージを処理するこの日程を作成します。</span><span class="sxs-lookup"><span data-stu-id="a0105-191">Later in this How-to topic, you will create this itinerary to process messages from GlobalBank East.</span></span>  
  
#### <a name="to-publish-and-deploy-the-policy"></a><span data-ttu-id="a0105-192">発行して、ポリシーを展開するには</span><span class="sxs-lookup"><span data-stu-id="a0105-192">To publish and deploy the policy</span></span>  
  
1.  <span data-ttu-id="a0105-193">ポリシー エクスプ ローラーで、、 **ResolveItineraryBasedOnCustomer**ポリシー、をクリックして**バージョン 1.0 (未保存)**、順にクリック**発行**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-193">In Policy Explorer, under the **ResolveItineraryBasedOnCustomer** policy, click **Version 1.0 (not saved)**, and then click **Publish**.</span></span>  
  
2.  <span data-ttu-id="a0105-194">ポリシー エクスプ ローラーで、、 **ResolveItineraryBasedOnCustomer**ポリシー、をクリックして**バージョン 1.0 - 公開済み**、順にクリック**展開**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-194">In Policy Explorer, under the **ResolveItineraryBasedOnCustomer** policy, click **Version 1.0 - Published**, and then click **Deploy**.</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model-for-globalbank-west-messages"></a><span data-ttu-id="a0105-195">GlobalBank 西部メッセージの ESB itinerary DSL モデルを作成するには</span><span class="sxs-lookup"><span data-stu-id="a0105-195">To create an ESB itinerary DSL model for GlobalBank West messages</span></span>  
  
1.  <span data-ttu-id="a0105-196"> **[!INCLUDE[vs2010](../includes/vs2010-md.md)]** C:\HowTos\Patterns\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="a0105-196">In **[!INCLUDE[vs2010](../includes/vs2010-md.md)]**, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="a0105-197">ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントし、**追加**、クリックして**新しい行程**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-197">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="a0105-198">**新しい項目の追加**ダイアログ ボックスの [テンプレート] ペインで、クリックして**ItineraryDsl**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-198">In the **Add New Item** dialog box, in the Templates pane, click **ItineraryDsl**.</span></span>  
  
4.  <span data-ttu-id="a0105-199">**名前**ボックスに、入力**GlobalBankWestItinerary**、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-199">In the **Name** box, type **GlobalBankWestItinerary**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-globalbank-west-itinerary"></a><span data-ttu-id="a0105-200">GlobalBank 西部旅行計画のプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="a0105-200">To configure the properties of the GlobalBank West itinerary</span></span>  
  
1.  <span data-ttu-id="a0105-201">Visual Studio でのデザイン画面をクリックして**GlobalBankWestItinerary.itinerary**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-201">In Visual Studio, click the design surface of **GlobalBankWestItinerary.itinerary**.</span></span> <span data-ttu-id="a0105-202">**GlobalBankWestItinerary**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="a0105-202">In the **GlobalBankWestItinerary** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a0105-203">**モデル エクスポーター**ドロップダウン リストをクリックして**データベース行程エクスポーター**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-203">In the **Model Exporter** drop-down list, click **Database Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="a0105-204">横にある省略記号ボタン (...) をクリックして、**行程データベース**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="a0105-204">Click the ellipsis button (...) next to the **Itinerary Database** property.</span></span>  
  
    3.  <span data-ttu-id="a0105-205">**接続プロパティ**ダイアログ ボックスで、itinerary リポジトリ データベースをホストする SQL Server を選択し、データベースの名前を指定 (既定の名前は**EsbItineraryDb**)。</span><span class="sxs-lookup"><span data-stu-id="a0105-205">In the **Connection Properties** dialog box, choose the SQL Server that hosts the itinerary repository database, and then specify the name of the database (the default name is **EsbItineraryDb**).</span></span>  
  
2.  <span data-ttu-id="a0105-206">**行程ステータス**ドロップダウン リストをクリックして**配置済み**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-206">In the **Itinerary Status** drop-down list, click **Deployed**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a0105-207">この手順では、; の中央リポジトリに旅行計画をエクスポートできます。日程を選択し、メッセージが受信したときに、このリポジトリからアタッチされます。</span><span class="sxs-lookup"><span data-stu-id="a0105-207">This step enables you to export the itinerary to a central repository; itineraries can be selected and attached from this repository when messages are received.</span></span> <span data-ttu-id="a0105-208">後で、BRI 競合回避モジュールを使用して受信メッセージを評価し、このリポジトリから適切な旅程を選択する行程セレクター パイプライン コンポーネントを構成します。</span><span class="sxs-lookup"><span data-stu-id="a0105-208">You will later configure the Itinerary Selector pipeline component to use the BRI resolver to evaluate inbound messages and select the appropriate itinerary from this repository.</span></span>  
  
#### <a name="to-define-the-structure-of-the-globalbank-west-itinerary"></a><span data-ttu-id="a0105-209">GlobalBank 西部行程の構造を定義するには</span><span class="sxs-lookup"><span data-stu-id="a0105-209">To define the structure of the GlobalBank West itinerary</span></span>  
  
1.  <span data-ttu-id="a0105-210">ツールボックスからドラッグして、**入り口**デザイン画面にモデル要素。</span><span class="sxs-lookup"><span data-stu-id="a0105-210">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="a0105-211">**OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="a0105-211">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a0105-212">クリックして、**名前**プロパティ、および入力**ReceiveNAOrder**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-212">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="a0105-213">**Extender**ドロップダウン リストをクリックして**入り口 ESB サービス拡張**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-213">In the **Extender** drop-down list, click **On-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="a0105-214">**BizTalk アプリケーション**ドロップダウン リストをクリックして**Microsoft.Practices.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-214">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="a0105-215">**受信ポート**ドロップダウン リストをクリックして**OnRamp.Itinerary**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-215">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="a0105-216">ツールボックスからドラッグして、**出口**デザイン画面に要素をモデル化の右側に配置し、 **ReceiveNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="a0105-216">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **ReceiveNAOrder** model element.</span></span> <span data-ttu-id="a0105-217">**OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="a0105-217">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a0105-218">クリックして、**名前**プロパティ、および入力**SendNAOrder**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-218">Click the **Name** property, and then type **SendNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="a0105-219">**Extender**ドロップダウン リストをクリックして**出口 ESB サービス拡張**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-219">In the **Extender** drop-down list, click **Off-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="a0105-220">**BizTalk アプリケーション**ドロップダウン リストをクリックして**GlobalBank.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-220">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="a0105-221">**送信ポート**ドロップダウン リストをクリックして**DynamicResolutionOneWay**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-221">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
3.  <span data-ttu-id="a0105-222">ツールボックスからドラッグ、**行程サービス**モデルをデザイン画面に要素との間に配置し、 **ReceiveNAOrder**モデル要素と**SendNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="a0105-222">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **ReceiveNAOrder** model element and the **SendNAOrder** model element.</span></span> <span data-ttu-id="a0105-223">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="a0105-223">In the **ItineraryService1** properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a0105-224">クリックして、**名前**プロパティ、および入力**RouteMessage**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-224">Click the **Name** property, and then type **RouteMessage**.</span></span>  
  
    2.  <span data-ttu-id="a0105-225">**行程サービス エクステンダー**ドロップダウン リストをクリックして**出口行程サービス拡張**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-225">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Itinerary Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="a0105-226">**出口**ドロップダウン リストで、展開**SendNAOrder**、クリックして**送信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-226">In the **Off-Ramp** drop-down list, expand **SendNAOrder**, and then click **Send Handlers**.</span></span>  
  
4.  <span data-ttu-id="a0105-227">右クリックし、**リゾルバー**のコレクション、 **RouteMessage**モデル要素をクリックして**新しいリゾルバーを追加**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-227">Right-click the **Resolver** collection of the **RouteMessage** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="a0105-228">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="a0105-228">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a0105-229">クリックして、**名前**プロパティ、および入力**StaticResolver**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-229">Click the **Name** property, and then type **StaticResolver**.</span></span>  
  
    2.  <span data-ttu-id="a0105-230">**リゾルバーの実装**ドロップダウン リストをクリックして**静的競合回避モジュールの拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="a0105-230">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="a0105-231">**トランスポート名**ドロップダウン リストをクリックして**ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-231">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="a0105-232">クリックして、**トランスポート場所**プロパティ、および入力**C:\HowTos\Out\West%MessageID%.xml**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-232">Click the **Transport Location** property, and then type **C:\HowTos\Out\West%MessageID%.xml**.</span></span>  
  
5.  <span data-ttu-id="a0105-233">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-233">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="a0105-234">接続をドラッグして、 **ReceiveNAOrder**モデル要素を**RouteMessage**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="a0105-234">Drag a connection from the **ReceiveNAOrder** model element to the  **RouteMessage** model element.</span></span>  
  
6.  <span data-ttu-id="a0105-235">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-235">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="a0105-236">接続をドラッグして、 **RouteMessage**モデル要素を**SendNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="a0105-236">Drag a connection from the **RouteMessage** model element to the **SendNAOrder** model element.</span></span>  
  
#### <a name="to-export-the-globalbank-west-model-to-the-itinerary-database"></a><span data-ttu-id="a0105-237">行程データベースに GlobalBank 西部モデルをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="a0105-237">To export the GlobalBank West model to the itinerary database</span></span>  
  
1.  <span data-ttu-id="a0105-238">Visual Studio でのデザイン画面を右クリックし、 **GlobalBankWestItinerary**行程をクリックして**モデルのエクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-238">In Visual Studio, right-click the design surface of the **GlobalBankWestItinerary** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a0105-239">Itinerary は行程データベースにエクスポートされてし、旅程セレクター コンポーネントによって使用されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="a0105-239">The itinerary has been exported to the itinerary database and can now be used by the Itinerary Selector component.</span></span>  
  
2.  <span data-ttu-id="a0105-240">すべてのプロジェクトの成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="a0105-240">Save all project artifacts.</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model-for-globalbank-east-message"></a><span data-ttu-id="a0105-241">GlobalBank 東部メッセージの ESB itinerary DSL モデルを作成するには</span><span class="sxs-lookup"><span data-stu-id="a0105-241">To create an ESB itinerary DSL model for GlobalBank East message</span></span>  
  
1.  <span data-ttu-id="a0105-242"> **[!INCLUDE[vs2010](../includes/vs2010-md.md)]** C:\HowTos\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="a0105-242">In **[!INCLUDE[vs2010](../includes/vs2010-md.md)]**, open C:\HowTos\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="a0105-243">ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントし、**追加**、クリックして**新しい行程**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-243">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="a0105-244">**新しい項目の追加**ダイアログ ボックスの [テンプレート] ペインで、クリックして**ItineraryDsl**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-244">In the **Add New Item** dialog box, in the Templates pane, click **ItineraryDsl**.</span></span>  
  
4.  <span data-ttu-id="a0105-245">**名前**ボックスに、入力**GlobalBankEastItinerary**、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-245">In the **Name** box, type **GlobalBankEastItinerary**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-globalbank-east-itinerary"></a><span data-ttu-id="a0105-246">GlobalBank 東部旅行計画のプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="a0105-246">To configure the properties of the GlobalBank East itinerary</span></span>  
  
1.  <span data-ttu-id="a0105-247">Visual Studio でのデザイン画面をクリックして**GlobalBankEastItinerary.itinerary**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-247">In Visual Studio, click the design surface of **GlobalBankEastItinerary.itinerary**.</span></span> <span data-ttu-id="a0105-248">**GlobalBankEastItinerary**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="a0105-248">In the **GlobalBankEastItinerary** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a0105-249">**モデル エクスポーター**ドロップダウン リストをクリックして**データベース行程エクスポーター**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-249">In the **Model Exporter** drop-down list, click **Database Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="a0105-250">横にある省略記号ボタン (...) をクリックして、**行程データベース**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="a0105-250">Click the ellipsis button (...) next to the **Itinerary Database** property.</span></span>  
  
    3.  <span data-ttu-id="a0105-251">**接続プロパティ**ダイアログ ボックスで、itinerary リポジトリ データベースをホストする SQL Server を選択し、データベースの名前を指定 (既定の名前は**EsbItineraryDb**)。</span><span class="sxs-lookup"><span data-stu-id="a0105-251">In the **Connection Properties** dialog box, choose the SQL Server that hosts the itinerary repository database, and then specify the name of the database (the default name is **EsbItineraryDb**).</span></span>  
  
2.  <span data-ttu-id="a0105-252">**行程ステータス**ドロップダウン リストをクリックして**配置済み**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-252">In the **Itinerary Status** drop-down list, click **Deployed**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a0105-253">この手順では、; の中央リポジトリに旅行計画をエクスポートできます。日程を選択し、メッセージが受信したときに、このリポジトリからアタッチされます。</span><span class="sxs-lookup"><span data-stu-id="a0105-253">This step enables you to export the itinerary to a central repository; itineraries can be selected and attached from this repository when messages are received.</span></span> <span data-ttu-id="a0105-254">後で、BRI 競合回避モジュールを使用して受信メッセージを評価し、このリポジトリから適切な旅程を選択する行程セレクター パイプライン コンポーネントを構成します。</span><span class="sxs-lookup"><span data-stu-id="a0105-254">You will later configure the Itinerary Selector pipeline component to use the BRI resolver to evaluate inbound messages and select the appropriate itinerary from this repository.</span></span>  
  
#### <a name="to-define-the-structure-of-the-globalbank-east-itinerary"></a><span data-ttu-id="a0105-255">GlobalBank 東部行程の構造を定義するには</span><span class="sxs-lookup"><span data-stu-id="a0105-255">To define the structure of the GlobalBank East itinerary</span></span>  
  
1.  <span data-ttu-id="a0105-256">ツールボックスからドラッグして、**入り口**デザイン画面にモデル要素。</span><span class="sxs-lookup"><span data-stu-id="a0105-256">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="a0105-257">**OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="a0105-257">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a0105-258">クリックして、**名前**プロパティ、および入力**ReceiveNAOrder**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-258">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="a0105-259">**Extender**ドロップダウン リストをクリックして**入り口 ESB サービス拡張**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-259">In the **Extender** drop-down list, click **On-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="a0105-260">**BizTalk アプリケーション**ドロップダウン リストをクリックして**Microsoft.Practices.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-260">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="a0105-261">**受信ポート**ドロップダウン リストをクリックして**OnRamp.Itinerary**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-261">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="a0105-262">ツールボックスからドラッグして、**出口**デザイン画面に要素をモデル化の右側に配置し、 **ReceiveNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="a0105-262">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **ReceiveNAOrder** model element.</span></span> <span data-ttu-id="a0105-263">**OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="a0105-263">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a0105-264">クリックして、**名前**プロパティ、および入力**SendNAOrder**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-264">Click the **Name** property, and then type **SendNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="a0105-265">**Extender**ドロップダウン リストをクリックして**出口 ESB サービス拡張**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-265">In the **Extender** drop-down list, click **Off-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="a0105-266">**BizTalk アプリケーション**ドロップダウン リストをクリックして**GlobalBank.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-266">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="a0105-267">**送信ポート**ドロップダウン リストをクリックして**DynamicResolutionOneWay**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-267">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
3.  <span data-ttu-id="a0105-268">ツールボックスからドラッグ、**行程サービス**モデルをデザイン画面に要素との間に配置し、 **ReceiveNAOrder**モデル要素と**SendNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="a0105-268">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **ReceiveNAOrder** model element and the **SendNAOrder** model element.</span></span> <span data-ttu-id="a0105-269">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="a0105-269">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a0105-270">クリックして、**名前**プロパティ、および入力**RouteMessage**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-270">Click the **Name** property, and then type **RouteMessage**.</span></span>  
  
    2.  <span data-ttu-id="a0105-271">**行程サービス エクステンダー**ドロップダウン リストをクリックして**出口行程サービス拡張**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-271">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Itinerary Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="a0105-272">**出口**ドロップダウン リストで、展開**SendNAOrder**、クリックして**送信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-272">In the **Off-Ramp** drop-down list, expand **SendNAOrder**, and then click **Send Handlers**.</span></span>  
  
4.  <span data-ttu-id="a0105-273">右クリックし、**リゾルバー**のコレクション、 **RouteMessage**モデル要素をクリックして**新しいリゾルバーを追加**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-273">Right-click the **Resolver** collection of the **RouteMessage** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="a0105-274">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="a0105-274">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a0105-275">クリックして、**名前**プロパティ、および入力**StaticResolver**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-275">Click the **Name** property, and then type **StaticResolver**.</span></span>  
  
    2.  <span data-ttu-id="a0105-276">**リゾルバーの実装**ドロップダウン リストをクリックして**静的競合回避モジュールの拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="a0105-276">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="a0105-277">**トランスポート名**ドロップダウン リストをクリックして**ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-277">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="a0105-278">クリックして、**トランスポート場所**プロパティ、および入力**C:\HowTos\Out\East%MessageID%.xml**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-278">Click the **Transport Location** property, and then type **C:\HowTos\Out\East%MessageID%.xml**.</span></span>  
  
5.  <span data-ttu-id="a0105-279">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-279">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="a0105-280">接続をドラッグして、 **ReceiveNAOrder**モデル要素を**RouteMessage**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="a0105-280">Drag a connection from the **ReceiveNAOrder** model element to the **RouteMessage** model element.</span></span>  
  
6.  <span data-ttu-id="a0105-281">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-281">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="a0105-282">接続をドラッグして、 **RouteMessage**モデル要素を**SendNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="a0105-282">Drag a connection from the **RouteMessage** model element to the **SendNAOrder** model element.</span></span>  
  
#### <a name="to-export-the-globalbank-east-model-to-the-itinerary-database"></a><span data-ttu-id="a0105-283">行程データベースに GlobalBank 東部モデルをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="a0105-283">To export the GlobalBank East model to the itinerary database</span></span>  
  
1.  <span data-ttu-id="a0105-284">Visual Studio でのデザイン画面を右クリックし、 **GlobalBankEastItinerary**行程をクリックして**モデルのエクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-284">In Visual Studio, right-click the design surface of the **GlobalBankEastItinerary** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a0105-285">Itinerary は行程データベースにエクスポートされてし、旅程セレクター コンポーネントによって使用されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="a0105-285">The itinerary has been exported to the itinerary database and can now be used by the Itinerary Selector component.</span></span>  
  
2.  <span data-ttu-id="a0105-286">すべてのプロジェクトの成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="a0105-286">Save all project artifacts.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="a0105-287">手順</span><span class="sxs-lookup"><span data-stu-id="a0105-287">Steps</span></span>  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a><span data-ttu-id="a0105-288">作成し、ESB 入り口を構成します。</span><span class="sxs-lookup"><span data-stu-id="a0105-288">To create and configure an ESB on-ramp</span></span>  
  
1.  <span data-ttu-id="a0105-289">をクリックして**開始**タスク バーで、をポイント**すべてのプログラム**、 をポイント **[!INCLUDE[prague](../includes/prague-md.md)]** 、順にクリック**BizTalk Server 管理**.</span><span class="sxs-lookup"><span data-stu-id="a0105-289">Click **Start** on the taskbar, point to **All Programs**, point to **[!INCLUDE[prague](../includes/prague-md.md)]**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="a0105-290">[!INCLUDE[prague](../includes/prague-md.md)]管理コンソールで、展開**BizTalk グループ**、展開**アプリケーション**、順に展開**Microsoft.Practices.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-290">In the [!INCLUDE[prague](../includes/prague-md.md)] Administration Console, expand **BizTalk Group**, expand **Applications**, and then expand **Microsoft.Practices.ESB**.</span></span>  
  
3.  <span data-ttu-id="a0105-291">右クリック**受信場所**、 をポイント**新規**、クリックして**一方向の受信場所**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-291">Right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
4.  <span data-ttu-id="a0105-292">**受信ポートの選択**ダイアログ ボックスで、をクリックして**OnRamp.Itinerary**、クリックして**[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-292">In the **Select a Receive Port** dialog box, click **OnRamp.Itinerary**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="a0105-293">**受信場所のプロパティ** ダイアログ ボックスで、**名前**ボックスに、入力**OnRamp.Itinerary.HowTo**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-293">In the **Receive Location Properties** dialog box, in the **Name** box, type **OnRamp.Itinerary.HowTo**.</span></span>  
  
6.  <span data-ttu-id="a0105-294">**型**ドロップダウン リストをクリックして**ファイル、**順にクリック**構成**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-294">In the **Type** drop-down list, click **FILE,** and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="a0105-295">**FILE トランスポートのプロパティ** ダイアログ ボックスで、**受信フォルダー**ボックスに、入力**C:\HowTos\DropFolder**、クリックして**ok**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-295">In the **FILE Transport Properties** dialog box, in the **Receive folder** box, type **C:\HowTos\DropFolder**, and then click **OK**.</span></span>  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a><span data-ttu-id="a0105-296">行程セレクター パイプライン コンポーネントを構成するには</span><span class="sxs-lookup"><span data-stu-id="a0105-296">To configure the Itinerary Selector pipeline component</span></span>  
  
1.  <span data-ttu-id="a0105-297">**受信場所のプロパティ**ダイアログ ボックスで、 をクリックして**ItinerarySelectReceiveXml**で、**受信パイプライン**ドロップダウン ボックスの一覧し、省略記号ボタン (...) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a0105-297">In the **Receive Location Properties** dialog box, click **ItinerarySelectReceiveXml** in the **Receive pipeline** drop-down list, and then click the ellipsis button (...).</span></span>  
  
2.  <span data-ttu-id="a0105-298">使用して、**パイプラインの構成**、次を構成するダイアログ ボックス**行程セレクター**コンポーネントのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="a0105-298">Use the **Configure Pipeline** dialog box to configure the following **Itinerary Selector** component properties:</span></span>  
  
    1.  <span data-ttu-id="a0105-299">クリックして、 **ItineraryFactKey**プロパティ、および入力**Resolver.Itinerary**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-299">Click the **ItineraryFactKey** property, and then type **Resolver.Itinerary**.</span></span>  
  
    2.  <span data-ttu-id="a0105-300">クリックして、 **ResolverConnectionString**プロパティ、および入力**BRI:\\\policy=ResolveItineraryBasedOnCustomer;useMsg=true;recognizeMessageFormat=true です。**</span><span class="sxs-lookup"><span data-stu-id="a0105-300">Click the **ResolverConnectionString** property, and then type **BRI:\\\policy=ResolveItineraryBasedOnCustomer;useMsg=true;recognizeMessageFormat=true;**</span></span>  
  
    3.  <span data-ttu-id="a0105-301">をクリックして**OK**を閉じる、**パイプラインの構成** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="a0105-301">Click **OK** to close the **Configure Pipeline** dialog box.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="a0105-302">この受信場所が、XML インターチェンジを逆アセンブル、XML 逆アセンブラー コンポーネントの構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="a0105-302">Because this receive location is disassembling an XML interchange, no XML Disassembler component configuration is required.</span></span>  
  
3.  <span data-ttu-id="a0105-303">をクリックして**OK**を閉じる、**受信場所のプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="a0105-303">Click **OK** to close the **Receive Location Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="a0105-304">[!INCLUDE[prague](../includes/prague-md.md)]管理コンソールで、右クリックし、 **OnRamp.Itinerary.HowTo**受信場所をクリックして**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-304">In the [!INCLUDE[prague](../includes/prague-md.md)] Administration Console, right-click the **OnRamp.Itinerary.HowTo** receive location, and then click **Enable**.</span></span>  
  
#### <a name="to-test-the-itinerary-selector-and-business-rules"></a><span data-ttu-id="a0105-305">行程セレクターとビジネス ルールをテストするには</span><span class="sxs-lookup"><span data-stu-id="a0105-305">To test the Itinerary Selector and business rules</span></span>  
  
1.  <span data-ttu-id="a0105-306">Windows エクスプローラで、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="a0105-306">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="a0105-307">コピー (移動しないでください) Batch.xml DropFolder フォルダーにします。</span><span class="sxs-lookup"><span data-stu-id="a0105-307">Copy (do not move) Batch.xml to the DropFolder folder.</span></span>  
  
3.  <span data-ttu-id="a0105-308">C:\HowTos\Out を参照します。1 つの West%MessageID%.xml メッセージと 2 つの East%MessageID%.xml メッセージがディレクトリに書き込まれたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a0105-308">Browse to C:\HowTos\Out. Verify that one West%MessageID%.xml message and two East%MessageID%.xml messages have been written to the directory.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a0105-309">メッセージが顧客の要素の値を除いて同一、行程セレクター パイプライン コンポーネントの解像度に基づいて、別の日程を使用して処理されました。</span><span class="sxs-lookup"><span data-stu-id="a0105-309">Although the messages are identical except for the value of the customer element, they were processed using different itineraries, based on the resolution of the Itinerary Selector pipeline component.</span></span>  
  
4.  <span data-ttu-id="a0105-310">[!INCLUDE[prague](../includes/prague-md.md)]管理コンソールで、右クリックし、OnRamp.Itinerary.HowTo 受信場所、をクリックを無効にします。</span><span class="sxs-lookup"><span data-stu-id="a0105-310">In the [!INCLUDE[prague](../includes/prague-md.md)] Administration Console, right-click the OnRamp.Itinerary.HowTo receive location, and then click Disable.</span></span>  
  
5.  <span data-ttu-id="a0105-311">後に、 **OnRamp.Itinerary.HowTo**受信場所が無効になっている、右クリックし、をクリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-311">After the **OnRamp.Itinerary.HowTo** receive location is disabled, right-click it, and then click **Delete**.</span></span> <span data-ttu-id="a0105-312">**受信場所のことを確認して削除**ダイアログ ボックスで、をクリックして**はい**です。</span><span class="sxs-lookup"><span data-stu-id="a0105-312">In the **Confirm delete receive location** dialog box, click **Yes**.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="a0105-313">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="a0105-313">Additional Resources</span></span>  
 <span data-ttu-id="a0105-314">詳細については、次の関連項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0105-314">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="a0105-315">方法: ビジネス ルール ポリシーを使用して、日程を選択</span><span class="sxs-lookup"><span data-stu-id="a0105-315">How to: Select an Itinerary Using a Business Rules Policy</span></span>](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [<span data-ttu-id="a0105-316">開発アクティビティ</span><span class="sxs-lookup"><span data-stu-id="a0105-316">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="a0105-317">インストールして、動的な解決サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="a0105-317">Installing and Running the Dynamic Resolution Sample</span></span>](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)  
  
-   [<span data-ttu-id="a0105-318">動的な解決を使用して、ルーティング</span><span class="sxs-lookup"><span data-stu-id="a0105-318">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)  
  
-   [<span data-ttu-id="a0105-319">メッセージのルーティング パターン</span><span class="sxs-lookup"><span data-stu-id="a0105-319">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)