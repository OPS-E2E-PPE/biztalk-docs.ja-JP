---
title: 'チュートリアル: 単純なビジネス ポリシーの作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 02d35735-dce2-4ee2-965e-dae307a125b0
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1eb4f21cf9311399ef6092b95fa818547679a240
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975821"
---
# <a name="walkthrough-creating-a-simple-business-policy"></a><span data-ttu-id="e1ee3-102">チュートリアル: 単純なビジネス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-102">Walkthrough: Creating a Simple Business Policy</span></span>
<span data-ttu-id="e1ee3-103">このチュートリアルは、ビジネス ルール作成ツールを使用してという名前の単純なビジネス ポリシーを作成する手順を示します**ProcessPurchaseOrder**という名前のルールを含む**ApprovedRule**です。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-103">This walkthrough provides step-by-step procedures for using the Business Rule Composer to create a simple business policy named **ProcessPurchaseOrder** containing a rule named **ApprovedRule**.</span></span> <span data-ttu-id="e1ee3-104">**ApprovedRule**ルールは、ユーザーが、ファクトとして XML ドキュメントを送信するを必要としの値を設定、**ステータス**フィールドをドキュメントに**Approved**場合、の値**数量**フィールドは、以下を**500**です。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-104">The **ApprovedRule** rule expects the user to submit an XML document as a fact, and sets the value of the **Status** field in the document to **Approved** if the value of the **Quantity** field is less than or equal to **500**.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e1ee3-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="e1ee3-105">Prerequisites</span></span>  
 <span data-ttu-id="e1ee3-106">このチュートリアルを実行するには、ビジネス ルール フレームワークの基礎を理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-106">You must be familiar with the basics of the Business Rules Framework to perform this walkthrough.</span></span> <span data-ttu-id="e1ee3-107">ビジネス ルール フレームワークのアーキテクチャの概要を読むことをお勧め、ビジネス ルール フレームワークを新しい場合は、[ビジネス ルール エンジン](../core/business-rules-engine.md)このチュートリアルを実行する前にします。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-107">If you are new to the Business Rules Framework, we recommend that you read the architecture overview of the Business Rules Framework at [Business Rules Engine](../core/business-rules-engine.md) before performing this walkthrough.</span></span>  
  
## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="e1ee3-108">このチュートリアルの概要</span><span class="sxs-lookup"><span data-stu-id="e1ee3-108">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="e1ee3-109">次の表に示すように、このチュートリアルには 2 つの手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-109">This walkthrough contains two procedures, as described in the following table.</span></span>  
  
|<span data-ttu-id="e1ee3-110">手順のタイトル</span><span class="sxs-lookup"><span data-stu-id="e1ee3-110">Procedure title</span></span>|<span data-ttu-id="e1ee3-111">手順の説明</span><span class="sxs-lookup"><span data-stu-id="e1ee3-111">Procedure description</span></span>|  
|---------------------|---------------------------|  
|<span data-ttu-id="e1ee3-112">PO スキーマ ファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="e1ee3-112">To create the PO schema file</span></span>|<span data-ttu-id="e1ee3-113">ドキュメントのスキーマを作成するための手順をわかりやすく説明、 **ProcessPurchaseOrder**ポリシーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-113">Provides step-by-step instructions for creating the schema for the document that the **ProcessPurchaseOrder** policy uses.</span></span>|  
|<span data-ttu-id="e1ee3-114">ProcessPurchaseOrder ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="e1ee3-114">To create the ProcessPurchaseOrder policy</span></span>|<span data-ttu-id="e1ee3-115">作成するための手順をわかりやすく説明、 **ProcessPurchaseOrder**ビジネス ルール作成ツールを使用してポリシー。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-115">Provides step-by-step instructions for creating the **ProcessPurchaseOrder** policy by using the Business Rule Composer.</span></span>|  
  
### <a name="to-create-the-po-schema-file"></a><span data-ttu-id="e1ee3-116">PO スキーマ ファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="e1ee3-116">To create the PO schema file</span></span>  
  
1.  <span data-ttu-id="e1ee3-117">**開始**] メニューの [開いている**メモ帳**です。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-117">On the **Start** menu, open **Notepad**.</span></span>  
  
2.  <span data-ttu-id="e1ee3-118">**[ファイル]** メニューの **[新規作成]** をポイントし、 **[ファイル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-118">On the **File** menu, point to **New**, and then click **File**.</span></span>  
  
3.  <span data-ttu-id="e1ee3-119">次の XML テキストをエディターにコピーします。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-119">Copy the following XML text to the editor:</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-16"?>  
    <xs:schema xmlns:b="http://schemas.microsoft.com/BizTalk/2003" xmlns="http://EAISolution.PurchaseOrder" targetNamespace="http://EAISolution.PurchaseOrder" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
      <xs:element name="PurchaseOrder">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element name="Header">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="ReqID" type="xs:string" />  
                  <xs:element name="Date" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
            <xs:element name="Item">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="Description" type="xs:string" />  
                  <xs:element name="Quantity" type="xs:int" />  
                  <xs:element name="UnitPrice" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
            <xs:element name="Status" type="xs:string" />  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:schema>  
    ```  
  
4.  <span data-ttu-id="e1ee3-120">**ファイル** メニューのをクリックして**TextFile1.txt に名前を付けて**です。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-120">On the **File** menu, click **Save TextFile1.txt As**.</span></span>  
  
5.  <span data-ttu-id="e1ee3-121">値を変更**名前を付けて保存型**から**テキスト ドキュメント (\*.txt)** に**すべてのファイル**です。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-121">Change the value for **Save As type** from **Text Documents(\*.txt)** to **All Files**.</span></span>  
  
6.  <span data-ttu-id="e1ee3-122">型**PO.xsd**で、**ファイル名**テキスト ボックスで、ディレクトリに移動**C:\BRE-Walkthroughs**の値を変更**エンコード**に**Unicode**  をクリックし、**保存**です。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-122">Type **PO.xsd** in the **File name** text box, change the directory to **C:\BRE-Walkthroughs**, change the value of **Encoding** to **Unicode** and then click **Save**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e1ee3-123">ディレクトリを作成**BRE チュートリアル** **c:\\** それが存在してをクリックしなかった場合**保存**です。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-123">Create the directory **BRE-Walkthroughs** under **C:\\** if it does not exist, and then click **Save**.</span></span>  
  
7.  <span data-ttu-id="e1ee3-124">メモ帳を閉じます。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-124">Close Notepad.</span></span>  
  
### <a name="to-create-the-processpurchaseorder-business-policy"></a><span data-ttu-id="e1ee3-125">ProcessPurchaseOrder ビジネス ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="e1ee3-125">To create the ProcessPurchaseOrder business policy</span></span>  
  
1.  <span data-ttu-id="e1ee3-126">**開始**] メニューの [開いている**ビジネス ルール作成ツール**です。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-126">On the **Start** menu, open **Business Rule Composer**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e1ee3-127">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-127">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="e1ee3-128">これを行うには、アプリケーションを右クリックし、**管理者として実行**です。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-128">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e1ee3-129">ビジネス ルール作成ツールを表示、**ルール ストアを開く** ダイアログ ボックスを初めてコンピューターで開かれたとき。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-129">The Business Rule Composer displays the **Open Rule Store** dialog box when it is opened for the first time on a computer.</span></span> <span data-ttu-id="e1ee3-130">表示される場合、**ルール ストアを開く**ダイアログ ボックスで、をクリックして**OK** SQL server 名とデータベース名を確認した後です。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-130">If you see the **Open Rule Store** dialog box, click **OK** after verifying the SQL server name and database name.</span></span>  
  
2.  <span data-ttu-id="e1ee3-131">ポリシー エクスプ ローラー ウィンドウで右クリック**ポリシー**、クリックして**新しいポリシーの追加**です。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-131">In the Policy Explorer window, right-click **Policies**, and then click **Add New Policy**.</span></span>  
  
3.  <span data-ttu-id="e1ee3-132">ポリシーの名前を編集 **"policy1"** を**ProcessPurchaseOrder** ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-132">Edit the name of the policy, **Policy1**, to **ProcessPurchaseOrder** and press ENTER.</span></span> <span data-ttu-id="e1ee3-133">ポリシーの名前を変更することも、**プロパティ**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-133">You can also change the name of the policy in the **Properties** window.</span></span>  
  
4.  <span data-ttu-id="e1ee3-134">右クリック**バージョン 1.0**、クリックして**新しいルールの追加**です。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-134">Right-click **Version 1.0**, and then click **AddNewRule**.</span></span>  
  
5.  <span data-ttu-id="e1ee3-135">ルールの名前を編集**Rule1**に**ApprovalRule** ENTER キーを押します**です。**</span><span class="sxs-lookup"><span data-stu-id="e1ee3-135">Edit the name of the rule from **Rule1** to **ApprovalRule** and press ENTER **.**</span></span> <span data-ttu-id="e1ee3-136">内のルールの名前を変更することも、**プロパティ**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-136">You can also change the name of the rule in the **Properties** window.</span></span>  
  
6.  <span data-ttu-id="e1ee3-137">[ファクト エクスプ ローラー] ウィンドウ、 **XML スキーマ**タブです。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-137">In the Facts Explorer window, click the **XML Schemas** tab.</span></span>  
  
7.  <span data-ttu-id="e1ee3-138">右クリック**スキーマ**、 をクリックして**参照**、クリックして、 **PO.xsd**先ほど作成したファイルです。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-138">Right-click **Schemas**, click **Browse**, and then select the **PO.xsd** file that you created earlier.</span></span>  
  
8.  <span data-ttu-id="e1ee3-139">[プロパティ] ウィンドウでの値を変更、**ドキュメントの種類**プロパティから**PO**に**RuleTest.PO**です。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-139">In the properties window, change the value of the **Document Type** property from **PO** to **RuleTest.PO**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e1ee3-140">という名前の BizTalk プロジェクトを作成して**RuleTest**後半、[チュートリアル: オーケストレーションからポリシーを呼び出す](../core/walkthrough-invoking-the-policy-from-an-orchestration.md)チュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-140">You will be creating a BizTalk project named **RuleTest** later in the [Walkthrough: Invoking the Policy from an Orchestration](../core/walkthrough-invoking-the-policy-from-an-orchestration.md) walkthrough.</span></span> <span data-ttu-id="e1ee3-141">チュートリアルでは、追加点で、 **PO.xsd**ファイルをプロジェクトを呼び出すオーケストレーションを作成、 **ProcessPurchaseOrder**ポリシー、およびポリシーをテストします。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-141">In that walkthrough, you will add the **PO.xsd** file to the project, create an orchestration that invokes the **ProcessPurchaseOrder** policy, and then test the policy.</span></span> <span data-ttu-id="e1ee3-142">オーケストレーションからポリシーをテストするを変更することを確認する必要があります、**ドキュメントの種類**プロパティを**\<プロジェクト名\>.\<SchemaName\>**、これは**RuleTest.PO**ここでします。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-142">To test the policy from the orchestration, you need to make sure that you change the **Document Type** property to **\<Project Name\>.\<SchemaName\>**, which is **RuleTest.PO** in this case.</span></span>  
  
     <span data-ttu-id="e1ee3-143">![BRE &#45;チュートリアル &#45;ChangeDocType](../core/media/e9a370fd-d9b2-48f0-ad0e-85a5428a9c21.gif "e9a370fd-d9b2-48f0-ad0e-85a5428a9c21")</span><span class="sxs-lookup"><span data-stu-id="e1ee3-143">![BRE&#45;Walkthrough&#45;ChangeDocType](../core/media/e9a370fd-d9b2-48f0-ad0e-85a5428a9c21.gif "e9a370fd-d9b2-48f0-ad0e-85a5428a9c21")</span></span>  
  
9. <span data-ttu-id="e1ee3-144">ファクト エクスプ ローラー ウィンドウで、 **PurchaseOrder**の順に展開および**項目**です。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-144">In the Facts Explorer window, expand **PurchaseOrder**, and then expand **Item**.</span></span>  
  
10. <span data-ttu-id="e1ee3-145">IF ペイン (上部) の右側を右クリックし**条件**をクリックして**述語**、順にクリック**以下**です。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-145">In the IF pane (top) on the right, right-click **Conditions**, click **Predicates**, and then click **LessThanEqual**.</span></span>  
  
     <span data-ttu-id="e1ee3-146">![ビジネス ルール作成ツール &#45;以下](../core/media/1e6418a6-5e5b-4f77-8b7e-dd31d0a753e7.gif "1e6418a6-5e5b-4f77-8b7e-dd31d0a753e7")</span><span class="sxs-lookup"><span data-stu-id="e1ee3-146">![Business Rule Composer &#45; Less Than or Equal](../core/media/1e6418a6-5e5b-4f77-8b7e-dd31d0a753e7.gif "1e6418a6-5e5b-4f77-8b7e-dd31d0a753e7")</span></span>  
  
11. <span data-ttu-id="e1ee3-147">ドラッグ、**数量**ノードを ファクト エクスプ ローラー ウィンドウから**argument1** IF ペイン。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-147">Drag the **Quantity** node from the Facts Explorer window to **argument1** in the IF pane.</span></span>  
  
     <span data-ttu-id="e1ee3-148">![ビジネス ルール作成ツール &#45;DragQuantity](../core/media/4742eca6-4a8a-401d-8989-cab4e8025fb3.gif "4742eca6-4a8a-401d-8989-cab4e8025fb3")</span><span class="sxs-lookup"><span data-stu-id="e1ee3-148">![Business Rule Composer &#45; DragQuantity](../core/media/4742eca6-4a8a-401d-8989-cab4e8025fb3.gif "4742eca6-4a8a-401d-8989-cab4e8025fb3")</span></span>  
  
     <span data-ttu-id="e1ee3-149">![ビジネス ルール作成ツール &#45;UseQuantity](../core/media/ee4f61b1-0f15-4329-b0b5-9badd21dcd61.gif "ee4f61b1-0f15-4329-b0b5-9badd21dcd61")</span><span class="sxs-lookup"><span data-stu-id="e1ee3-149">![Business Rule Composer&#45;UseQuantity](../core/media/ee4f61b1-0f15-4329-b0b5-9badd21dcd61.gif "ee4f61b1-0f15-4329-b0b5-9badd21dcd61")</span></span>  
  
12. <span data-ttu-id="e1ee3-150">IF ペインで、をクリックして**argument2**、型`500`、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-150">In the IF pane, click **argument2**, type `500`, and then press ENTER.</span></span>  
  
13. <span data-ttu-id="e1ee3-151">ドラッグ、**ステータス**ノード、ファクト エクスプ ローラー ウィンドウからビジネス ルール作成ツールの右側下部の THEN ペインにします。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-151">Drag the **Status** node from the Facts Explorer window to the THEN pane at the bottom-right side of Business Rule Composer.</span></span>  
  
     <span data-ttu-id="e1ee3-152">![ビジネス ルール作成ツール &#45; DragStatus](../core/media/3617251a-a192-4aec-9474-81f6290c0832.gif "3617251a-a192-4aec-9474-81f6290c0832")</span><span class="sxs-lookup"><span data-stu-id="e1ee3-152">![Business Rule Composer&#45;DragStatus](../core/media/3617251a-a192-4aec-9474-81f6290c0832.gif "3617251a-a192-4aec-9474-81f6290c0832")</span></span>  
  
14. <span data-ttu-id="e1ee3-153">[THEN] ペインでをクリックして**\<値を入力\>** し入力**Approved**です。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-153">In the THEN pane, click **\<Enter a value\>** and then type **Approved**.</span></span>  
  
15. <span data-ttu-id="e1ee3-154">ポリシー エクスプ ローラー ウィンドウで右クリック**バージョン 1.0 (未保存)**、クリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-154">In the Policy Explorer window, right-click **Version 1.0 (not saved)**, and then click **Save**.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="e1ee3-155">コメント</span><span class="sxs-lookup"><span data-stu-id="e1ee3-155">Comments</span></span>  
  
-   <span data-ttu-id="e1ee3-156">ポリシーには、1 つ以上のルールを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-156">A policy can have one or more rules.</span></span> <span data-ttu-id="e1ee3-157">別のルールを追加する**DeniedRule**で、[チュートリアル: ポリシーにルールを追加する](../core/walkthrough-adding-a-rule-to-the-policy.md)チュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-157">You will be adding another rule, **DeniedRule**, in the [Walkthrough: Adding a Rule to the Policy](../core/walkthrough-adding-a-rule-to-the-policy.md) walkthrough.</span></span>  
  
-   <span data-ttu-id="e1ee3-158">ポリシーが保存済みの状態であれば、ポリシーを変更して、さらにルールを追加したり、条件を変更したり、アクションを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-158">You can modify the policy to add more rules, change conditions, and change actions when the policy is in the Saved state.</span></span>  
  
-   <span data-ttu-id="e1ee3-159">指定してルールの実行を優先することができます、**優先度**ビジネス ルール作成ツールでルールのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-159">You can prioritize execution of rules by specifying the **Priority** property on rules in Business Rule Composer.</span></span> <span data-ttu-id="e1ee3-160">たとえばをクリックする、 **ApprovedRule**ポリシー エクスプ ローラー ウィンドウでノードを確認できます、**優先度**プロパティ ウィンドウでプロパティです。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-160">For example, if you click the **ApprovedRule** node in the Policy Explorer window, you can see the **Priority** property in the Properties window.</span></span> <span data-ttu-id="e1ee3-161">数字が大きくなるほど、そのルールの優先順位は高くなります。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-161">The larger the number, the higher the rule priority.</span></span>  
  
-   <span data-ttu-id="e1ee3-162">ポリシーのデータ ソースとして、XML スキーマ、データベース、または .NET アセンブリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-162">You can use an XML schema, a database, or a .NET assembly as a data source for the policy.</span></span> <span data-ttu-id="e1ee3-163">このチュートリアルでは、データ ソースとして XML スキーマを使用しました。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-163">In this walkthrough, you used an XML schema as a data source.</span></span> <span data-ttu-id="e1ee3-164">ポリシーを実行するには、ファクトとしてスキーマの XML ドキュメント インスタンスをルール エンジンに送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-164">You should submit an XML document instance of the schema as a fact to the rule engine to execute the policy.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="e1ee3-165">次の手順</span><span class="sxs-lookup"><span data-stu-id="e1ee3-165">Next Steps</span></span>  
 <span data-ttu-id="e1ee3-166">これで、このチュートリアルを完了すると、実行、[チュートリアル: ポリシーのテスト](../core/walkthrough-testing-the-policy.md)テストするための手順を説明するチュートリアル、 **ProcessPurchaseOrder**ポリシーします。このチュートリアルで作成します。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-166">Now that you have completed this walkthrough, perform the [Walkthrough: Testing the Policy](../core/walkthrough-testing-the-policy.md) walkthrough, which gives you step-by-step instructions for testing the **ProcessPurchaseOrder** policy you created in this walkthrough.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1ee3-167">参照</span><span class="sxs-lookup"><span data-stu-id="e1ee3-167">See Also</span></span>  
 [<span data-ttu-id="e1ee3-168">ビジネス ルールについて</span><span class="sxs-lookup"><span data-stu-id="e1ee3-168">About Business Rules</span></span>](../core/about-business-rules.md)