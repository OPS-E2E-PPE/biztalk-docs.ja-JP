---
title: "チュートリアル: ポリシーを展開する |Microsoft ドキュメント"
ms.custom: 
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 205760e2-9cd4-496f-93cd-0f93bc5d3231
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d235fa0f6882ecd9e180aabd26999b1d7f73390
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="walkthrough-deploying-the-policy"></a><span data-ttu-id="ef523-102">チュートリアル: ポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="ef523-102">Walkthrough: Deploying the Policy</span></span>
<span data-ttu-id="ef523-103">このチュートリアルでを展開する手順、 **ProcessPurchaseOrder**次の 3 つの方法でポリシー。</span><span class="sxs-lookup"><span data-stu-id="ef523-103">This walkthrough provides step-by-step instructions for deploying the **ProcessPurchaseOrder** policy in the following three ways:</span></span>  
  
-   <span data-ttu-id="ef523-104">エクスポートして、ビジネス ルール エンジン展開ウィザードを使用して、ポリシーをインポートします。</span><span class="sxs-lookup"><span data-stu-id="ef523-104">Exporting and importing the policy by using the Business Rules Engine Deployment Wizard.</span></span>  
  
-   <span data-ttu-id="ef523-105">BizTalk Server 管理コンソールを使用して、XML ファイルにポリシーをエクスポートし、XML ファイルからポリシーをインポートする。</span><span class="sxs-lookup"><span data-stu-id="ef523-105">Exporting the policy to an XML file and importing the policy from an XML file by using the BizTalk Server Administration console.</span></span>  
  
-   <span data-ttu-id="ef523-106">BizTalk Server 管理コンソールを使用して、ポリシーを MSI ファイルの一部としてエクスポートし、MSI ファイルをインポートする。</span><span class="sxs-lookup"><span data-stu-id="ef523-106">Exporting the policy as part of an MSI file and importing the MSI file by using BizTalk Server Administration console.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ef523-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="ef523-107">Prerequisites</span></span>  
 <span data-ttu-id="ef523-108">完了する必要があります、[チュートリアル: ポリシーの実行を追跡](../core/walkthrough-tracking-policy-execution.md)このチュートリアルを実行する前にチュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="ef523-108">You must complete the [Walkthrough: Tracking Policy Execution](../core/walkthrough-tracking-policy-execution.md) walkthrough before performing this walkthrough.</span></span>  
  
## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="ef523-109">このチュートリアルの概要</span><span class="sxs-lookup"><span data-stu-id="ef523-109">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="ef523-110">このトピックは次の 3 つのチュートリアルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="ef523-110">This topic  contains the following three walkthroughs:</span></span>  
  
1.  <span data-ttu-id="ef523-111">最初のチュートリアルには展開手順が含まれています、 **ProcessPurchaseOrder**ビジネス ルール エンジン展開ウィザードを使用してポリシー。</span><span class="sxs-lookup"><span data-stu-id="ef523-111">The first walkthrough contains procedures for deploying the **ProcessPurchaseOrder** policy by using the Business Rules Engine Deployment Wizard.</span></span> <span data-ttu-id="ef523-112">次の表に、このチュートリアルの手順を示します。</span><span class="sxs-lookup"><span data-stu-id="ef523-112">The following table describes the procedures in this walkthrough.</span></span>  
  
    |<span data-ttu-id="ef523-113">手順のタイトル</span><span class="sxs-lookup"><span data-stu-id="ef523-113">Procedure title</span></span>|<span data-ttu-id="ef523-114">手順の説明</span><span class="sxs-lookup"><span data-stu-id="ef523-114">Procedure description</span></span>|  
    |---------------------|---------------------------|  
    |<span data-ttu-id="ef523-115">ビジネス ルール エンジン展開ウィザードを使用して POVocabulary 1.0 および 1.1 をエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="ef523-115">To export POVocabulary 1.0 and 1.1 by using the Business Rules Engine Deployment Wizard</span></span>|<span data-ttu-id="ef523-116">バージョン 1.0 および 1.1 をエクスポートするための手順をわかりやすく説明、 **POVocabulary**ボキャブラリを XML ファイルをビジネス ルール エンジン展開ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="ef523-116">Provides step-by-step instructions for exporting versions 1.0 and 1.1 of the **POVocabulary** vocabulary to XML files by using the Business Rules Engine Deployment Wizard.</span></span>|  
    |<span data-ttu-id="ef523-117">ビジネス ルール エンジン展開ウィザードを使用して ProcessPurchaseOrder 1.3 をエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="ef523-117">To export ProcessPurchaseOrder 1.3 by using the Business Rules Engine Deployment Wizard</span></span>|<span data-ttu-id="ef523-118">バージョン 1.3 をエクスポートするための手順をわかりやすく説明、 **ProcessPurchaseOrder**ポリシーをビジネス ルール エンジン展開ウィザードを使用して、XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="ef523-118">Provides step-by-step instructions for exporting version 1.3 of the **ProcessPurchaseOrder** policy to an XML file by using the Business Rules Engine Deployment Wizard.</span></span>|  
    |<span data-ttu-id="ef523-119">ProcessPurchaseOrder および POVocabulary を削除するには</span><span class="sxs-lookup"><span data-stu-id="ef523-119">To delete ProcessPurchaseOrder and POVocabulary</span></span>|<span data-ttu-id="ef523-120">削除するための手順をわかりやすく説明、 **ProcessPurchaseOrder**ポリシーおよび**POVocabulary**ボキャブラリがテストできるように XML ファイルのインポートを再作成します。</span><span class="sxs-lookup"><span data-stu-id="ef523-120">Provides step-by-step instructions for deleting the **ProcessPurchaseOrder** policy and **POVocabulary** vocabulary so that you can test importing the XML files to re-create them.</span></span>|  
    |<span data-ttu-id="ef523-121">XML からインポートして POVocabulary 1.0 および 1.1 を再作成するには</span><span class="sxs-lookup"><span data-stu-id="ef523-121">To import from XML to re-create POVocabulary 1.0 and 1.1</span></span>|<span data-ttu-id="ef523-122">再作成する最初の手順で作成したボキャブラリ XML ファイルをインポートするための手順をわかりやすく説明、 **POVocabulary**ボキャブラリです。</span><span class="sxs-lookup"><span data-stu-id="ef523-122">Provides step-by-step instructions for importing the vocabulary XML file you created in the first procedure to re-create the **POVocabulary** vocabulary.</span></span>|  
    |<span data-ttu-id="ef523-123">POVocabulary 1.0 および 1.1 が再作成されたことを確認するには</span><span class="sxs-lookup"><span data-stu-id="ef523-123">To verify that POVocabulary 1.0 and 1.1 are re-created</span></span>|<span data-ttu-id="ef523-124">ビジネス ルール作成ツールを使用して、ことを確認するための手順をわかりやすく説明のバージョン 1.0 および 1.1 **POVocabulary**で再作成されます。</span><span class="sxs-lookup"><span data-stu-id="ef523-124">Provides step-by-step instructions for using the Business Rule Composer to verify that versions 1.0 and 1.1 of **POVocabulary** are re-created.</span></span>|  
    |<span data-ttu-id="ef523-125">XML からインポートして ProcessPurchaseOrder 1.3 を再作成するには</span><span class="sxs-lookup"><span data-stu-id="ef523-125">To import from XML to re-create ProcessPurchaseOrder 1.3</span></span>|<span data-ttu-id="ef523-126">バージョン 1.3 を再作成する 2 番目の手順で作成したポリシー XML ファイルをインポートするための手順をわかりやすく説明、 **ProcessPurchaseOrder**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="ef523-126">Provides step-by-step instructions for importing the policy XML file you created in the second procedure to re-create version 1.3 of the **ProcessPurchaseOrder** policy.</span></span>|  
    |<span data-ttu-id="ef523-127">ProcessPurchaseOrder 1.3 が再作成されたことを確認するには</span><span class="sxs-lookup"><span data-stu-id="ef523-127">To verify that ProcessPurchaseOrder 1.3 is re-created</span></span>|<span data-ttu-id="ef523-128">ビジネス ルール作成ツールを使用してそのバージョン 1.3 のことを確認するための手順をわかりやすく説明、 **ProcessPurchaseOrder**ポリシーを再作成します。</span><span class="sxs-lookup"><span data-stu-id="ef523-128">Provides step-by-step instructions for using the Business Rule Composer to verify that version 1.3 of the **ProcessPurchaseOrder** policy is re-created.</span></span>|  
  
2.  <span data-ttu-id="ef523-129">2 番目のチュートリアルには展開手順が含まれています、 **ProcessPurchaseOrder**次の BizTalk Server 管理コンソールからエクスポートしたポリシー XML ファイルを使用してテーブルには、この手順がについて説明しますチュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="ef523-129">The second walkthrough contains procedures for deploying the **ProcessPurchaseOrder** policy by using an XML file exported from the BizTalk Server Administration console The following table describes the procedures in this walkthrough.</span></span>  
  
    |<span data-ttu-id="ef523-130">手順のタイトル</span><span class="sxs-lookup"><span data-stu-id="ef523-130">Procedure title</span></span>|<span data-ttu-id="ef523-131">手順の説明</span><span class="sxs-lookup"><span data-stu-id="ef523-131">Procedure description</span></span>|  
    |---------------------|---------------------------|  
    |<span data-ttu-id="ef523-132">ProcessPurchaseOrder 1.3 ポリシーと POVocabulary ボキャブラリを XML ファイルにエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="ef523-132">To export the ProcessPurchaseOrder 1.3 policy and the POVocabulary vocabulary to an XML file</span></span>|<span data-ttu-id="ef523-133">BizTalk Server 管理コンソールを使用して、エクスポートするための手順をわかりやすく説明、 **ProcessPurchaseOrder**ポリシーおよび**POVocabulary**ボキャブラリを XML ファイルにします。</span><span class="sxs-lookup"><span data-stu-id="ef523-133">Provides step-by-step instructions for using the BizTalk Server Administration console to export the **ProcessPurchaseOrder** policy and the **POVocabulary** vocabulary to an XML file.</span></span>|  
    |<span data-ttu-id="ef523-134">ProcessPurchaseOrder ポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="ef523-134">To delete the ProcessPurchaseOrder policy</span></span>|<span data-ttu-id="ef523-135">削除するための手順をわかりやすく説明、 **ProcessPurchaseOrder**からポリシーを**RuleTestApp**とルール エンジン データベース。</span><span class="sxs-lookup"><span data-stu-id="ef523-135">Provides step-by-step instructions for deleting the **ProcessPurchaseOrder** policy from **RuleTestApp** and the rule engine database.</span></span>|  
    |<span data-ttu-id="ef523-136">XML ファイルをインポートして ProcessPurchaseOrder ポリシーを再作成するには</span><span class="sxs-lookup"><span data-stu-id="ef523-136">To import the XML file to re-create the ProcessPurchaseOrder policy</span></span>|<span data-ttu-id="ef523-137">再作成する最初の手順でエクスポートした XML ファイルをインポートするための手順をわかりやすく説明、 **ProcessPurchaseOrder**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="ef523-137">Provides step-by-step instructions for importing the XML file you exported in the first procedure to re-create the **ProcessPurchaseOrder** policy.</span></span>|  
    |<span data-ttu-id="ef523-138">RuleTestApp アプリケーションに ProcessPurchaseOrder ポリシーを追加するには</span><span class="sxs-lookup"><span data-stu-id="ef523-138">To add the ProcessPurchaseOrder policy to the RuleTestApp application</span></span>|<span data-ttu-id="ef523-139">追加するための手順をわかりやすく説明、 **ProcessPurchaseOrder**ポリシーを**RuleTestApp**アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="ef523-139">Provides step-by-step instructions for adding the **ProcessPurchaseOrder** policy to the **RuleTestApp** application.</span></span>|  
  
3.  <span data-ttu-id="ef523-140">3 番目のチュートリアルには展開手順が含まれています、 **ProcessPurchaseOrder** MSI ファイルを使用してポリシーが BizTalk Server 管理コンソールからエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="ef523-140">The third walkthrough contains procedures for deploying the **ProcessPurchaseOrder** policy by using an MSI file exported from the BizTalk Server Administration console.</span></span> <span data-ttu-id="ef523-141">次の表に、このチュートリアルの手順を示します。</span><span class="sxs-lookup"><span data-stu-id="ef523-141">The following table describes the procedures in this walkthrough.</span></span>  
  
    |<span data-ttu-id="ef523-142">手順のタイトル</span><span class="sxs-lookup"><span data-stu-id="ef523-142">Procedure title</span></span>|<span data-ttu-id="ef523-143">手順に含まれるステップごとの説明</span><span class="sxs-lookup"><span data-stu-id="ef523-143">Procedure has step-by-step instructions for</span></span>|  
    |---------------------|---------------------------------------------------|  
    |<span data-ttu-id="ef523-144">RuleTestApp アプリケーションを MSI ファイルにエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="ef523-144">To export the RuleTestApp application to an MSI file</span></span>|<span data-ttu-id="ef523-145">エクスポートするための手順をわかりやすく説明、 **RuleTestApp**を MSI ファイルを後でアプリケーションを再作成に使用されるアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="ef523-145">Provides step-by-step instructions for exporting the **RuleTestApp** application to an MSI file, which is used later to re-create the application.</span></span>|  
    |<span data-ttu-id="ef523-146">RuleTestApp アプリケーションを削除するには</span><span class="sxs-lookup"><span data-stu-id="ef523-146">To delete the RuleTestApp application</span></span>|<span data-ttu-id="ef523-147">削除するための手順をわかりやすく説明、 **RuleTestApp**アプリケーションの MSI ファイルを使用してアプリケーションを再作成がテストできるようにします。</span><span class="sxs-lookup"><span data-stu-id="ef523-147">Provides step-by-step instructions for deleting the **RuleTestApp** application so that you can test re-creating the application by using the MSI file.</span></span>|  
    |<span data-ttu-id="ef523-148">ProcessPurchaseOrder ポリシーと POVocabulary ボキャブラリが削除されたことを確認するには</span><span class="sxs-lookup"><span data-stu-id="ef523-148">To verify that the ProcessPurchaseOrder policy and POVocabulary vocabulary are deleted</span></span>|<span data-ttu-id="ef523-149">ビジネス ルール作成ツールを使用していることを確認するための手順をわかりやすく説明、 **ProcessPurchaseOrder**ポリシーと POVocabulary ボキャブラリが削除されます。</span><span class="sxs-lookup"><span data-stu-id="ef523-149">Provides step-by-step instructions for using the Business Rule Composer to verify that the **ProcessPurchaseOrder** policy and POVocabulary vocabulary are deleted.</span></span>|  
    |<span data-ttu-id="ef523-150">MSI ファイルをインポートして RuleTestApp アプリケーションを再作成するには</span><span class="sxs-lookup"><span data-stu-id="ef523-150">To import the MSI file to re-create the RuleTestApp application</span></span>|<span data-ttu-id="ef523-151">再作成する、BizTalk Server 管理コンソールを使用して MSI ファイルをインポートするための手順をわかりやすく説明、 **RuleTestApp**アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="ef523-151">Provides step-by-step instructions for using the BizTalk Server Administration console to import the MSI file to re-create the **RuleTestApp** application.</span></span>|  
    |<span data-ttu-id="ef523-152">RuleTestApp に ProcessPurchaseOrder ポリシーが追加されたことを確認するには</span><span class="sxs-lookup"><span data-stu-id="ef523-152">To verify that the ProcessPurchaseOrder policy is added to RuleTestApp</span></span>|<span data-ttu-id="ef523-153">BizTalk Server 管理コンソールを使用していることを確認するための手順をわかりやすく説明、 **ProcessPurchaseOrder**ポリシーに追加、 **RuleTestApp**アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="ef523-153">Provides step-by-step instructions for using the BizTalk Server Administration console to verify that the **ProcessPurchaseOrder** policy is added to the **RuleTestApp** application.</span></span>|  
    |<span data-ttu-id="ef523-154">ProcessPurchaseOrder ポリシーと POVocabulary ボキャブラリが再作成されたことを確認するには</span><span class="sxs-lookup"><span data-stu-id="ef523-154">To verify that the ProcessPurchaseOrder policy and POVocabulary vocabulary are re-created</span></span>|<span data-ttu-id="ef523-155">ビジネス ルール作成ツールを使用していることを確認するための手順をわかりやすく説明、 **ProcessPurchaseOrder**ポリシーおよび**POVocabulary**ボキャブラリが再作成されます。</span><span class="sxs-lookup"><span data-stu-id="ef523-155">Provides step-by-step instructions for using the Business Rule Composer to verify that the **ProcessPurchaseOrder** policy and **POVocabulary** vocabulary are re-created.</span></span>|  
    |<span data-ttu-id="ef523-156">ソリューションをテストするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ef523-156">To test the solution</span></span>|<span data-ttu-id="ef523-157">ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="ef523-157">Provides step-by-step instructions for testing the solution.</span></span>|  
  
## <a name="procedures-for-deploying-the-processpurchaseorder-policy-by-using-the-business-rules-engine-deployment-wizard"></a><span data-ttu-id="ef523-158">ビジネス ルール エンジン展開ウィザードを使用して ProcessPurchaseOrder ポリシーを展開するための手順</span><span class="sxs-lookup"><span data-stu-id="ef523-158">Procedures for Deploying the ProcessPurchaseOrder Policy by Using the Business Rules Engine Deployment Wizard</span></span>  
  
#### <a name="to-export-povocabulary-10-and-11-by-using-the-business-rules-engine-deployment-wizard"></a><span data-ttu-id="ef523-159">ビジネス ルール エンジン展開ウィザードを使用して POVocabulary 1.0 および 1.1 をエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="ef523-159">To export POVocabulary 1.0 and 1.1 by using the Business Rules Engine Deployment Wizard</span></span>  
  
1.  <span data-ttu-id="ef523-160">**開始**] メニューの [開いている**ビジネス ルール エンジン展開ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-160">On the **Start** menu, open **Business Rules Engine Deployment Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ef523-161">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="ef523-161">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="ef523-162">これを行うには、アプリケーションを右クリックし、**管理者として実行**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-162">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="ef523-163">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ef523-163">Click **Next**.</span></span>  
  
3.  <span data-ttu-id="ef523-164">**展開タスク**] ページで、[**エクスポート ポリシー/ボキャブラリをファイルにデータベースから**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-164">On the **Deployment Task** page, select **Export Policy/Vocabulary to file from database**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="ef523-165">**ポリシー ストア**] ページで [**次**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-165">On the **Policy Store** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="ef523-166">**ポリシー/ボキャブラリのエクスポート**] ページで [**ボキャブラリ**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-166">On the **Export Policy/Vocabulary** page, click **Vocabulary**.</span></span>  
  
6.  <span data-ttu-id="ef523-167">選択**POVocabulary.1.0**のドロップダウン リストから**ポリシー/ボキャブラリ**を入力するか、XML 出力ファイル名を指定する参照**C:\BRE-walkthroughs\POVocabulary10.xml**、クリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-167">Select **POVocabulary.1.0** from the drop-down list for **Policy/Vocabulary**, type or browse to specify the XML output file name as **C:\BRE-walkthroughs\POVocabulary10.xml**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="ef523-168">**準備** ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-168">On the **Ready** page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="ef523-169">**ポリシー/ボキャブラリのエクスポート**] ページで [ **[次へ] です。**</span><span class="sxs-lookup"><span data-stu-id="ef523-169">On the **Exporting Policy/Vocabulary** page, click **Next.**</span></span>  
  
9. <span data-ttu-id="ef523-170">選択**このウィザードを再度実行**、順にクリック**完了**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-170">Select **Run this wizard again**, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="ef523-171">選択したので、**このウィザードを再度実行**ウィザードの最初の画面が再度表示されます。</span><span class="sxs-lookup"><span data-stu-id="ef523-171">Because you selected **Run this wizard again**, the first screen of the wizard appears again.</span></span>  
  
10. <span data-ttu-id="ef523-172">手順 2. ~ 6. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="ef523-172">Repeat steps 2-6.</span></span>  
  
11. <span data-ttu-id="ef523-173">選択**POVocabulary.1.1**のドロップダウン リストから**ポリシー/ボキャブラリ**を入力するか、XML 出力ファイル名を指定する参照**C:\BRE-walkthroughs\POVocabulary11.xml**、クリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-173">Select **POVocabulary.1.1** from the drop-down list for **Policy/Vocabulary**, type or browse to specify the XML output file name as **C:\BRE-walkthroughs\POVocabulary11.xml**, and then click **Next**.</span></span>  
  
12. <span data-ttu-id="ef523-174">手順 8. ～ 9. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="ef523-174">Repeat steps 8 and 9.</span></span>  
  
13. <span data-ttu-id="ef523-175">**[完了]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ef523-175">Click **Finish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ef523-176">バージョン 1.0 および 1.1 の両方をエクスポートする必要が**POVocabulary**ため**ProcessPurchaseOrder** 1.3 の両方のバージョンによって異なります**POVocabulary**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-176">You need to export both version 1.0 and version 1.1 of **POVocabulary** because **ProcessPurchaseOrder** 1.3 depends on both versions of **POVocabulary**.</span></span> <span data-ttu-id="ef523-177">**許可される項目の最大数**バージョン 1.1 のボキャブラリから定義を使用します。</span><span class="sxs-lookup"><span data-stu-id="ef523-177">The **Maximum number of items allowed** definition is used from version 1.1 of the vocabulary.</span></span> <span data-ttu-id="ef523-178">**要求された数量**と**要求の状態**定義はバージョン 1.0 から使用されます。</span><span class="sxs-lookup"><span data-stu-id="ef523-178">The **Requested Quantity** and **Request Status** definitions are used from version 1.0.</span></span>  
  
#### <a name="to-export-processpurchaseorder-13-by-using-the-business-rule-engine-deployment-wizard"></a><span data-ttu-id="ef523-179">ビジネス ルール エンジン展開ウィザードを使用して ProcessPurchaseOrder 1.3 をエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="ef523-179">To export ProcessPurchaseOrder 1.3 by using the Business Rule Engine Deployment Wizard</span></span>  
  
1.  <span data-ttu-id="ef523-180">**開始**] メニューの [開いている**ビジネス ルール エンジン展開ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-180">On the **Start** menu, open **Business Rules Engine Deployment Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ef523-181">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="ef523-181">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="ef523-182">これを行うには、アプリケーションを右クリックし、**管理者として実行**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-182">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="ef523-183">**ルール エンジン展開ウィザードへようこそ** ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-183">On the **Welcome to the Rules Engine Deployment Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="ef523-184">選択**エクスポート ポリシー/ボキャブラリをファイルにデータベースから**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-184">Select **Export Policy/Vocabulary to file from database**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="ef523-185">**ポリシー ストア**] ページで [**次**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-185">On the **Policy Store** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="ef523-186">いることを確認、**ポリシー**オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="ef523-186">Verify that the **Policy** option is selected.</span></span>  
  
6.  <span data-ttu-id="ef523-187">選択**ProcessPurchaseOrder.1.3**のドロップダウン リストから**ポリシー/ボキャブラリ**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-187">Select **ProcessPurchaseOrder.1.3** from the drop-down list for **Policy/Vocabulary**.</span></span>  
  
7.  <span data-ttu-id="ef523-188">入力するかを指定する参照**C:\BRE-walkthroughs\ProcessPOPolicy13.xml** XML 出力ファイル名として。</span><span class="sxs-lookup"><span data-stu-id="ef523-188">Type or browse to specify **C:\BRE-walkthroughs\ProcessPOPolicy13.xml** as the XML output file name.</span></span>  
  
8.  <span data-ttu-id="ef523-189">をクリックして**[次へ]** 4 回、順にクリック**完了**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-189">Click **Next** thrice, and then click **Finish**.</span></span>  
  
#### <a name="to-delete-processpurchaseorder-and-povocabulary"></a><span data-ttu-id="ef523-190">ProcessPurchaseOrder および POVocabulary を削除するには</span><span class="sxs-lookup"><span data-stu-id="ef523-190">To delete ProcessPurchaseOrder and POVocabulary</span></span>  
  
1.  <span data-ttu-id="ef523-191">**開始**] メニューの [開いている**ビジネス ルール作成ツール**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-191">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="ef523-192">開く、f5 キーを押して、またはをクリックを既にのビジネス ルール作成ツールがあるかどうか**再読み込み**で、**ファイル**メニューを更新します。</span><span class="sxs-lookup"><span data-stu-id="ef523-192">If you have Business Rule Composer already open, press F5 or click **Reload** on the **File** menu to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ef523-193">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="ef523-193">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="ef523-194">これを行うには、アプリケーションを右クリックし、**管理者として実行**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-194">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="ef523-195">ポリシー エクスプ ローラー ウィンドウで、**ポリシー**、展開**ProcessPurchaseOrder**を右クリックして**バージョン 1.0**、クリックして**を削除**.</span><span class="sxs-lookup"><span data-stu-id="ef523-195">In the Policy Explorer window, expand **Policies**, expand **ProcessPurchaseOrder**, right-click **Version 1.0**, and then click **Delete**.</span></span> <span data-ttu-id="ef523-196">場合**削除**は無効になっているを右クリックし**バージョン 1.0**をクリックし、 **Undeploy**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-196">If **Delete** is disabled, right-click **Version 1.0**, and then click **Undeploy**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ef523-197">展開されたポリシー バージョンは削除できません。</span><span class="sxs-lookup"><span data-stu-id="ef523-197">The deployed policy versions cannot be deleted.</span></span> <span data-ttu-id="ef523-198">ポリシー バージョンを削除する前に、ポリシーを展開解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef523-198">You must undeploy a policy before deleting a policy version.</span></span>  
  
3.  <span data-ttu-id="ef523-199">をクリックして**はい**確認のメッセージ ボックスにします。</span><span class="sxs-lookup"><span data-stu-id="ef523-199">Click **Yes** in the confirmation message box.</span></span>  
  
4.  <span data-ttu-id="ef523-200">手順 2 および 3 を削除する**バージョン 1.1**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-200">Repeat steps 2 and 3 to delete **Version 1.1**.</span></span>  
  
5.  <span data-ttu-id="ef523-201">手順 2 および 3 を削除する**バージョン 1.2**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-201">Repeat steps 2 and 3 to delete **Version 1.2**.</span></span>  
  
6.  <span data-ttu-id="ef523-202">右クリック**Version 1.3 - Deployed**、クリックして**Undeploy**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-202">Right-click **Version 1.3 - Deployed**, and then click **Undeploy**.</span></span> <span data-ttu-id="ef523-203">場合、 **Undeploy**オプションが無効になっている、この手順を無視します。</span><span class="sxs-lookup"><span data-stu-id="ef523-203">If the **Undeploy** option is disabled, ignore this step.</span></span>  
  
7.  <span data-ttu-id="ef523-204">ファクト エクスプ ローラー ウィンドウで、**ボキャブラリ**を右クリックして**POVocabulary**、クリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-204">In the Facts Explorer window, expand **Vocabularies**, right-click **POVocabulary**, and then click **Delete**.</span></span>  
  
#### <a name="to-import-from-xml-to-re-create-povocabulary-10-and-11"></a><span data-ttu-id="ef523-205">XML からインポートして POVocabulary 1.0 および 1.1 を再作成するには</span><span class="sxs-lookup"><span data-stu-id="ef523-205">To import from XML to re-create POVocabulary 1.0 and 1.1</span></span>  
  
1.  <span data-ttu-id="ef523-206">**開始**] メニューの [開いている**ビジネス ルール エンジン展開ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-206">On the **Start** menu, open **Business Rules Engine Deployment Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ef523-207">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="ef523-207">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="ef523-208">これを行うには、アプリケーションを右クリックし、**管理者として実行**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-208">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="ef523-209">**ルール エンジン展開ウィザードへようこそ**、 をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-209">On the **Welcome to the Rules Engine Deployment Wizard**, click **Next**.</span></span>  
  
3.  <span data-ttu-id="ef523-210">**展開タスク**] ページで、[**インポート ポリシー/ボキャブラリをファイルからデータベースに発行し、**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-210">On the **Deployment Task** page, select **Import and publish Policy/Vocabulary to database from file**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="ef523-211">**ポリシー ストア**] ページで [**次**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-211">On the **Policy Store** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="ef523-212">参照し、選択、 **POVocabulary10.xml**最初の手順で作成したファイルです。</span><span class="sxs-lookup"><span data-stu-id="ef523-212">Browse and select the **POVocabulary10.xml** file you created in the first procedure.</span></span>  
  
6.  <span data-ttu-id="ef523-213">をクリックして**開く**ダブルクリックまたは**POVocabulary10.xml**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-213">Click **Open** or double-click **POVocabulary10.xml**.</span></span>  
  
7.  <span data-ttu-id="ef523-214">をクリックして**次**ビジネス ルール エンジン展開ウィザードでします。</span><span class="sxs-lookup"><span data-stu-id="ef523-214">Click **Next** in the Business Rules Engine Deployment Wizard.</span></span>  
  
8.  <span data-ttu-id="ef523-215">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ef523-215">Click **Next**.</span></span>  
  
9. <span data-ttu-id="ef523-216">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ef523-216">Click **Next**.</span></span>  
  
10. <span data-ttu-id="ef523-217">選択**このウィザードを再度実行**、順にクリック**完了**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-217">Select **Run this wizard again**, and then click **Finish**.</span></span>  
  
11. <span data-ttu-id="ef523-218">手順 2 ~ 9 をインポートする**POVocabulary11.xml**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-218">Repeat steps 2-9 to import **POVocabulary11.xml**.</span></span>  
  
12. <span data-ttu-id="ef523-219">**[完了]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ef523-219">Click **Finish**.</span></span>  
  
#### <a name="to-verify-that-povocabulary-10-and-11-are-re-created"></a><span data-ttu-id="ef523-220">POVocabulary 1.0 および 1.1 が再作成されたことを確認するには</span><span class="sxs-lookup"><span data-stu-id="ef523-220">To verify that POVocabulary 1.0 and 1.1 are re-created</span></span>  
  
1.  <span data-ttu-id="ef523-221">**開始**] メニューの [開いている**ビジネス ルール作成ツール**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-221">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="ef523-222">既に開かれていることがある場合、f5 キーを押すか をクリックして**再読み込み**上、**ファイル**メニューを更新します。</span><span class="sxs-lookup"><span data-stu-id="ef523-222">If you have it already open, press F5 or click **Reload** on the **File** menu to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ef523-223">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="ef523-223">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="ef523-224">これを行うには、アプリケーションを右クリックし、**管理者として実行**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-224">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="ef523-225">[ファクト エクスプ ローラー] ウィンドウ、**ボキャブラリ**タブです。</span><span class="sxs-lookup"><span data-stu-id="ef523-225">In the Facts Explorer window, click the **Vocabularies** tab.</span></span>  
  
3.  <span data-ttu-id="ef523-226">展開**ボキャブラリ**、ください**POVocabulary**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-226">Expand **Vocabularies**, and you should see **POVocabulary**.</span></span>  
  
4.  <span data-ttu-id="ef523-227">展開**POVocabulary**、ください**バージョン 1.0**と**バージョン 1.1**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-227">Expand **POVocabulary**, and you should see **Version 1.0** and **Version 1.1**.</span></span>  
  
#### <a name="to-import-from-xml-to-re-create-processpurchaseorder-13"></a><span data-ttu-id="ef523-228">XML からインポートして ProcessPurchaseOrder 1.3 を再作成するには</span><span class="sxs-lookup"><span data-stu-id="ef523-228">To import from XML to re-create ProcessPurchaseOrder 1.3</span></span>  
  
1.  <span data-ttu-id="ef523-229">**開始**] メニューの [開いている**ビジネス ルール エンジン展開ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-229">On the **Start** menu, open **Business Rules Engine Deployment Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ef523-230">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="ef523-230">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="ef523-231">これを行うには、アプリケーションを右クリックし、**管理者として実行**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-231">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="ef523-232">**ルール エンジン展開ウィザードへようこそ**、 をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-232">On the **Welcome to the Rules Engine Deployment Wizard**, click **Next**.</span></span>  
  
3.  <span data-ttu-id="ef523-233">**展開タスク**] ページで、[**インポート ポリシー/ボキャブラリをファイルからデータベースをファイルからデータベースに発行し、**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-233">On the **Deployment Task** page, select **Import and publish Policy/Vocabulary to database from fileto database from file**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="ef523-234">**ポリシー ストア**] ページで [**次**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-234">On the **Policy Store** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="ef523-235">参照し、選択、 **ProcessPOPolicy13.xml**このチュートリアルで先ほど作成したファイルです。</span><span class="sxs-lookup"><span data-stu-id="ef523-235">Browse and select the **ProcessPOPolicy13.xml** file you created earlier in this walkthrough.</span></span>  
  
6.  <span data-ttu-id="ef523-236">をクリックして**開く**ダブルクリックまたは**ProcessPOPolicy13.xml**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-236">Click **Open** or double-click **ProcessPOPolicy13.xml**.</span></span>  
  
7.  <span data-ttu-id="ef523-237">をクリックして**次**ビジネス ルール エンジン展開ウィザードでします。</span><span class="sxs-lookup"><span data-stu-id="ef523-237">Click **Next** in the Business Rules Engine Deployment Wizard.</span></span>  
  
8.  <span data-ttu-id="ef523-238">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ef523-238">Click **Next**.</span></span>  
  
9. <span data-ttu-id="ef523-239">**[次へ]**をクリックし、 **[完了]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ef523-239">Click **Next**, and then click **Finish**.</span></span>  
  
#### <a name="to-verify-that-processpurchaseorder-13-is-re-created"></a><span data-ttu-id="ef523-240">ProcessPurchaseOrder 1.3 が再作成されたことを確認するには</span><span class="sxs-lookup"><span data-stu-id="ef523-240">To verify that ProcessPurchaseOrder 1.3 is re-created</span></span>  
  
1.  <span data-ttu-id="ef523-241">**開始**] メニューの [開いている**ビジネス ルール作成ツール**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-241">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="ef523-242">既に開かれていることがある場合、f5 キーを押すか をクリックして**再読み込み**上、**ファイル**メニューを更新します。</span><span class="sxs-lookup"><span data-stu-id="ef523-242">If you have it already open, press F5 or click **Reload** on the **File** menu to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ef523-243">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="ef523-243">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="ef523-244">これを行うには、アプリケーションを右クリックし、**管理者として実行**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-244">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="ef523-245">ポリシー エクスプ ローラー ウィンドウで、**ポリシー**ください**ProcessPurchaseOrder**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-245">In the Policy Explorer window, expand **Policies** and you should see **ProcessPurchaseOrder**.</span></span>  
  
3.  <span data-ttu-id="ef523-246">展開**ProcessPurchaseOrder**ください**Version 1.3 - Published**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-246">Expand **ProcessPurchaseOrder** and you should see **Version 1.3 - Published**.</span></span>  
  
## <a name="procedures-for-deploying-the-policy-by-using-an-xml-file-exported-from-the-biztalk-server-administration-console"></a><span data-ttu-id="ef523-247">BizTalk Server 管理コンソールからエクスポートした XML ファイルを使用したポリシーの展開手順</span><span class="sxs-lookup"><span data-stu-id="ef523-247">Procedures for Deploying the Policy by Using an XML file Exported from the BizTalk Server Administration Console</span></span>  
  
#### <a name="to-export-the-processpurchaseorder-13-policy-and-the-povocabulary-vocabulary-to-an-xml-file"></a><span data-ttu-id="ef523-248">ProcessPurchaseOrder 1.3 ポリシーと POVocabulary ボキャブラリを XML ファイルにエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="ef523-248">To export the ProcessPurchaseOrder 1.3 policy and the POVocabulary vocabulary to an XML file</span></span>  
  
1.  <span data-ttu-id="ef523-249">**開始**] メニューの [開いている[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ef523-249">On the **Start** menu, open [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span> <span data-ttu-id="ef523-250">このツールを既に開いている場合は、F5 キーを押して更新します。</span><span class="sxs-lookup"><span data-stu-id="ef523-250">If you have the tool already open, press F5 to refresh it.</span></span>  
  
2.  <span data-ttu-id="ef523-251">展開**コンソール ルート**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**、順に展開**RuleTestApp**.</span><span class="sxs-lookup"><span data-stu-id="ef523-251">Expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, expand **Applications**, and then expand **RuleTestApp**.</span></span>  
  
3.  <span data-ttu-id="ef523-252">をクリックして**ポリシー**し、ProcessPurchaseOrder 1.3 ポリシー一覧に表示されるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="ef523-252">Click **Policies** and make sure that you see the ProcessPurchaseOrder 1.3 policy in the list.</span></span>  
  
4.  <span data-ttu-id="ef523-253">右クリック**ProcessPurchaseOrder**、クリックして**エクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-253">Right-click **ProcessPurchaseOrder**, and then click **Export**.</span></span>  
  
5.  <span data-ttu-id="ef523-254">**ポリシーのエクスポート** ダイアログ ボックスで、確認、 **ProcessPurchaseOrder**ポリシーおよび**POVocabulary**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="ef523-254">In the **Export Policies** dialog box, make sure the **ProcessPurchaseOrder** policy and the **POVocabulary** are selected.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ef523-255">右クリックして、アプリケーションを XML ファイル内のすべてのポリシーをエクスポートすることができます**RuleTest**クリックし、**エクスポート**上、**ポリシー**メニュー。</span><span class="sxs-lookup"><span data-stu-id="ef523-255">You can export all the policies in an application to an XML file by right-clicking **RuleTest** and then clicking **Export** on the **Policies** menu.</span></span> <span data-ttu-id="ef523-256">この方法により、このアプリケーションで使用されるすべてのポリシーとボキャブラリを、単一の XML ファイルにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="ef523-256">This way you can export all the policies and vocabulary used by this application to a single XML file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ef523-257">右クリックして XML ファイルへのすべてのアプリケーション内のすべてのポリシーをエクスポートすることができます、**アプリケーション**ノードをクリックして**エクスポート**上、**ポリシー**メニュー。</span><span class="sxs-lookup"><span data-stu-id="ef523-257">You can export all the policies in all the applications to an XML file by right-clicking the **Applications** node and then clicking **Export** on the **Policies** menu.</span></span> <span data-ttu-id="ef523-258">この方法により、すべてのアプリケーションで使用されるすべてのポリシーとボキャブラリを、単一の XML ファイルにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="ef523-258">This way you can export all the policies and vocabularies used by all the applications into a single XML file.</span></span>  
  
6.  <span data-ttu-id="ef523-259">出力 XML ファイル名を指定 (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**)、をクリックして**Ok**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-259">Specify an output XML file name (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**), and then click **Ok**.</span></span>  
  
#### <a name="to-delete-the-processpurchaseorder-policy"></a><span data-ttu-id="ef523-260">ProcessPurchaseOrder ポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="ef523-260">To delete the ProcessPurchaseOrder policy</span></span>  
  
1.  <span data-ttu-id="ef523-261">BizTalk Server 管理コンソールで、右クリック**ProcessPurchaseOrder**  をクリックし、一覧で**削除**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-261">In BizTalk Server Administration, right-click **ProcessPurchaseOrder** in the list, and then click **Remove**.</span></span>  
  
2.  <span data-ttu-id="ef523-262">をクリックして**はい**で、**を削除するポリシー**メッセージ ボックスです。</span><span class="sxs-lookup"><span data-stu-id="ef523-262">Click **Yes** in the **Remove Policy** message box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ef523-263">展開された状態のポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="ef523-263">If the policy is in the deployed state, it cannot be removed.</span></span> <span data-ttu-id="ef523-264">右クリック**ProcessPurchaseOrder**、順にクリック**Undeploy**ポリシーの展開を解除します。</span><span class="sxs-lookup"><span data-stu-id="ef523-264">Right-click **ProcessPurchaseOrder**, and then click **Undeploy** to undeploy the policy.</span></span> <span data-ttu-id="ef523-265">**削除**ポリシーは展開されていない場合は、メニュー項目が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ef523-265">The **Remove** menu item is available when the policy is undeployed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ef523-266">ボキャブラリ、 **ProcessPurchaseOrder**ここでポリシーが依存**POVocabulary**も削除されます。</span><span class="sxs-lookup"><span data-stu-id="ef523-266">The vocabularies on which the **ProcessPurchaseOrder** policy depends, in this case **POVocabulary**, are also deleted.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ef523-267">アプリケーションからポリシーを削除すると、そのポリシーと依存対象のボキャブラリは、アプリケーションからだけでなくルール エンジン データベースからも削除されます。</span><span class="sxs-lookup"><span data-stu-id="ef523-267">When you remove a policy from an application, the policy and the vocabularies that it depends on are deleted from the rule engine database as well, not just from the application.</span></span>  
  
#### <a name="to-import-the-xml-file-to-re-create-the-processpurchaseorder-policy"></a><span data-ttu-id="ef523-268">XML ファイルをインポートして ProcessPurchaseOrder ポリシーを再作成するには</span><span class="sxs-lookup"><span data-stu-id="ef523-268">To import the XML file to re-create the ProcessPurchaseOrder policy</span></span>  
  
1.  <span data-ttu-id="ef523-269">BizTalk Server 管理コンソールで、展開**コンソール ルート**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、順に展開**BizTalk グループ**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-269">In BizTalk Server Administration, expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then expand **BizTalk Group**.</span></span>  
  
2.  <span data-ttu-id="ef523-270">右クリック**アプリケーション**、 をポイント**インポート**、クリックして**ポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-270">Right-click **Applications**, point to **Import**, and then click **Policies**.</span></span>  
  
3.  <span data-ttu-id="ef523-271">参照、および XML ファイルをダブルクリックして (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**) の最初の手順で作成しました。</span><span class="sxs-lookup"><span data-stu-id="ef523-271">Browse, and double-click the XML file (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**) that you created in the first procedure.</span></span>  
  
4.  <span data-ttu-id="ef523-272">展開**\<すべての成果物\>** **アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-272">Expand **\<All Artifacts\>** under **Applications**.</span></span>  
  
5.  <span data-ttu-id="ef523-273">をクリックして**ポリシー**のバージョン 1.3 を表示する必要があります、 **ProcessPurchaseOrder**が一覧にします。</span><span class="sxs-lookup"><span data-stu-id="ef523-273">Click **Policies**, and you should see version 1.3 of the **ProcessPurchaseOrder** policy in the list.</span></span>  
  
6.  <span data-ttu-id="ef523-274">F5 キーを押してビューを更新します。</span><span class="sxs-lookup"><span data-stu-id="ef523-274">Press F5 to refresh the view.</span></span> <span data-ttu-id="ef523-275">**ProcessPurchaseOrder**にポリシーがあります、**非公開**状態です。</span><span class="sxs-lookup"><span data-stu-id="ef523-275">The **ProcessPurchaseOrder** policy should be in the **Not Published** state.</span></span>  
  
#### <a name="to-add-the-processpurchaseorder-policy-to-the-ruletestapp-application"></a><span data-ttu-id="ef523-276">RuleTestApp アプリケーションに ProcessPurchaseOrder ポリシーを追加するには</span><span class="sxs-lookup"><span data-stu-id="ef523-276">To add the ProcessPurchaseOrder policy to the RuleTestApp application</span></span>  
  
1.  <span data-ttu-id="ef523-277">BizTalk Server 管理コンソールで、右クリック**ProcessPurchaseOrder**ポリシー、およびクリック**発行**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-277">In BizTalk Server Administration, right-click **ProcessPurchaseOrder** policy, and then click **Publish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ef523-278">BizTalk アプリケーションに追加できるのは、公開済みのポリシーだけです。</span><span class="sxs-lookup"><span data-stu-id="ef523-278">Only published policies can be added to a BizTalk application.</span></span>  
  
2.  <span data-ttu-id="ef523-279">**アプリケーション** ノードを展開**RuleTestApp**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-279">In the **Applications** node, expand **RuleTestApp**.</span></span>  
  
3.  <span data-ttu-id="ef523-280">をクリックして**ポリシー**で**RuleTestApp**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-280">Click **Policies** in **RuleTestApp**.</span></span>  
  
4.  <span data-ttu-id="ef523-281">右側の一覧内を右クリックし、**追加**、クリックして**ポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-281">Right-click in the list on the right, point to **Add**, and then click **Policy**.</span></span>  
  
5.  <span data-ttu-id="ef523-282">展開、 **ProcessPurchaseOrder**ノードで、チェック ボックスを選択**Version 1.3 (Published)**、クリックして**[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-282">Expand the **ProcessPurchaseOrder** node, select the check box for **Version 1.3 (Published)**, and then click **OK**.</span></span> <span data-ttu-id="ef523-283">のインスタンスにアクセスするたびに SQL Server ログインを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ef523-283">.</span></span>  
  
6.  <span data-ttu-id="ef523-284">右クリック**ProcessPurchaseOrder**、クリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-284">Right-click **ProcessPurchaseOrder**, and then click **Deploy**.</span></span> <span data-ttu-id="ef523-285">表示されない場合**ProcessPurchaseOrder**一覧で、f5 キーを押して表示を更新します。</span><span class="sxs-lookup"><span data-stu-id="ef523-285">If you do not see **ProcessPurchaseOrder** in the list, press F5 to refresh the view.</span></span>  
  
7.  <span data-ttu-id="ef523-286">をクリックして**はい**確認のメッセージ ボックスにします。</span><span class="sxs-lookup"><span data-stu-id="ef523-286">Click **Yes** in the confirmation message box.</span></span>  
  
## <a name="procedures-for-deploying-the-policy-by-using-an-msi-file"></a><span data-ttu-id="ef523-287">MSI ファイルを使用したポリシーの展開手順</span><span class="sxs-lookup"><span data-stu-id="ef523-287">Procedures for Deploying the Policy by Using an MSI File</span></span>  
  
#### <a name="to-export-the-ruletestapp-application-to-an-msi-file"></a><span data-ttu-id="ef523-288">RuleTestApp アプリケーションを MSI ファイルにエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="ef523-288">To export the RuleTestApp application to an MSI file</span></span>  
  
1.  <span data-ttu-id="ef523-289">**開始**] メニューの [開いている**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-289">On the **Start** menu, open **BizTalk Server Administration**.</span></span> <span data-ttu-id="ef523-290">このツールを既に開いている場合は、F5 キーを押して更新します。</span><span class="sxs-lookup"><span data-stu-id="ef523-290">If you have the tool already open, press F5 to refresh it.</span></span>  
  
2.  <span data-ttu-id="ef523-291">展開**コンソール ルート**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、順に展開**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-291">Expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="ef523-292">右クリック**RuleTestApp**、 をポイント**エクスポート**、クリックして**MSI ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-292">Right-click **RuleTestApp**, point to **Export**, and then click **MSI file**.</span></span>  
  
4.  <span data-ttu-id="ef523-293">**MSI ファイルのエクスポート ウィザードへようこそ** ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-293">On the **Welcome to the Export MSI File Wizard** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="ef523-294">**リソースの選択** ページで、すべての既定オプションを確認してをクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-294">On the **Select Resources** page, review all the default options, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="ef523-295">**IIS ホストの指定**] ページで [**次**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-295">On the **Specify IIS Hosts** page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="ef523-296">**の依存関係** ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-296">On the **Dependencies** page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="ef523-297">**先**として msi ファイルの名前とディレクトリを指定 ページで、 **C:\BRE-Walkthroughs\RuleTestApp.msi**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-297">On the **Destination** page, specify the directory and name for the MSI as **C:\BRE-Walkthroughs\RuleTestApp.msi**.</span></span>  
  
9. <span data-ttu-id="ef523-298">**[エクスポート]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ef523-298">Click **Export**.</span></span>  
  
10. <span data-ttu-id="ef523-299">**概要**] ページで [**完了**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-299">On the **Summary** page, click **Finish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ef523-300">RuleTestApp アプリケーションをエクスポートすると、アプリケーションで使用されるポリシーとボキャブラリも MSI ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="ef523-300">When you export the RuleTestApp application, the policies and vocabularies used by the application are also exported in the MSI file.</span></span> <span data-ttu-id="ef523-301">後で MSI ファイルをインポートすると、ボキャブラリ、ポリシー、およびアプリケーションが、すべて再作成されます。</span><span class="sxs-lookup"><span data-stu-id="ef523-301">Later, when you import the MSI file, the vocabulary, policy, and application are all re-created.</span></span>  
  
#### <a name="to-delete-the-ruletestapp-application"></a><span data-ttu-id="ef523-302">RuleTestApp アプリケーションを削除するには</span><span class="sxs-lookup"><span data-stu-id="ef523-302">To delete the RuleTestApp application</span></span>  
  
1.  <span data-ttu-id="ef523-303">BizTalk Server 管理コンソールで、右クリック**RuleTestApp**、かどうか確認し、**削除**メニューを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="ef523-303">In BizTalk Server Administration, right-click **RuleTestApp**, and check if the **Delete** menu is enabled or disabled.</span></span>  
  
2.  <span data-ttu-id="ef523-304">場合**削除**は無効になっているを右クリックし**[ruletestapp]**、] をクリックして**停止**[**完全停止 - インスタンスの終了**をクリックして**停止**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-304">If **Delete** is disabled, right-click **RuleTestApp**, click **Stop**, select **Full Stop - Terminate Instance**, and then click **Stop**.</span></span>  
  
3.  <span data-ttu-id="ef523-305">右クリック**RuleTestApp**、クリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-305">Right-click **RuleTestApp**, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="ef523-306">をクリックして**はい**削除を確認します。</span><span class="sxs-lookup"><span data-stu-id="ef523-306">Click **Yes** to confirm deletion.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ef523-307">アプリケーションを削除すると、アプリケーション内のすべてのポリシーとそれらが依存するボキャブラリも、ルール エンジン データベースから削除されます。</span><span class="sxs-lookup"><span data-stu-id="ef523-307">When you delete an application, all the policies in the application and dependent vocabularies are deleted from the rule engine database as well.</span></span>  
  
#### <a name="to-verify-that-the-processpurchaseorder-policy-and-povocabulary-vocabulary-are-deleted"></a><span data-ttu-id="ef523-308">ProcessPurchaseOrder ポリシーと POVocabulary ボキャブラリが削除されたことを確認するには</span><span class="sxs-lookup"><span data-stu-id="ef523-308">To verify that the ProcessPurchaseOrder policy and POVocabulary vocabulary are deleted</span></span>  
  
1.  <span data-ttu-id="ef523-309">**開始**] メニューの [開いている**ビジネス ルール作成ツール**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-309">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="ef523-310">ある場合は既にを開き、f5 キーを押して更新のビジネス ルール作成ツール。</span><span class="sxs-lookup"><span data-stu-id="ef523-310">If you have Business Rule Composer already open, press F5 to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ef523-311">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="ef523-311">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="ef523-312">これを行うには、アプリケーションを右クリックし、**管理者として実行**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-312">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="ef523-313">ポリシー エクスプ ローラー ウィンドウで、**ポリシー**、ProcessPurchaseOrder ポリシーが存在しないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ef523-313">In the Policy Explorer window, expand **Policies**, and make sure that the ProcessPurchaseOrder policy does not exist.</span></span>  
  
3.  <span data-ttu-id="ef523-314">ファクト エクスプ ローラー ウィンドウで、**ボキャブラリ**POVocabulary が存在しないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ef523-314">In the Facts Explorer window, expand **Vocabularies**, and make sure that POVocabulary does not exist.</span></span>  
  
#### <a name="to-import-the-msi-file-to-re-create-the-ruletestapp-application"></a><span data-ttu-id="ef523-315">MSI ファイルをインポートして RuleTestApp アプリケーションを再作成するには</span><span class="sxs-lookup"><span data-stu-id="ef523-315">To import the MSI file to re-create the RuleTestApp application</span></span>  
  
1.  <span data-ttu-id="ef523-316">**開始**] メニューの [開いている**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-316">On the **Start** menu, open **BizTalk Server Administration**.</span></span> <span data-ttu-id="ef523-317">BizTalk Server 管理コンソールを既に開いている場合は、F5 キーを押して更新します。</span><span class="sxs-lookup"><span data-stu-id="ef523-317">If you have the BizTalk Server Administration console already open, press F5 to refresh it.</span></span>  
  
2.  <span data-ttu-id="ef523-318">展開**コンソール ルート**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、順に展開**BizTalk グループ**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-318">Expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then expand **BizTalk Group**.</span></span>  
  
3.  <span data-ttu-id="ef523-319">右クリック**アプリケーション**、 をポイント**インポート**、クリックして**MSI ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-319">Right-click **Applications**, point to **Import**, and then click **MSI file**.</span></span>  
  
4.  <span data-ttu-id="ef523-320">**のインポート ウィザードへようこそ**ページで、参照の前にエクスポートした MSI ファイル (RuleTestApp.msi) を選択し、**インポートする MSI ファイル**設定します。</span><span class="sxs-lookup"><span data-stu-id="ef523-320">On the **Welcome to the Import Wizard** page, browse and select the MSI file (RuleTestApp.msi) you exported earlier for the **MSI file to import** setting.</span></span>  
  
5.  <span data-ttu-id="ef523-321">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ef523-321">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="ef523-322">**アプリケーション設定** ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-322">On the **Application Settings** page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="ef523-323">**アプリケーションのターゲット環境設定** ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-323">On the **Application Target Environment Settings** page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="ef523-324">**インポートの概要**] ページで [**インポート**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-324">On the **Import Summary** page, click **Import**.</span></span>  
  
9. <span data-ttu-id="ef523-325">**インポートに成功しました**] ページで [**完了**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-325">On the **Import Succeeded** page, click **Finish**.</span></span> <span data-ttu-id="ef523-326">表示する必要があります、 **RuleTestApp**下にアプリケーションが作成**アプリケーション**BizTalk Server 管理コンソールでします。</span><span class="sxs-lookup"><span data-stu-id="ef523-326">You should see that the **RuleTestApp** application is created under **Applications** in the BizTalk Server Administration console.</span></span>  
  
#### <a name="to-verify-that-the-processpurchaseorder-policy-is-added-to-ruletestapp"></a><span data-ttu-id="ef523-327">RuleTestApp に ProcessPurchaseOrder ポリシーが追加されたことを確認するには</span><span class="sxs-lookup"><span data-stu-id="ef523-327">To verify that the ProcessPurchaseOrder policy is added to RuleTestApp</span></span>  
  
1.  <span data-ttu-id="ef523-328">展開**RuleTestApp** BizTalk Server 管理コンソールでします。</span><span class="sxs-lookup"><span data-stu-id="ef523-328">Expand **RuleTestApp** in the BizTalk Server Administration console.</span></span>  
  
2.  <span data-ttu-id="ef523-329">選択**ポリシー**して表示**ProcessPurchaseOrder**右側のペインの一覧にします。</span><span class="sxs-lookup"><span data-stu-id="ef523-329">Select **Policies** and you should see **ProcessPurchaseOrder** in the list in the right pane.</span></span>  
  
#### <a name="to-verify-that-the-processpurchaseorder-policy-and-povocabulary-vocabulary-are-re-created"></a><span data-ttu-id="ef523-330">ProcessPurchaseOrder ポリシーと POVocabulary ボキャブラリが再作成されたことを確認するには</span><span class="sxs-lookup"><span data-stu-id="ef523-330">To verify that the ProcessPurchaseOrder policy and POVocabulary vocabulary are re-created</span></span>  
  
1.  <span data-ttu-id="ef523-331">**開始**] メニューの [開いている**ビジネス ルール作成ツール**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-331">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="ef523-332">既に開いている場合は、F5 キーを押して更新します。</span><span class="sxs-lookup"><span data-stu-id="ef523-332">If you have it already open, press F5 to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ef523-333">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="ef523-333">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="ef523-334">これを行うには、アプリケーションを右クリックし、**管理者として実行**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-334">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="ef523-335">ポリシー エクスプ ローラー ウィンドウで、**ポリシー**、ことを確認および**ProcessPurchaseOrder**が存在します。</span><span class="sxs-lookup"><span data-stu-id="ef523-335">In the Policy Explorer window, expand **Policies**, and make sure that **ProcessPurchaseOrder** exists.</span></span>  
  
3.  <span data-ttu-id="ef523-336">ファクト エクスプ ローラー ウィンドウで、**ボキャブラリ**、ことを確認および**POVocabulary**が存在します。</span><span class="sxs-lookup"><span data-stu-id="ef523-336">In the Facts Explorer window, expand **Vocabularies**, and make sure that **POVocabulary** exists.</span></span>  
  
#### <a name="to-test-the-solution"></a><span data-ttu-id="ef523-337">ソリューションをテストするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ef523-337">To test the solution</span></span>  
  
1.  <span data-ttu-id="ef523-338">**開始**] メニューの [開いている**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-338">On the **Start** menu, open **BizTalk Server Administration**.</span></span> <span data-ttu-id="ef523-339">BizTalk Server 管理コンソールを既に開いている場合は、F5 キーを押して更新します。</span><span class="sxs-lookup"><span data-stu-id="ef523-339">If you have the BizTalk Server Administration console already open, press F5 to refresh it.</span></span>  
  
2.  <span data-ttu-id="ef523-340">展開**コンソール ルート**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、順に展開**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-340">Expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="ef523-341">右クリック**RuleTestApp**、クリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-341">Right-click **RuleTestApp**, and then click **Start**.</span></span>  
  
4.  <span data-ttu-id="ef523-342">をクリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-342">Click **Start**.</span></span>  
  
5.  <span data-ttu-id="ef523-343">コピー **SamplePO.xml**で作成した[チュートリアル: ポリシーのテスト](../core/walkthrough-testing-the-policy.md)オーケストレーションの入力ディレクトリにします。</span><span class="sxs-lookup"><span data-stu-id="ef523-343">Copy **SamplePO.xml** that you created in [Walkthrough: Testing the Policy](../core/walkthrough-testing-the-policy.md) to the input directory for the orchestration.</span></span>  
  
6.  <span data-ttu-id="ef523-344">オーケストレーションの出力ディレクトリに、出力ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ef523-344">You should see an output file in the output directory for the orchestration.</span></span> <span data-ttu-id="ef523-345">出力 XML ファイルを開くことを確認の値、**ステータス**にフィールドが設定されている**Approved**です。</span><span class="sxs-lookup"><span data-stu-id="ef523-345">Open the output XML file and notice that the value of the **Status** field is set to **Approved**.</span></span>  
  
7.  <span data-ttu-id="ef523-346">手順 3. と 4. を繰り返します**SamplePO2.xml**、ことを確認の値、**ステータス**出力ドキュメント内のフィールドは、入力ドキュメントと同じ (**XYZ**)。</span><span class="sxs-lookup"><span data-stu-id="ef523-346">Repeat steps 3 and 4 with **SamplePO2.xml**, and notice that the value of the **Status** field in the output document is the same as in the input document (**XYZ**).</span></span>  
  
## <a name="comments"></a><span data-ttu-id="ef523-347">コメント</span><span class="sxs-lookup"><span data-stu-id="ef523-347">Comments</span></span>  
  
-   <span data-ttu-id="ef523-348">**非常に重要な**ことに注意して、アプリケーションからポリシーを削除するときをだけを削除しないと、アプリケーションとポリシーの関連付けです削除することも、ポリシーと関連付けられている語彙規則から。エンジンのデータベースです。</span><span class="sxs-lookup"><span data-stu-id="ef523-348">It is **very important** to remember that when you remove a policy from an application, you do not just remove the association between the application and the policy; you also delete the policy and its associated vocabulary from the rule engine database.</span></span>  
  
-   <span data-ttu-id="ef523-349">既定では、アプリケーションを開始すると、ポリシーが自動的に展開されます。</span><span class="sxs-lookup"><span data-stu-id="ef523-349">When you start an application, by default, it deploys the policies automatically.</span></span> <span data-ttu-id="ef523-350">同様に、アプリケーションを停止し、選択する**完全停止 - インスタンスを終了**、関連付けられているポリシーは展開解除自動的にします。</span><span class="sxs-lookup"><span data-stu-id="ef523-350">Similarly, when you stop an application and select **Full Stop - Terminate Instances**, the associated policies are undeployed automatically.</span></span> <span data-ttu-id="ef523-351">選択すると**部分停止 - 実行中のインスタンスを中断**、関連付けられているポリシーが解除されません自動的にします。</span><span class="sxs-lookup"><span data-stu-id="ef523-351">When you select **Partial Stop - Suspend running instances**, the associated policies are not undeployed automatically.</span></span>  
  
-   <span data-ttu-id="ef523-352">ビジネス ルール作成ツールと BizTalk Server 管理コンソールで操作を実行する前には、ビューを更新して、最新の情報を確実に表示してください。</span><span class="sxs-lookup"><span data-stu-id="ef523-352">You should refresh the views in Business Rule Composer and BizTalk Server Administration console to make sure you are looking at the latest information before performing any operation.</span></span>  
  
-   <span data-ttu-id="ef523-353">以前のバージョンが BizTalk アプリケーションに関連付けられているポリシーに、新しいバージョンを作成する場合、ポリシーの新しいバージョンを手動でアプリケーションに追加してください。</span><span class="sxs-lookup"><span data-stu-id="ef523-353">If you create a new version of the policy whose earlier version is associated with a BizTalk application, you should manually add the new version of the policy to the application.</span></span> <span data-ttu-id="ef523-354">ルール エンジン データベースから削除する場合を除いて、ポリシーの古いバージョンは削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="ef523-354">You should not remove the old version of the policy unless you really want to delete it from the rule engine database.</span></span>  
  
-   <span data-ttu-id="ef523-355">インポート前に、複数の BRL (ビジネス ルール言語 XML ファイル) ファイルを単一の BRL ファイルに結合できます。</span><span class="sxs-lookup"><span data-stu-id="ef523-355">You can merge two or more BRL (Business Rule Language XML file) files into a single BRL file before importing.</span></span> <span data-ttu-id="ef523-356">次のコードは 3 つの BRL ファイルを示しています。</span><span class="sxs-lookup"><span data-stu-id="ef523-356">The following code shows three BRL files.</span></span> <span data-ttu-id="ef523-357">1 番目の BRL ファイルに含まれています、 **POVocabulary**ボキャブラリです。</span><span class="sxs-lookup"><span data-stu-id="ef523-357">The first BRL file contains the **POVocabulary** vocabulary.</span></span> <span data-ttu-id="ef523-358">2 番目の BRL ファイルに含まれる、 **ProcessPurchaseOrder**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="ef523-358">The second BRL file contains the **ProcessPurchaseOrder** policy.</span></span> <span data-ttu-id="ef523-359">3 番目の BRL ファイルには、両方が含まれています、 **POVocabulary**ボキャブラリと**ProcessPurchaseOrder**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="ef523-359">The third BRL file contains both the **POVocabulary** vocabulary and the **ProcessPurchaseOrder** policy.</span></span> <span data-ttu-id="ef523-360">3 番目の BRE ファイルを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ef523-360">The third BRE file is created by performing the following steps:</span></span>  
  
    1.  <span data-ttu-id="ef523-361">任意のファイルを使用して新しいファイル エディターを作成し、XML ファイルとして保存します (例: POPolicyVocabulary.xml)。</span><span class="sxs-lookup"><span data-stu-id="ef523-361">Create a new file using any file editor and save it as an XML file (for example: POPolicyVocabulary.xml).</span></span>  
  
    2.  <span data-ttu-id="ef523-362">ボキャブラリが含まれている 1 番目の BRL ファイルから、XML コンテンツ全体をコピーします。</span><span class="sxs-lookup"><span data-stu-id="ef523-362">Copy the entire XML content from the first BRL file containing the vocabulary.</span></span>  
  
    3.  <span data-ttu-id="ef523-363">ルール セット ブロックのコピー (で始まる、 \<ruleset\>タグと末尾には、 \</ruleset\>タグ)、2 番目の BRL ファイルからです。</span><span class="sxs-lookup"><span data-stu-id="ef523-363">Copy the ruleset block (starts with the \<ruleset\> tag and ends with the \</ruleset\> tag) from the second BRL file.</span></span>  
  
    4.  <span data-ttu-id="ef523-364">新しいファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="ef523-364">Save the new file.</span></span> <span data-ttu-id="ef523-365">この単一の XML ファイルを作成するをインポートすることができます、 **POVocabulary**ボキャブラリと**ProcessPurchaseOrder**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="ef523-365">You can import this single XML file to create the **POVocabulary** vocabulary and the **ProcessPurchaseOrder** policy.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ef523-366">結合された BRL ファイル内での、ボキャブラリ ノードとルール セット ノードの順序に意味はありません。</span><span class="sxs-lookup"><span data-stu-id="ef523-366">It does not matter in which order the vocabulary and ruleset nodes are listed in the merged BRL file.</span></span> <span data-ttu-id="ef523-367">ルール セット ノードをボキャブラリ ノードより前に置いてもかまいません。</span><span class="sxs-lookup"><span data-stu-id="ef523-367">You can have the ruleset node ahead of the vocabulary node.</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <brl  
    xmlns="http://schemas.microsoft.com/businessruleslanguage/2002">  
      <vocabulary id="e588676a-ba01-4f37-b59d-91f7e1eb1f1a" name="POVocabulary" uri="" description="">  
           ……   
      </vocabulary>  
    </brl>  
  
    <?xml version="1.0" encoding="utf-8"?>  
    <brl  
    xmlns="http://schemas.microsoft.com/businessruleslanguage/2002">  
      <ruleset name="ProcessPurchaseOrder">  
         ……  
      </ruleset>  
    </brl>  
  
    <brl  
    xmlns="http://schemas.microsoft.com/businessruleslanguage/2002">  
      <vocabulary id="e588676a-ba01-4f37-b59d-91f7e1eb1f1a" name="POVocabulary" uri="" description="">  
           ……   
      </vocabulary>  
      <ruleset name="ProcessPurchaseOrder">  
         ……  
      </ruleset>  
    </brl>  
    ```