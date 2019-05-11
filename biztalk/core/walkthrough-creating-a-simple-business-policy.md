---
title: 'チュートリアル: 単純なビジネス ポリシーを作成する |Microsoft Docs'
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
ms.openlocfilehash: 8ad7eb892174c850d991ae9fdc7cdff0b4fbf241
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262134"
---
# <a name="walkthrough-creating-a-simple-business-policy"></a><span data-ttu-id="83870-102">チュートリアル: 単純なビジネス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="83870-102">Walkthrough: Creating a Simple Business Policy</span></span>
<span data-ttu-id="83870-103">このチュートリアルは、ビジネス ルール作成ツールを使用してという名前の単純なビジネス ポリシーを作成する手順を示します**ProcessPurchaseOrder**という名前の規則を含む**ApprovedRule**します。</span><span class="sxs-lookup"><span data-stu-id="83870-103">This walkthrough provides step-by-step procedures for using the Business Rule Composer to create a simple business policy named **ProcessPurchaseOrder** containing a rule named **ApprovedRule**.</span></span> <span data-ttu-id="83870-104">**ApprovedRule**ルールは、ファクトとして XML ドキュメントを送信するユーザーを想定し、値を設定、**状態**フィールドをドキュメントに**Approved**場合、の値**数量**フィールドと等しいまたはそれよりも小さい**500**します。</span><span class="sxs-lookup"><span data-stu-id="83870-104">The **ApprovedRule** rule expects the user to submit an XML document as a fact, and sets the value of the **Status** field in the document to **Approved** if the value of the **Quantity** field is less than or equal to **500**.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="83870-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="83870-105">Prerequisites</span></span>  
 <span data-ttu-id="83870-106">このチュートリアルを実行するビジネス ルール フレームワークの基本を理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83870-106">You must be familiar with the basics of the Business Rules Framework to perform this walkthrough.</span></span> <span data-ttu-id="83870-107">ビジネス ルール フレームワークのアーキテクチャの概要を確認することをお勧め、ビジネス ルール フレームワークに慣れていない場合[ビジネス ルール エンジン](../core/business-rules-engine.md)このチュートリアルを実行する前にします。</span><span class="sxs-lookup"><span data-stu-id="83870-107">If you are new to the Business Rules Framework, we recommend that you read the architecture overview of the Business Rules Framework at [Business Rules Engine](../core/business-rules-engine.md) before performing this walkthrough.</span></span>  
  
## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="83870-108">このチュートリアルの概要</span><span class="sxs-lookup"><span data-stu-id="83870-108">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="83870-109">次の表に示すように、このチュートリアルには 2 つの手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="83870-109">This walkthrough contains two procedures, as described in the following table.</span></span>  
  
|<span data-ttu-id="83870-110">プロシージャ タイトル</span><span class="sxs-lookup"><span data-stu-id="83870-110">Procedure title</span></span>|<span data-ttu-id="83870-111">手順の説明</span><span class="sxs-lookup"><span data-stu-id="83870-111">Procedure description</span></span>|  
|---------------------|---------------------------|  
|<span data-ttu-id="83870-112">PO スキーマ ファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="83870-112">To create the PO schema file</span></span>|<span data-ttu-id="83870-113">ドキュメントのスキーマを作成するための手順について説明します、 **ProcessPurchaseOrder**ポリシーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="83870-113">Provides step-by-step instructions for creating the schema for the document that the **ProcessPurchaseOrder** policy uses.</span></span>|  
|<span data-ttu-id="83870-114">ProcessPurchaseOrder ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="83870-114">To create the ProcessPurchaseOrder policy</span></span>|<span data-ttu-id="83870-115">作成するための手順について説明します、 **ProcessPurchaseOrder**ビジネス ルール作成ツールを使用してポリシー。</span><span class="sxs-lookup"><span data-stu-id="83870-115">Provides step-by-step instructions for creating the **ProcessPurchaseOrder** policy by using the Business Rule Composer.</span></span>|  
  
### <a name="to-create-the-po-schema-file"></a><span data-ttu-id="83870-116">PO スキーマ ファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="83870-116">To create the PO schema file</span></span>  
  
1.  <span data-ttu-id="83870-117">**開始**] メニューの [open**メモ帳**します。</span><span class="sxs-lookup"><span data-stu-id="83870-117">On the **Start** menu, open **Notepad**.</span></span>  
  
2.  <span data-ttu-id="83870-118">**ファイル**メニューで、**新規**、 をクリックし、**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="83870-118">On the **File** menu, point to **New**, and then click **File**.</span></span>  
  
3.  <span data-ttu-id="83870-119">次の XML テキストをエディターにコピーします。</span><span class="sxs-lookup"><span data-stu-id="83870-119">Copy the following XML text to the editor:</span></span>  
  
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
  
4.  <span data-ttu-id="83870-120">**ファイル** メニューのをクリックして**TextFile1.txt に名前を付けて**します。</span><span class="sxs-lookup"><span data-stu-id="83870-120">On the **File** menu, click **Save TextFile1.txt As**.</span></span>  
  
5.  <span data-ttu-id="83870-121">値を変更**名前を付けて保存型**から**テキスト ドキュメント (\*.txt)** に**すべてのファイル**します。</span><span class="sxs-lookup"><span data-stu-id="83870-121">Change the value for **Save As type** from **Text Documents(\*.txt)** to **All Files**.</span></span>  
  
6.  <span data-ttu-id="83870-122">型**PO.xsd**で、**ファイル名**テキスト ボックスに、ディレクトリに移動します**C:\BRE-Walkthroughs**の値を変更**エンコード**に**Unicode**し**保存**します。</span><span class="sxs-lookup"><span data-stu-id="83870-122">Type **PO.xsd** in the **File name** text box, change the directory to **C:\BRE-Walkthroughs**, change the value of **Encoding** to **Unicode** and then click **Save**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="83870-123">ディレクトリを作成**BRE チュートリアル** **c:\\** が存在して、をクリックしなかった場合**保存**します。</span><span class="sxs-lookup"><span data-stu-id="83870-123">Create the directory **BRE-Walkthroughs** under **C:\\** if it does not exist, and then click **Save**.</span></span>  
  
7.  <span data-ttu-id="83870-124">メモ帳を閉じます。</span><span class="sxs-lookup"><span data-stu-id="83870-124">Close Notepad.</span></span>  
  
### <a name="to-create-the-processpurchaseorder-business-policy"></a><span data-ttu-id="83870-125">ProcessPurchaseOrder ビジネス ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="83870-125">To create the ProcessPurchaseOrder business policy</span></span>  
  
1. <span data-ttu-id="83870-126">**開始**] メニューの [open**ビジネス ルール作成ツール**します。</span><span class="sxs-lookup"><span data-stu-id="83870-126">On the **Start** menu, open **Business Rule Composer**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="83870-127">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="83870-127">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="83870-128">これを行うには、アプリケーションを右クリックし、**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="83870-128">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="83870-129">ビジネス ルール作成ツールが表示されます、**ルール ストアを開く** ダイアログ ボックスをコンピューターに初めて開かれたとき。</span><span class="sxs-lookup"><span data-stu-id="83870-129">The Business Rule Composer displays the **Open Rule Store** dialog box when it is opened for the first time on a computer.</span></span> <span data-ttu-id="83870-130">表示された場合、**ルール ストアを開く**ダイアログ ボックスで、をクリックして**OK** SQL server 名とデータベース名を確認した後。</span><span class="sxs-lookup"><span data-stu-id="83870-130">If you see the **Open Rule Store** dialog box, click **OK** after verifying the SQL server name and database name.</span></span>  
  
2. <span data-ttu-id="83870-131">ポリシー エクスプ ローラー ウィンドウで右クリック**ポリシー**、 をクリックし、**新しいポリシーの追加**します。</span><span class="sxs-lookup"><span data-stu-id="83870-131">In the Policy Explorer window, right-click **Policies**, and then click **Add New Policy**.</span></span>  
  
3. <span data-ttu-id="83870-132">ポリシーの名前を編集**Policy1**を**ProcessPurchaseOrder** ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="83870-132">Edit the name of the policy, **Policy1**, to **ProcessPurchaseOrder** and press ENTER.</span></span> <span data-ttu-id="83870-133">ポリシーの名前を変更することも、**プロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="83870-133">You can also change the name of the policy in the **Properties** window.</span></span>  
  
4. <span data-ttu-id="83870-134">右クリックして**バージョン 1.0**、 をクリックし、**新しいルールの追加**します。</span><span class="sxs-lookup"><span data-stu-id="83870-134">Right-click **Version 1.0**, and then click **AddNewRule**.</span></span>  
  
5. <span data-ttu-id="83870-135">ルールの名前を編集**Rule1**に**ApprovalRule** ENTER キーを押します<strong>します。</strong></span><span class="sxs-lookup"><span data-stu-id="83870-135">Edit the name of the rule from **Rule1** to **ApprovalRule** and press ENTER<strong>.</strong></span></span> <span data-ttu-id="83870-136">ルールの名前を変更することも、**プロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="83870-136">You can also change the name of the rule in the **Properties** window.</span></span>  
  
6. <span data-ttu-id="83870-137">[ファクト エクスプ ローラー] ウィンドウ、 **XML スキーマ**タブ。</span><span class="sxs-lookup"><span data-stu-id="83870-137">In the Facts Explorer window, click the **XML Schemas** tab.</span></span>  
  
7. <span data-ttu-id="83870-138">右クリック**スキーマ**、 をクリックして**参照**を選び、 **PO.xsd**先ほど作成したファイル。</span><span class="sxs-lookup"><span data-stu-id="83870-138">Right-click **Schemas**, click **Browse**, and then select the **PO.xsd** file that you created earlier.</span></span>  
  
8. <span data-ttu-id="83870-139">[プロパティ] ウィンドウでの値を変更、**ドキュメントの種類**プロパティから**PO**に**RuleTest.PO**します。</span><span class="sxs-lookup"><span data-stu-id="83870-139">In the properties window, change the value of the **Document Type** property from **PO** to **RuleTest.PO**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="83870-140">という名前の BizTalk プロジェクトを作成して**RuleTest**後半、[チュートリアル。オーケストレーションからポリシーを呼び出す](../core/walkthrough-invoking-the-policy-from-an-orchestration.md)チュートリアル。</span><span class="sxs-lookup"><span data-stu-id="83870-140">You will be creating a BizTalk project named **RuleTest** later in the [Walkthrough: Invoking the Policy from an Orchestration](../core/walkthrough-invoking-the-policy-from-an-orchestration.md) walkthrough.</span></span> <span data-ttu-id="83870-141">チュートリアルを追加しますが、 **PO.xsd**をプロジェクトにファイルを呼び出すオーケストレーションを作成、 **ProcessPurchaseOrder**ポリシー、およびポリシーをテストします。</span><span class="sxs-lookup"><span data-stu-id="83870-141">In that walkthrough, you will add the **PO.xsd** file to the project, create an orchestration that invokes the **ProcessPurchaseOrder** policy, and then test the policy.</span></span> <span data-ttu-id="83870-142">オーケストレーションからポリシーをテストするには、変更することを確認する必要があります、**ドキュメントの種類**プロパティを**\<プロジェクト名\>.\<SchemaName\>**、これは**RuleTest.PO**ここでします。</span><span class="sxs-lookup"><span data-stu-id="83870-142">To test the policy from the orchestration, you need to make sure that you change the **Document Type** property to **\<Project Name\>.\<SchemaName\>**, which is **RuleTest.PO** in this case.</span></span>  
  
    <span data-ttu-id="83870-143">![BRE&#45;チュートリアル&#45;ChangeDocType](../core/media/e9a370fd-d9b2-48f0-ad0e-85a5428a9c21.gif "e9a370fd-d9b2-48f0-ad0e-85a5428a9c21")</span><span class="sxs-lookup"><span data-stu-id="83870-143">![BRE&#45;Walkthrough&#45;ChangeDocType](../core/media/e9a370fd-d9b2-48f0-ad0e-85a5428a9c21.gif "e9a370fd-d9b2-48f0-ad0e-85a5428a9c21")</span></span>  
  
9. <span data-ttu-id="83870-144">ファクト エクスプ ローラー ウィンドウで、 **PurchaseOrder**、順に展開**項目**します。</span><span class="sxs-lookup"><span data-stu-id="83870-144">In the Facts Explorer window, expand **PurchaseOrder**, and then expand **Item**.</span></span>  
  
10. <span data-ttu-id="83870-145">右側の場合にペイン (上部)、右クリック**条件**、 をクリックして**述語**、 をクリックし、 **以下**。</span><span class="sxs-lookup"><span data-stu-id="83870-145">In the IF pane (top) on the right, right-click **Conditions**, click **Predicates**, and then click **LessThanEqual**.</span></span>  
  
     <span data-ttu-id="83870-146">![ビジネス ルール作成ツール&#45;以下](../core/media/1e6418a6-5e5b-4f77-8b7e-dd31d0a753e7.gif "1e6418a6-5e5b-4f77-8b7e-dd31d0a753e7")</span><span class="sxs-lookup"><span data-stu-id="83870-146">![Business Rule Composer &#45; Less Than or Equal](../core/media/1e6418a6-5e5b-4f77-8b7e-dd31d0a753e7.gif "1e6418a6-5e5b-4f77-8b7e-dd31d0a753e7")</span></span>  
  
11. <span data-ttu-id="83870-147">ドラッグ、**数量**ノードを ファクト エクスプ ローラー ウィンドウから**引数 1** IF ペインでします。</span><span class="sxs-lookup"><span data-stu-id="83870-147">Drag the **Quantity** node from the Facts Explorer window to **argument1** in the IF pane.</span></span>  
  
     <span data-ttu-id="83870-148">![ビジネス ルール作成ツール&#45;DragQuantity](../core/media/4742eca6-4a8a-401d-8989-cab4e8025fb3.gif "4742eca6-4a8a-401d-8989-cab4e8025fb3")</span><span class="sxs-lookup"><span data-stu-id="83870-148">![Business Rule Composer &#45; DragQuantity](../core/media/4742eca6-4a8a-401d-8989-cab4e8025fb3.gif "4742eca6-4a8a-401d-8989-cab4e8025fb3")</span></span>  
  
     <span data-ttu-id="83870-149">![ビジネス ルール作成ツール&#45;UseQuantity](../core/media/ee4f61b1-0f15-4329-b0b5-9badd21dcd61.gif "ee4f61b1-0f15-4329-b0b5-9badd21dcd61")</span><span class="sxs-lookup"><span data-stu-id="83870-149">![Business Rule Composer&#45;UseQuantity](../core/media/ee4f61b1-0f15-4329-b0b5-9badd21dcd61.gif "ee4f61b1-0f15-4329-b0b5-9badd21dcd61")</span></span>  
  
12. <span data-ttu-id="83870-150">[IF] ペインで、クリックして **[引数 2]**、型`500`、し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="83870-150">In the IF pane, click **argument2**, type `500`, and then press ENTER.</span></span>  
  
13. <span data-ttu-id="83870-151">ドラッグ、**状態**ノードをファクト エクスプ ローラー ウィンドウからビジネス ルール作成ツールの下部にある右側にある THEN ペインにします。</span><span class="sxs-lookup"><span data-stu-id="83870-151">Drag the **Status** node from the Facts Explorer window to the THEN pane at the bottom-right side of Business Rule Composer.</span></span>  
  
     <span data-ttu-id="83870-152">![ビジネス ルール作成ツール&#45;DragStatus](../core/media/3617251a-a192-4aec-9474-81f6290c0832.gif "3617251a-a192-4aec-9474-81f6290c0832")</span><span class="sxs-lookup"><span data-stu-id="83870-152">![Business Rule Composer&#45;DragStatus](../core/media/3617251a-a192-4aec-9474-81f6290c0832.gif "3617251a-a192-4aec-9474-81f6290c0832")</span></span>  
  
14. <span data-ttu-id="83870-153">[THEN] ペインで、次のようにクリックします。 **\<値を入力します\>** し、入力**Approved**。</span><span class="sxs-lookup"><span data-stu-id="83870-153">In the THEN pane, click **\<Enter a value\>** and then type **Approved**.</span></span>  
  
15. <span data-ttu-id="83870-154">ポリシー エクスプ ローラー ウィンドウで右クリック**バージョン 1.0 (未保存)**、 をクリックし、**保存**します。</span><span class="sxs-lookup"><span data-stu-id="83870-154">In the Policy Explorer window, right-click **Version 1.0 (not saved)**, and then click **Save**.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="83870-155">コメント</span><span class="sxs-lookup"><span data-stu-id="83870-155">Comments</span></span>  
  
-   <span data-ttu-id="83870-156">ポリシーは、1 つまたは複数のルールを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="83870-156">A policy can have one or more rules.</span></span> <span data-ttu-id="83870-157">別のルールを追加して**DeniedRule**の[チュートリアル。ポリシーにルールを追加する](../core/walkthrough-adding-a-rule-to-the-policy.md)チュートリアル。</span><span class="sxs-lookup"><span data-stu-id="83870-157">You will be adding another rule, **DeniedRule**, in the [Walkthrough: Adding a Rule to the Policy](../core/walkthrough-adding-a-rule-to-the-policy.md) walkthrough.</span></span>  
  
-   <span data-ttu-id="83870-158">ルールを追加、条件を変更してポリシーが保存された状態のときにアクションを変更するポリシーを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="83870-158">You can modify the policy to add more rules, change conditions, and change actions when the policy is in the Saved state.</span></span>  
  
-   <span data-ttu-id="83870-159">指定してルールの実行を優先することができます、**優先度**ビジネス ルール作成ツールでルールのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="83870-159">You can prioritize execution of rules by specifying the **Priority** property on rules in Business Rule Composer.</span></span> <span data-ttu-id="83870-160">たとえばをクリックする、 **ApprovedRule**ポリシー エクスプ ローラー ウィンドウでノードを確認できます、**優先度**プロパティ ウィンドウでプロパティ。</span><span class="sxs-lookup"><span data-stu-id="83870-160">For example, if you click the **ApprovedRule** node in the Policy Explorer window, you can see the **Priority** property in the Properties window.</span></span> <span data-ttu-id="83870-161">数値が大きいほど、ルールの優先順位を高くなります。</span><span class="sxs-lookup"><span data-stu-id="83870-161">The larger the number, the higher the rule priority.</span></span>  
  
-   <span data-ttu-id="83870-162">ポリシーのデータ ソースとして XML スキーマ、データベース、または .NET アセンブリを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="83870-162">You can use an XML schema, a database, or a .NET assembly as a data source for the policy.</span></span> <span data-ttu-id="83870-163">このチュートリアルでは、データ ソースとして XML スキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="83870-163">In this walkthrough, you used an XML schema as a data source.</span></span> <span data-ttu-id="83870-164">スキーマの XML ドキュメント インスタンスは、ポリシーを実行するルール エンジンのファクトとして送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83870-164">You should submit an XML document instance of the schema as a fact to the rule engine to execute the policy.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="83870-165">次の手順</span><span class="sxs-lookup"><span data-stu-id="83870-165">Next Steps</span></span>  
 <span data-ttu-id="83870-166">これで、このチュートリアルを完了すると、実行、[チュートリアル。ポリシーのテスト](../core/walkthrough-testing-the-policy.md)をテストするための手順を説明するチュートリアル、 **ProcessPurchaseOrder**このチュートリアルで作成したポリシーです。</span><span class="sxs-lookup"><span data-stu-id="83870-166">Now that you have completed this walkthrough, perform the [Walkthrough: Testing the Policy](../core/walkthrough-testing-the-policy.md) walkthrough, which gives you step-by-step instructions for testing the **ProcessPurchaseOrder** policy you created in this walkthrough.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83870-167">参照</span><span class="sxs-lookup"><span data-stu-id="83870-167">See Also</span></span>  
 [<span data-ttu-id="83870-168">ビジネス ルールについて</span><span class="sxs-lookup"><span data-stu-id="83870-168">About Business Rules</span></span>](../core/about-business-rules.md)