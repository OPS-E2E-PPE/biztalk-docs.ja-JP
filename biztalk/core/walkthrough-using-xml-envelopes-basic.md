---
title: 'チュートリアル: XML エンベロープ (Basic) の使用 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- content-based routing, promoting properties
- promoting properties, routing messages
- promoting properties, content-based routing
- routing, messages
- routing, promoting properties
ms.assetid: 02d0c596-0cfe-4bae-9f1b-d7dbc17e18a9
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b637f37c8d0953417ca628204fe299318b91266
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022096"
---
# <a name="walkthrough-using-xml-envelopes-basic"></a><span data-ttu-id="77b5a-102">チュートリアル: を使用して XML エンベロープ (Basic)</span><span class="sxs-lookup"><span data-stu-id="77b5a-102">Walkthrough: Using XML Envelopes (Basic)</span></span>
<span data-ttu-id="77b5a-103">この例では、架空のエラー追跡システムを実装して、基本的な XML エンベロープの逆アセンブルを示します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-103">This example demonstrates basic XML envelope disassembly by implementing part of a fictitious error-tracking system.</span></span> <span data-ttu-id="77b5a-104">この例は次の要件を満たしています。</span><span class="sxs-lookup"><span data-stu-id="77b5a-104">The example meets the following requirements:</span></span>  
  
1.  <span data-ttu-id="77b5a-105">エラー メッセージは社内のさまざまな物理的な場所でログに記録され、集中管理された場所に送信されて、さまざまなバックエンド システムに振り分けられます。</span><span class="sxs-lookup"><span data-stu-id="77b5a-105">Error messages are logged at various physical sites within the company and sent to a central location for processing into various back-end systems.</span></span>  
  
2.  <span data-ttu-id="77b5a-106">エラー メッセージは XML 形式で書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="77b5a-106">Error messages are written in XML format.</span></span>  
  
3.  <span data-ttu-id="77b5a-107">エラー メッセージは、エンベロープなしで単独に送信したり、エンベロープに含まれるバッチとして送信したりできます。</span><span class="sxs-lookup"><span data-stu-id="77b5a-107">An error message can be sent singly without an envelope or as a batch contained within an envelope.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="77b5a-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="77b5a-108">Prerequisites</span></span>  
 <span data-ttu-id="77b5a-109">この例では、BizTalk プロジェクトの作成、アセンブリへの署名、BizTalk Server 管理コンソールでのアプリケーションとポートの表示に慣れている必要があります。</span><span class="sxs-lookup"><span data-stu-id="77b5a-109">For this example you need to be comfortable with creating BizTalk projects, signing an assembly, and using the BizTalk Server Administration console to view applications and ports.</span></span> <span data-ttu-id="77b5a-110">またはずで紹介したアイデアに[チュートリアル: 基本的な BizTalk アプリケーションの展開](../core/walkthrough-deploying-a-basic-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-110">You should also be comfortable with the ideas presented in [Walkthrough: Deploying a Basic BizTalk Application](../core/walkthrough-deploying-a-basic-biztalk-application.md).</span></span>  
  
## <a name="what-this-example-does"></a><span data-ttu-id="77b5a-111">この例の処理</span><span class="sxs-lookup"><span data-stu-id="77b5a-111">What This Example Does</span></span>  
 <span data-ttu-id="77b5a-112">この例では、エンベロープ スキーマを定義し、XmlDisassembler パイプラインを使用して、単一のエラー メッセージまたはエラー メッセージのバッチを含む受信メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-112">The example processes inbound messages containing either a single error message or a batch of error messages by defining an envelope schema and using the XmlDisassembler pipeline.</span></span>  
  
## <a name="example"></a><span data-ttu-id="77b5a-113">例</span><span class="sxs-lookup"><span data-stu-id="77b5a-113">Example</span></span>  
 <span data-ttu-id="77b5a-114">この例を作成するには、以下で概要を説明している手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-114">To create the example, follow the steps outlined in the following sections.</span></span>  
  
### <a name="create-a-new-biztalk-project"></a><span data-ttu-id="77b5a-115">新しい BizTalk プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="77b5a-115">Create a New BizTalk Project</span></span>  
 <span data-ttu-id="77b5a-116">BizTalk プロジェクトを作成する必要があるソリューションをビルドする前に、ソリューションに厳密な名前が付いていることを確認し、アプリケーション名をそのソリューションに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="77b5a-116">Before building a solution you need to create a BizTalk project, ensure that it is strongly named, and assign it an application name.</span></span> <span data-ttu-id="77b5a-117">アプリケーション名を割り当てると、そのソリューションが BizTalk Server によって既定の BizTalk アプリケーションに配置されるのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="77b5a-117">Assigning an application name prevents BizTalk Server from deploying the solution into the default BizTalk application.</span></span>  
  
##### <a name="to-create-and-configure-a-new-biztalk-project"></a><span data-ttu-id="77b5a-118">新しい BizTalk プロジェクトを作成および構成するには</span><span class="sxs-lookup"><span data-stu-id="77b5a-118">To create and configure a new BizTalk project</span></span>  
  
1. <span data-ttu-id="77b5a-119">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用して新しい BizTalk プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-119">Use [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to create a new BizTalk project.</span></span> <span data-ttu-id="77b5a-120">プロジェクトを呼び出す**BasicXMLEnvelope**します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-120">Call the project **BasicXMLEnvelope**.</span></span>  
  
2. <span data-ttu-id="77b5a-121">キー ファイルを作成してプロジェクトに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="77b5a-121">Generate a key file and assign it to the project.</span></span> <span data-ttu-id="77b5a-122">このタスクの詳細については、次を参照してください。[厳密な名前のアセンブリ キー ファイルを構成する方法](../core/how-to-configure-a-strong-name-assembly-key-file.md)します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-122">For more information about this task, see [How to Configure a Strong Name Assembly Key File](../core/how-to-configure-a-strong-name-assembly-key-file.md).</span></span>  
  
3. <span data-ttu-id="77b5a-123">プロジェクトの配置構成プロパティを割り当てて、**アプリケーション名**設定と**ホスト インスタンスを再起動**に`True`します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-123">In the deployment configuration properties for the project, assign an **Application Name** and set **Restart Host Instances** to `True`.</span></span> <span data-ttu-id="77b5a-124">このフラグを設定すると、キャッシュされたアセンブリのインスタンスを消去するようにホストに通知されます。</span><span class="sxs-lookup"><span data-stu-id="77b5a-124">Setting this flag tells the host to clear any cached instances of the assembly.</span></span>  
  
### <a name="create-the-error-schema"></a><span data-ttu-id="77b5a-125">エラー スキーマの作成</span><span class="sxs-lookup"><span data-stu-id="77b5a-125">Create the Error Schema</span></span>  
 <span data-ttu-id="77b5a-126">このステップではエラー スキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-126">In this step you create the Error schema.</span></span> <span data-ttu-id="77b5a-127">システムのキー メッセージを定義します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-127">It defines the key message for the system.</span></span>  
  
##### <a name="to-create-the-error-schema"></a><span data-ttu-id="77b5a-128">エラー スキーマを作成するには</span><span class="sxs-lookup"><span data-stu-id="77b5a-128">To create the Error schema</span></span>  
  
1. <span data-ttu-id="77b5a-129">プロジェクトに "エラー" という名前の新しいスキーマを追加します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-129">Add a new schema named "Error" to the project.</span></span>  
  
2. <span data-ttu-id="77b5a-130">変更するスキーマのターゲットの名前空間 **http://BasicXMLEnvelope**します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-130">Change the target namespace for the schema to **http://BasicXMLEnvelope**.</span></span>  
  
3. <span data-ttu-id="77b5a-131">スキーマ プロパティを変更**Element FormDefault**下、 **[詳細設定]** カテゴリ**Qualified**します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-131">Change the schema property **Element FormDefault** under the **Advanced** category to **Qualified**.</span></span> <span data-ttu-id="77b5a-132">これは、ローカルに宣言された要素を、ターゲットの名前空間を使用してインスタンス ドキュメント内で修飾する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-132">This indicates that locally declared elements must be qualified by the target namespace in an instance document.</span></span>  
  
4. <span data-ttu-id="77b5a-133">ルート ノードの名前を "エラー" に変更し、次に示す型の 5 つの子要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-133">Rename the root node "Error" and create five child elements with the types indicated:</span></span>  
  
   - <span data-ttu-id="77b5a-134">ID、xs:int 型</span><span class="sxs-lookup"><span data-stu-id="77b5a-134">ID, xs:int</span></span>  
  
   - <span data-ttu-id="77b5a-135">Type、xs:int 型</span><span class="sxs-lookup"><span data-stu-id="77b5a-135">Type, xs:int</span></span>  
  
   - <span data-ttu-id="77b5a-136">Priority、xs:string 型</span><span class="sxs-lookup"><span data-stu-id="77b5a-136">Priority, xs:string</span></span>  
  
   - <span data-ttu-id="77b5a-137">Description、xs:string 型</span><span class="sxs-lookup"><span data-stu-id="77b5a-137">Description, xs:string</span></span>  
  
   - <span data-ttu-id="77b5a-138">ErrorDateTime、xs:string 型</span><span class="sxs-lookup"><span data-stu-id="77b5a-138">ErrorDateTime, xs:string</span></span>  
  
     <span data-ttu-id="77b5a-139">スキーマは以下のようになります。</span><span class="sxs-lookup"><span data-stu-id="77b5a-139">Your schema should look like the following:</span></span>  
  
     <span data-ttu-id="77b5a-140">![完成したエラー スキーマ](../core/media/error-schema.gif "error_schema")</span><span class="sxs-lookup"><span data-stu-id="77b5a-140">![Completed Error schema](../core/media/error-schema.gif "error_schema")</span></span>  
  
5. <span data-ttu-id="77b5a-141">このスキーマに対応するサンプル メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-141">Create a sample message for this schema.</span></span> <span data-ttu-id="77b5a-142">このメッセージは、エンベロープの外部の単一メッセージが適切に処理されているかどうかを確認するために使用します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-142">This is used to verify that single messages outside of an envelope are processed properly.</span></span> <span data-ttu-id="77b5a-143">以下に、サンプル メッセージの例を示します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-143">An example sample message is:</span></span>  
  
   ```  
   <Error xmlns="http://BasicXMLEnvelope">  
     <ID>1</ID>  
     <Type>5</Type>  
     <Priority>Low</Priority>  
     <Description>Sprocket widget prints reports slowly.</Description>  
     <ErrorDateTime>1999-05-31T13:20:00.000-05:00</ErrorDateTime>  
   </Error>  
   ```  
  
    <span data-ttu-id="77b5a-144">このメッセージをプロジェクト ディレクトリ内のファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-144">Save this message in a file in the project directory.</span></span>  
  
### <a name="create-the-envelope-schema"></a><span data-ttu-id="77b5a-145">エンベロープ スキーマの作成</span><span class="sxs-lookup"><span data-stu-id="77b5a-145">Create the Envelope Schema</span></span>  
 <span data-ttu-id="77b5a-146">エンベロープには、1 つ以上のエラー メッセージが格納されます。</span><span class="sxs-lookup"><span data-stu-id="77b5a-146">The envelope contains one or more error messages.</span></span> <span data-ttu-id="77b5a-147">この基本の例のエンベロープには、独自のプロパティおよび要素がありません。</span><span class="sxs-lookup"><span data-stu-id="77b5a-147">In this basic example, the envelope does not have properties and elements of its own.</span></span>  
  
##### <a name="to-create-the-envelope-schema"></a><span data-ttu-id="77b5a-148">エンベロープ スキーマを作成するには</span><span class="sxs-lookup"><span data-stu-id="77b5a-148">To create the envelope schema</span></span>  
  
1.  <span data-ttu-id="77b5a-149">BasicXMLEnvelope プロジェクトに "エンベロープ" という名前の新しいスキーマを追加します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-149">Add a new schema named "Envelope" to the BasicXMLEnvelope project.</span></span>  
  
2.  <span data-ttu-id="77b5a-150">ターゲット名前空間を変更 **http://BasicXMLEnvelope**します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-150">Change the target namespace to **http://BasicXMLEnvelope**.</span></span>  
  
3.  <span data-ttu-id="77b5a-151">ルート ノードの名前を "ルート" から "エンベロープ" に変更します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-151">Change the name of the root node from "Root" to "Envelope".</span></span>  
  
4.  <span data-ttu-id="77b5a-152">次に、スキーマをエンベロープ スキーマとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="77b5a-152">Now mark the schema as an envelope schema.</span></span> <span data-ttu-id="77b5a-153">をクリックして、 **\<スキーマ\>** ノード。</span><span class="sxs-lookup"><span data-stu-id="77b5a-153">Click the **\<Schema\>** node.</span></span> <span data-ttu-id="77b5a-154">プロパティ ペインで、スキーマ参照プロパティを設定**エンベロープ**に`OK`します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-154">In the Properties pane, set the schema reference property **Envelope** to `OK`.</span></span>  
  
5.  <span data-ttu-id="77b5a-155">設定、**ボディ XPath**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="77b5a-155">Set the **Body XPath** property.</span></span> <span data-ttu-id="77b5a-156">これを行うには、クリックして、**エンベロープ**ノード。</span><span class="sxs-lookup"><span data-stu-id="77b5a-156">To do this, click the **Envelope** node.</span></span> <span data-ttu-id="77b5a-157">[プロパティ] ウィンドウで、省略記号ボタンをクリックします (**.。**) ボタン、**ボディ XPath**プロパティで、**エンベロープ**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-157">In the Properties window, click the ellipsis (**...**) button in the **Body XPath** property, select **Envelope**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="77b5a-158">[エンベロープ] ノードにすべての子要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-158">Add an Any element child to the Envelope node.</span></span> <span data-ttu-id="77b5a-159">この要素にエラー メッセージが含まれます。</span><span class="sxs-lookup"><span data-stu-id="77b5a-159">The error message will be contained in this element.</span></span> <span data-ttu-id="77b5a-160">スキーマは以下のようになります。</span><span class="sxs-lookup"><span data-stu-id="77b5a-160">Your schema should look like the following:</span></span>  
  
     <span data-ttu-id="77b5a-161">![完成したエンベロープ スキーマ](../core/media/envelope-schema.gif "envelope_schema")</span><span class="sxs-lookup"><span data-stu-id="77b5a-161">![Completed envelope schema](../core/media/envelope-schema.gif "envelope_schema")</span></span>  
  
7.  <span data-ttu-id="77b5a-162">エンベロープと 1 つ以上のサンプル メッセージを含むサンプル メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-162">Create a sample message containing an envelope and one or more sample messages.</span></span> <span data-ttu-id="77b5a-163">以下に、メッセージの例を示します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-163">An example message is:</span></span>  
  
    ```  
    <Envelope xmlns="http://BasicXMLEnvelope">  
      <Error>  
        <ID>102</ID>  
        <Type>0</Type>  
        <Priority>High</Priority>  
        <Description>Sprocket query fails.</Description>  
        <ErrorDateTime>1999-05-31T13:20:00.000-05:00</ErrorDateTime>  
      </Error>  
      <Error>  
        <ID>16502</ID>  
        <Type>2</Type>  
        <Priority>Low</Priority>  
        <Description>Time threshold exceeded.</Description>  
        <ErrorDateTime>1999-05-31T13:20:00.000-05:00</ErrorDateTime>  
      </Error>  
    </Envelope>  
    ```  
  
     <span data-ttu-id="77b5a-164">このメッセージをプロジェクト ディレクトリ内のファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-164">Save this message in a file in the project directory.</span></span>  
  
### <a name="deploy-and-configure-the-send-and-receive-ports"></a><span data-ttu-id="77b5a-165">受信ポートと送信ポートの配置および構成</span><span class="sxs-lookup"><span data-stu-id="77b5a-165">Deploy and Configure the Send and Receive Ports</span></span>  
 <span data-ttu-id="77b5a-166">スキーマを作成したら、次はプロジェクトをコンパイルして配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77b5a-166">With the schemas created, you need to compile and deploy the project.</span></span> <span data-ttu-id="77b5a-167">プロジェクトを配置すると、BizTalk Server 管理コンソールを使用して、送信ポートと受信ポートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="77b5a-167">After it is deployed, you can use the BizTalk Server Administration console to configure the send and receive ports.</span></span>  
  
##### <a name="to-deploy-basicxmlenvelope"></a><span data-ttu-id="77b5a-168">BasicXMLEnvelope を配置するには</span><span class="sxs-lookup"><span data-stu-id="77b5a-168">To deploy BasicXMLEnvelope</span></span>  
  
1. <span data-ttu-id="77b5a-169">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、選択 **[BasicXMLEnvelope の配置**ビルド] メニューから。</span><span class="sxs-lookup"><span data-stu-id="77b5a-169">From [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], choose **Deploy BasicXMLEnvelope** from the Build menu.</span></span> <span data-ttu-id="77b5a-170">この操作により、BizTalk Server に "BasicXMLEnvelope" アプリケーションとしてビルドおよび配置されます。</span><span class="sxs-lookup"><span data-stu-id="77b5a-170">This will build and deploy it to BizTalk Server as the application "BasicXMLEnvelope".</span></span>  
  
2. <span data-ttu-id="77b5a-171">BizTalk Server 管理コンソールで、**アプリケーション**ことを確認するグループ **[basicxmlenvelope]** がカスタム アプリケーションとして存在します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-171">In the BizTalk Server Administration console, expand the **Applications** group to verify that **BasicXMLEnvelope** is present as a custom application.</span></span>  
  
##### <a name="to-configure-the-receive-port"></a><span data-ttu-id="77b5a-172">受信ポートを構成するには</span><span class="sxs-lookup"><span data-stu-id="77b5a-172">To configure the receive port</span></span>  
  
1.  <span data-ttu-id="77b5a-173">下の"Receive"という名前のディレクトリを作成する Windows エクスプ ローラーを使用して、 **BasicXMLEnvelope**プロジェクト ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="77b5a-173">Use Windows Explorer to create a directory named "Receive" under the **BasicXMLEnvelope** project directory.</span></span>  
  
2.  <span data-ttu-id="77b5a-174">BizTalk Server 管理コンソールで、 **basicxmlenvelope**アプリケーションを右クリックして**受信ポート**、 をポイント**新規**順にクリックします**一方向受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-174">In the BizTalk Server Administration console, expand the **BasicXMLEnvelope** application, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
3.  <span data-ttu-id="77b5a-175">**受信ポートのプロパティ** ダイアログ ボックスで、ポートを"Receive"の名前を設定します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-175">In the **Receive Port Properties** dialog box, set the name of the port to "Receive".</span></span>  
  
4.  <span data-ttu-id="77b5a-176">受信場所を右クリックし、をクリックし、**新規**受信ポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-176">Right-click Receive Locations, and then click **New** to add a receive port.</span></span> <span data-ttu-id="77b5a-177">新しいポートに "ReceiveError" という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="77b5a-177">Name the new port "ReceiveError".</span></span> <span data-ttu-id="77b5a-178">設定、**受信パイプライン**に**XMLReceive**します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-178">Set the **Receive Pipeline** to **XMLReceive**.</span></span> <span data-ttu-id="77b5a-179">**トランスポートの種類**を選択します**ファイル**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-179">For **Transport Type**, select **FILE**, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="77b5a-180">上記で作成した受信ディレクトリを選択し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-180">Select the receive directory created above and click **OK**.</span></span> <span data-ttu-id="77b5a-181">受信ポートが正しく構成されます。</span><span class="sxs-lookup"><span data-stu-id="77b5a-181">Your receive port should now be configured.</span></span> <span data-ttu-id="77b5a-182">クリックして**OK**を閉じます。</span><span class="sxs-lookup"><span data-stu-id="77b5a-182">Click **OK** to close.</span></span>  
  
##### <a name="to-configure-the-send-port"></a><span data-ttu-id="77b5a-183">送信ポートを構成するには</span><span class="sxs-lookup"><span data-stu-id="77b5a-183">To configure the send port</span></span>  
  
1.  <span data-ttu-id="77b5a-184">下の"Send"という名前のディレクトリを作成する Windows エクスプ ローラーを使用して、 **BasicXMLEnvelope**プロジェクト ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="77b5a-184">Use Windows Explorer to create a directory named "Send" under the **BasicXMLEnvelope** project directory.</span></span>  
  
2.  <span data-ttu-id="77b5a-185">BizTalk Server 管理コンソールで、 **basicxmlenvelope** 、アプリケーションを右クリックして**送信ポート**、 をポイント**新規**、順にクリックします**静的な一方向**します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-185">In the BizTalk Server Administration console, expand the **BasicXMLEnvelope** application, right-click **Send Ports**, point to **New**, and then click **Static One-Way**.</span></span>  
  
3.  <span data-ttu-id="77b5a-186">**送信ポートのプロパティ** ダイアログ ボックスで、「送信」をポートの名前を設定します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-186">In the **Send Port Properties** dialog box, set the name of the port to "Send".</span></span>  
  
4.  <span data-ttu-id="77b5a-187">**トランスポートの種類**を選択します**ファイル**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-187">For **Transport Type**, select **FILE**, and then click **Configure**.</span></span> <span data-ttu-id="77b5a-188">先ほど作成した送信ディレクトリにコピー先のフォルダーを設定し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-188">Set the destination folder to the send directory you created earlier and click **OK**.</span></span>  
  
5.  <span data-ttu-id="77b5a-189">クリックして**フィルター**し、1 つのフィルターを追加します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-189">Click **Filters** and add a single filter:</span></span>  
  
    -   <span data-ttu-id="77b5a-190">BTS.MessageType == **http://BasicXMLEnvelope#Error**</span><span class="sxs-lookup"><span data-stu-id="77b5a-190">BTS.MessageType == **http://BasicXMLEnvelope#Error**</span></span>  
  
6.  <span data-ttu-id="77b5a-191">クリックして**OK**送信ポートの構成を完了します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-191">Click **OK** to complete the send port configuration.</span></span> <span data-ttu-id="77b5a-192">送信ポートが正しく構成されます。</span><span class="sxs-lookup"><span data-stu-id="77b5a-192">Your send port should be configured.</span></span>  
  
### <a name="run-the-example"></a><span data-ttu-id="77b5a-193">例の実行</span><span class="sxs-lookup"><span data-stu-id="77b5a-193">Run the Example</span></span>  
 <span data-ttu-id="77b5a-194">次に、例を実行します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-194">It is now time to run the example.</span></span> <span data-ttu-id="77b5a-195">BizTalk Server 管理コンソールを使用して BasicXMLEnvelope アプリケーションを起動した後、テスト ファイルを受信場所にコピーして、送信場所に生成される内容を観察します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-195">After using the BizTalk Server Management console to start the BasicXMLEnvelope application, you will copy the test files to the receive location and observe what is produced in the send location.</span></span>  
  
##### <a name="to-run-the-basicxmlenvelope-example"></a><span data-ttu-id="77b5a-196">BasicXMLEnvelope 例を実行するには</span><span class="sxs-lookup"><span data-stu-id="77b5a-196">To run the BasicXMLEnvelope example</span></span>  
  
1.  <span data-ttu-id="77b5a-197">右クリックし、BizTalk Server 管理コンソールで、 **BasicXMLEnvelope**アプリケーションをクリック**開始**します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-197">In the BizTalk Server Administration console, right-click the **BasicXMLEnvelope** application and then click **Start**.</span></span> <span data-ttu-id="77b5a-198">これにより、送信ポートと受信ポートが参加し、開始されます。</span><span class="sxs-lookup"><span data-stu-id="77b5a-198">This will enlist and start the send and receive ports.</span></span>  
  
2.  <span data-ttu-id="77b5a-199">各サンプル ファイルを受信ディレクトリに置きます。</span><span class="sxs-lookup"><span data-stu-id="77b5a-199">Drop each of the sample files into the receive directory.</span></span> <span data-ttu-id="77b5a-200">上記のサンプルを使用する場合は、処理された後、送信場所で 3 つの各エラー メッセージを探します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-200">If you use the samples given earlier, you should find three individual error messages in the send location when processing is completed.</span></span>  
  
## <a name="extending-the-example"></a><span data-ttu-id="77b5a-201">例の拡張</span><span class="sxs-lookup"><span data-stu-id="77b5a-201">Extending the Example</span></span>  
 <span data-ttu-id="77b5a-202">この例は、他の要件に合わせて拡張できます。</span><span class="sxs-lookup"><span data-stu-id="77b5a-202">You can extend the example to accommodate other requirements.</span></span> <span data-ttu-id="77b5a-203">このセクションでは、2 つの一般的なシナリオを取り上げます。</span><span class="sxs-lookup"><span data-stu-id="77b5a-203">This section addresses two common scenarios:</span></span>  
  
- <span data-ttu-id="77b5a-204">エラーのバッチがエンベロープで送信される場合、逆アセンブルでの個別のメッセージの失敗によって、失敗でないメッセージの処理が停止しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="77b5a-204">If a batch of errors is submitted within an envelope, individual message failures in disassembly should not prohibit other nonfailing messages from being further processed.</span></span>  
  
- <span data-ttu-id="77b5a-205">エラーは、優先度に基づいて異なる場所に配信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77b5a-205">Errors should be delivered to different locations based on error priority.</span></span> <span data-ttu-id="77b5a-206">優先度の高いメッセージは迅速に処理され、それ以外の優先度のメッセージは通常のチャネルで処理されます。</span><span class="sxs-lookup"><span data-stu-id="77b5a-206">High-priority messages are expedited while other priorities are handled through normal channels.</span></span>  
  
  <span data-ttu-id="77b5a-207">次のセクションでは、例を拡張してこれらの要件に適合させます。</span><span class="sxs-lookup"><span data-stu-id="77b5a-207">The following sections extend the example to handle these requirements.</span></span>  
  
### <a name="recoverable-interchange-processing"></a><span data-ttu-id="77b5a-208">回復可能なインターチェンジ処理</span><span class="sxs-lookup"><span data-stu-id="77b5a-208">Recoverable Interchange Processing</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="77b5a-209"> は、回復可能なインターチェンジ処理をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="77b5a-209"> supports recoverable interchange processing.</span></span> <span data-ttu-id="77b5a-210">この機能を使用すると、逆アセンブル時のメッセージのバッチの失敗がバッチとしてではなく、個別に発生するように設定できます。</span><span class="sxs-lookup"><span data-stu-id="77b5a-210">By using this feature, you can ensure that batches of messages fail individually in disassembly and not as a batch.</span></span>  
  
##### <a name="to-configure-the-example-for-recoverable-interchange-processing"></a><span data-ttu-id="77b5a-211">回復可能なインターチェンジ処理の例を構成するには</span><span class="sxs-lookup"><span data-stu-id="77b5a-211">To configure the example for recoverable interchange processing</span></span>  
  
1.  <span data-ttu-id="77b5a-212">BizTalk Server 管理コンソールで、 **basicxmlenvelope**アプリケーション、 をクリックして**受信ポート**、受信ポートをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="77b5a-212">In the BizTalk Server Administration console, expand the **BasicXMLEnvelope** application, click **Receive Ports**, and then double-click the Receive port.</span></span> <span data-ttu-id="77b5a-213">これは既に作成したポートです。</span><span class="sxs-lookup"><span data-stu-id="77b5a-213">This is the port you created previously.</span></span>  
  
2.  <span data-ttu-id="77b5a-214">**受信ポートのプロパティ**ダイアログ ボックスで、をクリックして**受信場所**します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-214">In the **Receive Port Properties** dialog box, click **Receive Locations**.</span></span> <span data-ttu-id="77b5a-215">クリックして**プロパティ**を起動、 **ReceiveError 受信場所のプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="77b5a-215">Click **Properties** to bring up the **ReceiveError Receive Location Properties** dialog box.</span></span> <span data-ttu-id="77b5a-216">省略記号をクリックします (**.**) ボタンを**受信パイプライン**します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-216">Click the ellipsis (**...**) button for the **Receive Pipeline**.</span></span>  
  
3.  <span data-ttu-id="77b5a-217">**パイプラインの構成 - XMLReceive**ダイアログ ボックスで、セット、**回復可能なインターチェンジ処理**プロパティを`True`、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-217">In the **Configure Pipeline - XMLReceive** dialog box, set the **Recoverable Interchange Processing** property to `True`, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="77b5a-218">をクリックして **[ok]** を閉じる、**受信場所のプロパティ**クリックしてダイアログ ボックスで、 **[ok]** を閉じる、**受信ポートのプロパティ**ダイアログボックス。</span><span class="sxs-lookup"><span data-stu-id="77b5a-218">Click **OK** to close the **Receive Location Properties** dialog box, and then click **OK** to close the **Receive Port Properties** dialog box.</span></span>  
  
##### <a name="to-create-a-sample-file-and-run-the-example"></a><span data-ttu-id="77b5a-219">サンプル ファイルを作成して例を実行するには</span><span class="sxs-lookup"><span data-stu-id="77b5a-219">To create a sample file and run the example</span></span>  
  
1.  <span data-ttu-id="77b5a-220">サンプル ファイルを作成するには、例で作成したエンベロープ サンプル ファイルのコピーを作成し、存在しない名前空間を Error インスタンスの 1 つに追加してファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-220">To create a sample file, make a copy of the envelope sample file created in the example, add a nonexistent namespace to one of the Error instances, and then save the file:</span></span>  
  
    ```  
    <Envelope xmlns="http://BasicXMLEnvelope">  
      <Error>  
        <ID>102</ID>  
        <Type>0</Type>  
        <Priority>High</Priority>  
        <Description>Sprocket query fails to return any sprockets even though some exist</Description>  
        <ErrorDateTime>1999-05-31T13:20:00.000-05:00</ErrorDateTime>  
      </Error>  
      <Error xmlns="http://ThisIsAnError">  
        <ID>16502</ID>  
        <Type>2</Type>  
        <Priority>Low</Priority>  
        <Description>Time threshold exceeded.</Description>  
        <ErrorDateTime>1999-05-31T13:20:00.000-05:00</ErrorDateTime>  
      </Error>  
    </Envelope>  
    ```  
  
2.  <span data-ttu-id="77b5a-221">BizTalk Server 管理コンソールで、次のようにクリックします。**アプリケーション**いることを確認し、 **[basicxmlenvelope]** アプリケーションが実行されています。</span><span class="sxs-lookup"><span data-stu-id="77b5a-221">In the BizTalk Server Administration console, click **Applications** and verify that the **BasicXMLEnvelope** application is running.</span></span>  
  
3.  <span data-ttu-id="77b5a-222">受信場所にメッセージをドロップします。</span><span class="sxs-lookup"><span data-stu-id="77b5a-222">Drop the message in the receive location.</span></span> <span data-ttu-id="77b5a-223">処理後、送信場所で最初のメッセージを探し、保留キューで 2 番目のメッセージや優先度の低いメッセージを探します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-223">After processing, you should find the first message in the send location and the second, low-priority, message in the Suspended queue.</span></span>  
  
### <a name="content-based-routing-cbr"></a><span data-ttu-id="77b5a-224">コンテンツ ベースのルーティング (CBR)</span><span class="sxs-lookup"><span data-stu-id="77b5a-224">Content-Based Routing (CBR)</span></span>  
 <span data-ttu-id="77b5a-225">コンテンツ ベースのルーティングを使用すると、コンテンツに基づいてメッセージをルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="77b5a-225">You can use content-based routing to route messages based on their content.</span></span> <span data-ttu-id="77b5a-226">このシナリオでは、優先度が “高” のメッセージは 1 つの送信場所に送られ、優先度が "中" または "低" のメッセージは別の送信場所に送られるという優先度に基づいたルーティングが行われます。</span><span class="sxs-lookup"><span data-stu-id="77b5a-226">In this scenario, routing is based on priority, with High messages going to one send location and Low and Medium messages going to a different send location.</span></span>  
  
 <span data-ttu-id="77b5a-227">サンプルを拡張するには、次の作業を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="77b5a-227">To extend the sample, you must complete the following tasks:</span></span>  
  
1.  <span data-ttu-id="77b5a-228">昇格、**優先度**BasicXMLEnvelope プロジェクトの [エラー] スキーマのフィールド。</span><span class="sxs-lookup"><span data-stu-id="77b5a-228">Promote the **Priority** field in the Error schema in the BasicXMLEnvelope project.</span></span> <span data-ttu-id="77b5a-229">コンテンツ ベースのルーティングでは、メッセージのルーティングに昇格させたプロパティが必要です。</span><span class="sxs-lookup"><span data-stu-id="77b5a-229">Content-based routing relies on promoted properties to route messages.</span></span> <span data-ttu-id="77b5a-230">詳細については、次を参照してください。[プロパティの昇格](../core/promoting-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-230">For more information, see [Promoting Properties](../core/promoting-properties.md).</span></span>  
  
2.  <span data-ttu-id="77b5a-231">2 つの追加の送信ポートを作成および構成します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-231">Create and configure two additional send ports.</span></span> <span data-ttu-id="77b5a-232">これらのポートでは、適切なメッセージを受信するためにフィルターを使用します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-232">The ports use a filter to ensure they receive appropriate messages.</span></span>  
  
##### <a name="to-promote-the-priority-field-in-the-error-schema"></a><span data-ttu-id="77b5a-233">[エラー] スキーマの "優先度" フィールドを昇格させるには</span><span class="sxs-lookup"><span data-stu-id="77b5a-233">To promote the Priority field in the Error schema</span></span>  
  
1. <span data-ttu-id="77b5a-234">**[Basicxmlenvelope]** でプロジェクトを開き[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、オープン、**エラー**スキーマを展開し、**エラー**ノード。</span><span class="sxs-lookup"><span data-stu-id="77b5a-234">With the **BasicXMLEnvelope** project open in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the **Error** schema and expand the **Error** node.</span></span>  
  
2. <span data-ttu-id="77b5a-235">右クリックし、**優先度**要素を指す**昇格**、 をクリックし、**クイック昇格**。</span><span class="sxs-lookup"><span data-stu-id="77b5a-235">Right-click the **Priority** element, point to **Promote**, and then click **Quick Promote**.</span></span>  
  
3. <span data-ttu-id="77b5a-236">クリックして**OK**昇格させたプロパティの新しいプロパティ スキーマの追加を確認します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-236">Click **OK** to confirm the addition of a new property schema for the promoted properties.</span></span>  
  
4. <span data-ttu-id="77b5a-237">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、ソリューション エクスプ ローラーで、新しいプロパティ スキーマ PropertySchema.xsd を開きます。</span><span class="sxs-lookup"><span data-stu-id="77b5a-237">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], in Solution Explorer, open the new property schema PropertySchema.xsd.</span></span> <span data-ttu-id="77b5a-238">スキーマの"Field1"を削除します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-238">Remove "Field1" from the schema.</span></span>  
  
5. <span data-ttu-id="77b5a-239">次に、ソリューションを再コンパイルして再配置します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-239">Now recompile and redeploy the solution.</span></span> <span data-ttu-id="77b5a-240">[ビルド] メニューの [BasicXMLEnvelope の配置] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-240">On the Build menu, choose Deploy BasicXMLEnvelope.</span></span>  
  
6. <span data-ttu-id="77b5a-241">プロジェクトは、ソリューションが再配置されるときにホスト インスタンスを再設定するように構成されました。</span><span class="sxs-lookup"><span data-stu-id="77b5a-241">The project was configured to reset the host instance when the solution is redeployed.</span></span> <span data-ttu-id="77b5a-242">これを変更した場合、ホストを停止して開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77b5a-242">If you have changed this, you need to stop and start the host.</span></span>  
  
##### <a name="to-configure-the-low-and-medium-priority-send-port"></a><span data-ttu-id="77b5a-243">優先度が低または中程度の送信ポートを構成するには</span><span class="sxs-lookup"><span data-stu-id="77b5a-243">To configure the low and medium-priority send port</span></span>  
  
1.  <span data-ttu-id="77b5a-244">"SendLowMediumPriority"という名前のディレクトリを作成する Windows エクスプ ローラーを使用して、 **BasicXMLEnvelope**プロジェクト ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="77b5a-244">Use Windows Explorer to create a directory named "SendLowMediumPriority" under the **BasicXMLEnvelope** project directory.</span></span>  
  
2.  <span data-ttu-id="77b5a-245">BizTalk Server 管理コンソールで、 **basicxmlenvelope** 、アプリケーションを右クリックして**送信ポート**、 をポイント**新規**、順にクリックします**静的な一方向**します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-245">In the BizTalk Server Administration console, expand the **BasicXMLEnvelope** application, right-click **Send Ports**, point to **New**, and then click **Static One-Way**.</span></span>  
  
3.  <span data-ttu-id="77b5a-246">**送信ポートのプロパティ** ダイアログ ボックスで、ポートを"SendLowMediumPriority"の名前を設定します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-246">In the **Send Port Properties** dialog box, set the name of the port to "SendLowMediumPriority".</span></span>  
  
4.  <span data-ttu-id="77b5a-247">**トランスポートの種類**を選択します**ファイル**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-247">For **Transport Type**, select **FILE**, and then click **Configure**.</span></span> <span data-ttu-id="77b5a-248">送信先のフォルダーを、先ほど作成したディレクトリに設定します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-248">Set the destination folder to the directory you created earlier.</span></span> <span data-ttu-id="77b5a-249">クリックして**OK**を閉じます。</span><span class="sxs-lookup"><span data-stu-id="77b5a-249">Click **OK** to close.</span></span>  
  
5.  <span data-ttu-id="77b5a-250">クリックして**フィルター**と 3 つのフィルター式を追加します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-250">Click **Filters** and add three filter expressions:</span></span>  
  
    -   <span data-ttu-id="77b5a-251">BTS します。MessageType = =http://BasicXMLEnvelope#Errorと</span><span class="sxs-lookup"><span data-stu-id="77b5a-251">BTS.MessageType == http://BasicXMLEnvelope#Error And</span></span>  
  
    -   <span data-ttu-id="77b5a-252">BasicXMLEnvelope.PropertySchema.Priority == Low Or</span><span class="sxs-lookup"><span data-stu-id="77b5a-252">BasicXMLEnvelope.PropertySchema.Priority == Low Or</span></span>  
  
    -   <span data-ttu-id="77b5a-253">BasicXMLEnvelope.PropertySchema.Priority == Medium</span><span class="sxs-lookup"><span data-stu-id="77b5a-253">BasicXMLEnvelope.PropertySchema.Priority == Medium</span></span>  
  
6.  <span data-ttu-id="77b5a-254">クリックして**OK**低または中程度の送信ポートの構成を完了します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-254">Click **OK** to complete the low and medium-priority send port configuration.</span></span>  
  
##### <a name="to-configure-the-high-priority-send-port"></a><span data-ttu-id="77b5a-255">優先度の高い送信ポートを構成するには</span><span class="sxs-lookup"><span data-stu-id="77b5a-255">To configure the high-priority send port</span></span>  
  
1.  <span data-ttu-id="77b5a-256">"SendHighPriority"という名前のディレクトリを作成する Windows エクスプ ローラーを使用して、 **BasicXMLEnvelope**プロジェクト ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="77b5a-256">Use Windows Explorer to create a directory named "SendHighPriority" under the **BasicXMLEnvelope** project directory.</span></span>  
  
2.  <span data-ttu-id="77b5a-257">BizTalk Server 管理コンソールで、 **basicxmlenvelope** 、アプリケーションを右クリックして**送信ポート**、 をポイント**新規**、順にクリックします**静的な一方向**します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-257">In the BizTalk Server Administration console, expand the **BasicXMLEnvelope** application, right-click **Send Ports**, point to **New**, and then click **Static One-Way**.</span></span>  
  
3.  <span data-ttu-id="77b5a-258">**送信ポートのプロパティ** ダイアログ ボックスで、ポートを"SendHighPriority"の名前を設定します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-258">In the **Send Port Properties** dialog box, set the name of the port to "SendHighPriority".</span></span>  
  
4.  <span data-ttu-id="77b5a-259">**トランスポートの種類**を選択します**ファイル**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-259">For **Transport Type**, select **FILE**, and then click **Configure**.</span></span> <span data-ttu-id="77b5a-260">送信先のフォルダーを、先ほど作成したディレクトリに設定します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-260">Set the destination folder to the directory you created earlier.</span></span> <span data-ttu-id="77b5a-261">クリックして**OK**を閉じます。</span><span class="sxs-lookup"><span data-stu-id="77b5a-261">Click **OK** to close.</span></span>  
  
5.  <span data-ttu-id="77b5a-262">クリックして**フィルター**し、2 つのフィルター式を追加します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-262">Click **Filters** and add two filter expressions:</span></span>  
  
    -   <span data-ttu-id="77b5a-263">BTS します。MessageType = =http://BasicXMLEnvelope#Errorと</span><span class="sxs-lookup"><span data-stu-id="77b5a-263">BTS.MessageType == http://BasicXMLEnvelope#Error And</span></span>  
  
    -   <span data-ttu-id="77b5a-264">BasicXMLEnvelope.PropertySchema.Priority == High</span><span class="sxs-lookup"><span data-stu-id="77b5a-264">BasicXMLEnvelope.PropertySchema.Priority == High</span></span>  
  
6.  <span data-ttu-id="77b5a-265">クリックして**OK**優先度の高い送信ポートの構成を完了します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-265">Click **OK** to complete the high-priority send port configuration.</span></span>  
  
##### <a name="to-test-the-routing-solution"></a><span data-ttu-id="77b5a-266">ソリューションのルーティングをテストするには</span><span class="sxs-lookup"><span data-stu-id="77b5a-266">To test the routing solution</span></span>  
  
1.  <span data-ttu-id="77b5a-267">BizTalk Server 管理コンソールで、展開、**アプリケーション**グループで、右クリックし、 **[basicxmlenvelope]** アプリケーション、およびクリック**開始**。</span><span class="sxs-lookup"><span data-stu-id="77b5a-267">In the BizTalk Server Administration console, expand the **Applications** group, right-click the **BasicXMLEnvelope** application, and then click **Start**.</span></span> <span data-ttu-id="77b5a-268">確認するメッセージが表示されたら、クリックして**開始**します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-268">When prompted to confirm, click **Start**.</span></span> <span data-ttu-id="77b5a-269">これにより、新しい送信ポートが参加します。</span><span class="sxs-lookup"><span data-stu-id="77b5a-269">This enlists the new send ports.</span></span>  
  
2.  <span data-ttu-id="77b5a-270">受信場所にテスト メッセージをドロップします。</span><span class="sxs-lookup"><span data-stu-id="77b5a-270">Drop the test message into the receive location.</span></span> <span data-ttu-id="77b5a-271">エラー メッセージが異なる送信場所にルーティングされていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="77b5a-271">Notice how error messages are routed to the different send locations:</span></span>  
  
    -   <span data-ttu-id="77b5a-272">優先度が低、中、または高に設定され、メッセージ処理を失敗していないエラー メッセージは、元の送信場所 (基本例で構成されています) と優先度に基づく送信場所の両方にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="77b5a-272">Error messages that have a Low, Medium, or High priority and do not fail message processing are routed both to the original send location (configured in the core example) and the send location by priority.</span></span> <span data-ttu-id="77b5a-273">優先度が低または中に設定されたメッセージでは、元の送信場所と優先度が低または中の送信場所の両方にコピーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="77b5a-273">For messages with a Low or Medium priority, a copy appears in both the original send location and the Low/Medium send location.</span></span>  
  
    -   <span data-ttu-id="77b5a-274">回復可能なインターチェンジ処理が有効になっている場合、失敗したエラー メッセージのルーティングは行われませんが、失敗しなかったメッセージは想定どおり適切にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="77b5a-274">If recoverable interchange processing is enabled, the failed error message is not routed and the nonfailed message is properly routed as expected.</span></span> <span data-ttu-id="77b5a-275">失敗したメッセージがルーティングされないのは、そのメッセージの種類と、構成したフィルターで使用される種類が一致しないためです。</span><span class="sxs-lookup"><span data-stu-id="77b5a-275">The failed message is not routed because its message type does not match the type used in the configured filters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77b5a-276">参照</span><span class="sxs-lookup"><span data-stu-id="77b5a-276">See Also</span></span>  
 <span data-ttu-id="77b5a-277">[回復可能なインターチェンジ処理](../core/recoverable-interchange-processing.md) </span><span class="sxs-lookup"><span data-stu-id="77b5a-277">[Recoverable Interchange Processing](../core/recoverable-interchange-processing.md) </span></span>  
 <span data-ttu-id="77b5a-278">[プロパティの昇格](../core/promoting-properties.md) </span><span class="sxs-lookup"><span data-stu-id="77b5a-278">[Promoting Properties](../core/promoting-properties.md) </span></span>  
 [<span data-ttu-id="77b5a-279">CBRSample (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="77b5a-279">CBRSample (BizTalk Server Sample)</span></span>](../core/cbrsample-biztalk-server-sample.md)