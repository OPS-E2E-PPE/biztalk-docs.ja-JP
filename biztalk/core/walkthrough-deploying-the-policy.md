---
title: 'チュートリアル: ポリシーの展開 |Microsoft Docs'
ms.custom: ''
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 205760e2-9cd4-496f-93cd-0f93bc5d3231
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b35b7d9c3b2b7780ef87b0dedae52f58c20dc835
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996299"
---
# <a name="walkthrough-deploying-the-policy"></a><span data-ttu-id="c70ea-102">チュートリアル: ポリシーの展開</span><span class="sxs-lookup"><span data-stu-id="c70ea-102">Walkthrough: Deploying the Policy</span></span>
<span data-ttu-id="c70ea-103">このチュートリアルを展開するための手順について説明します、 **ProcessPurchaseOrder**次の 3 つの方法でポリシー。</span><span class="sxs-lookup"><span data-stu-id="c70ea-103">This walkthrough provides step-by-step instructions for deploying the **ProcessPurchaseOrder** policy in the following three ways:</span></span>  
  
-   <span data-ttu-id="c70ea-104">エクスポートして、ビジネス ルール エンジン展開ウィザードを使用して、ポリシーをインポートします。</span><span class="sxs-lookup"><span data-stu-id="c70ea-104">Exporting and importing the policy by using the Business Rules Engine Deployment Wizard.</span></span>  
  
-   <span data-ttu-id="c70ea-105">BizTalk Server 管理コンソールを使用して、XML ファイルにポリシーをエクスポートし、XML ファイルからポリシーをインポートする。</span><span class="sxs-lookup"><span data-stu-id="c70ea-105">Exporting the policy to an XML file and importing the policy from an XML file by using the BizTalk Server Administration console.</span></span>  
  
-   <span data-ttu-id="c70ea-106">BizTalk Server 管理コンソールを使用して、ポリシーを MSI ファイルの一部としてエクスポートし、MSI ファイルをインポートする。</span><span class="sxs-lookup"><span data-stu-id="c70ea-106">Exporting the policy as part of an MSI file and importing the MSI file by using BizTalk Server Administration console.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c70ea-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="c70ea-107">Prerequisites</span></span>  
 <span data-ttu-id="c70ea-108">完了する必要があります、[チュートリアル: ポリシーの実行を追跡](../core/walkthrough-tracking-policy-execution.md)このチュートリアルを実行する前にチュートリアル。</span><span class="sxs-lookup"><span data-stu-id="c70ea-108">You must complete the [Walkthrough: Tracking Policy Execution](../core/walkthrough-tracking-policy-execution.md) walkthrough before performing this walkthrough.</span></span>  
  
## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="c70ea-109">このチュートリアルの概要</span><span class="sxs-lookup"><span data-stu-id="c70ea-109">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="c70ea-110">このトピックは次の 3 つのチュートリアルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="c70ea-110">This topic  contains the following three walkthroughs:</span></span>  
  
1.  <span data-ttu-id="c70ea-111">最初のチュートリアルには展開手順が含まれています、 **ProcessPurchaseOrder**ビジネス ルール エンジン展開ウィザードを使用してポリシー。</span><span class="sxs-lookup"><span data-stu-id="c70ea-111">The first walkthrough contains procedures for deploying the **ProcessPurchaseOrder** policy by using the Business Rules Engine Deployment Wizard.</span></span> <span data-ttu-id="c70ea-112">次の表に、このチュートリアルの手順を示します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-112">The following table describes the procedures in this walkthrough.</span></span>  
  
    |<span data-ttu-id="c70ea-113">プロシージャ タイトル</span><span class="sxs-lookup"><span data-stu-id="c70ea-113">Procedure title</span></span>|<span data-ttu-id="c70ea-114">手順の説明</span><span class="sxs-lookup"><span data-stu-id="c70ea-114">Procedure description</span></span>|  
    |---------------------|---------------------------|  
    |<span data-ttu-id="c70ea-115">ビジネス ルール エンジン展開ウィザードを使用して POVocabulary 1.0 および 1.1 をエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="c70ea-115">To export POVocabulary 1.0 and 1.1 by using the Business Rules Engine Deployment Wizard</span></span>|<span data-ttu-id="c70ea-116">バージョン 1.0 および 1.1 をエクスポートするための手順について説明します、 **POVocabulary**ボキャブラリを XML には、ビジネス ルール エンジン展開ウィザードを使用してファイルします。</span><span class="sxs-lookup"><span data-stu-id="c70ea-116">Provides step-by-step instructions for exporting versions 1.0 and 1.1 of the **POVocabulary** vocabulary to XML files by using the Business Rules Engine Deployment Wizard.</span></span>|  
    |<span data-ttu-id="c70ea-117">ビジネス ルール エンジン展開ウィザードを使用して ProcessPurchaseOrder 1.3 をエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="c70ea-117">To export ProcessPurchaseOrder 1.3 by using the Business Rules Engine Deployment Wizard</span></span>|<span data-ttu-id="c70ea-118">バージョン 1.3 をエクスポートするための手順について説明します、 **ProcessPurchaseOrder**ビジネス ルール エンジン展開ウィザードを使用して XML ファイルにポリシー。</span><span class="sxs-lookup"><span data-stu-id="c70ea-118">Provides step-by-step instructions for exporting version 1.3 of the **ProcessPurchaseOrder** policy to an XML file by using the Business Rules Engine Deployment Wizard.</span></span>|  
    |<span data-ttu-id="c70ea-119">ProcessPurchaseOrder および POVocabulary を削除するには</span><span class="sxs-lookup"><span data-stu-id="c70ea-119">To delete ProcessPurchaseOrder and POVocabulary</span></span>|<span data-ttu-id="c70ea-120">削除するための手順について説明します、 **ProcessPurchaseOrder**ポリシーと**POVocabulary**ボキャブラリを再作成するファイル、XML のインポートをテストできるようにします。</span><span class="sxs-lookup"><span data-stu-id="c70ea-120">Provides step-by-step instructions for deleting the **ProcessPurchaseOrder** policy and **POVocabulary** vocabulary so that you can test importing the XML files to re-create them.</span></span>|  
    |<span data-ttu-id="c70ea-121">XML からインポートして POVocabulary 1.0 および 1.1 を再作成するには</span><span class="sxs-lookup"><span data-stu-id="c70ea-121">To import from XML to re-create POVocabulary 1.0 and 1.1</span></span>|<span data-ttu-id="c70ea-122">再作成する最初の手順で作成したボキャブラリ XML ファイルをインポートするための手順を提供します、 **POVocabulary**ボキャブラリです。</span><span class="sxs-lookup"><span data-stu-id="c70ea-122">Provides step-by-step instructions for importing the vocabulary XML file you created in the first procedure to re-create the **POVocabulary** vocabulary.</span></span>|  
    |<span data-ttu-id="c70ea-123">POVocabulary 1.0 および 1.1 が再作成されたことを確認するには</span><span class="sxs-lookup"><span data-stu-id="c70ea-123">To verify that POVocabulary 1.0 and 1.1 are re-created</span></span>|<span data-ttu-id="c70ea-124">ビジネス ルール作成ツールを使用して検証するための手順は、のバージョン 1.0 および 1.1 **POVocabulary**は再作成します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-124">Provides step-by-step instructions for using the Business Rule Composer to verify that versions 1.0 and 1.1 of **POVocabulary** are re-created.</span></span>|  
    |<span data-ttu-id="c70ea-125">XML からインポートして ProcessPurchaseOrder 1.3 を再作成するには</span><span class="sxs-lookup"><span data-stu-id="c70ea-125">To import from XML to re-create ProcessPurchaseOrder 1.3</span></span>|<span data-ttu-id="c70ea-126">バージョン 1.3 を再作成する 2 番目の手順で作成したポリシー XML ファイルをインポートするための手順を提供します、 **ProcessPurchaseOrder**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="c70ea-126">Provides step-by-step instructions for importing the policy XML file you created in the second procedure to re-create version 1.3 of the **ProcessPurchaseOrder** policy.</span></span>|  
    |<span data-ttu-id="c70ea-127">ProcessPurchaseOrder 1.3 が再作成されたことを確認するには</span><span class="sxs-lookup"><span data-stu-id="c70ea-127">To verify that ProcessPurchaseOrder 1.3 is re-created</span></span>|<span data-ttu-id="c70ea-128">ビジネス ルール作成ツールを使用して、バージョン 1.3 を検証するための手順について説明します、 **ProcessPurchaseOrder**ポリシーが再作成されます。</span><span class="sxs-lookup"><span data-stu-id="c70ea-128">Provides step-by-step instructions for using the Business Rule Composer to verify that version 1.3 of the **ProcessPurchaseOrder** policy is re-created.</span></span>|  
  
2.  <span data-ttu-id="c70ea-129">2 番目のチュートリアルには展開手順が含まれています、 **ProcessPurchaseOrder**次の BizTalk Server 管理コンソールからエクスポートされたポリシー XML ファイルを使用してテーブルには、この手順がについて説明しますチュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="c70ea-129">The second walkthrough contains procedures for deploying the **ProcessPurchaseOrder** policy by using an XML file exported from the BizTalk Server Administration console The following table describes the procedures in this walkthrough.</span></span>  
  
    |<span data-ttu-id="c70ea-130">プロシージャ タイトル</span><span class="sxs-lookup"><span data-stu-id="c70ea-130">Procedure title</span></span>|<span data-ttu-id="c70ea-131">手順の説明</span><span class="sxs-lookup"><span data-stu-id="c70ea-131">Procedure description</span></span>|  
    |---------------------|---------------------------|  
    |<span data-ttu-id="c70ea-132">ProcessPurchaseOrder 1.3 ポリシーと POVocabulary ボキャブラリを XML ファイルにエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="c70ea-132">To export the ProcessPurchaseOrder 1.3 policy and the POVocabulary vocabulary to an XML file</span></span>|<span data-ttu-id="c70ea-133">BizTalk Server 管理コンソールを使用してエクスポートする手順について説明します、 **ProcessPurchaseOrder**ポリシーと**POVocabulary**ボキャブラリを XML ファイルにします。</span><span class="sxs-lookup"><span data-stu-id="c70ea-133">Provides step-by-step instructions for using the BizTalk Server Administration console to export the **ProcessPurchaseOrder** policy and the **POVocabulary** vocabulary to an XML file.</span></span>|  
    |<span data-ttu-id="c70ea-134">ProcessPurchaseOrder ポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="c70ea-134">To delete the ProcessPurchaseOrder policy</span></span>|<span data-ttu-id="c70ea-135">削除するための手順について説明します、 **ProcessPurchaseOrder**からポリシー **RuleTestApp**とルール エンジン データベース。</span><span class="sxs-lookup"><span data-stu-id="c70ea-135">Provides step-by-step instructions for deleting the **ProcessPurchaseOrder** policy from **RuleTestApp** and the rule engine database.</span></span>|  
    |<span data-ttu-id="c70ea-136">XML ファイルをインポートして ProcessPurchaseOrder ポリシーを再作成するには</span><span class="sxs-lookup"><span data-stu-id="c70ea-136">To import the XML file to re-create the ProcessPurchaseOrder policy</span></span>|<span data-ttu-id="c70ea-137">再作成する最初の手順でエクスポートした XML ファイルをインポートするための手順を提供します、 **ProcessPurchaseOrder**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="c70ea-137">Provides step-by-step instructions for importing the XML file you exported in the first procedure to re-create the **ProcessPurchaseOrder** policy.</span></span>|  
    |<span data-ttu-id="c70ea-138">RuleTestApp アプリケーションに ProcessPurchaseOrder ポリシーを追加するには</span><span class="sxs-lookup"><span data-stu-id="c70ea-138">To add the ProcessPurchaseOrder policy to the RuleTestApp application</span></span>|<span data-ttu-id="c70ea-139">追加するための手順について説明します、 **ProcessPurchaseOrder**ポリシーを**RuleTestApp**アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="c70ea-139">Provides step-by-step instructions for adding the **ProcessPurchaseOrder** policy to the **RuleTestApp** application.</span></span>|  
  
3.  <span data-ttu-id="c70ea-140">3 番目のチュートリアルには展開手順が含まれています、 **ProcessPurchaseOrder** MSI ファイルを使用してポリシーが BizTalk Server 管理コンソールからエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="c70ea-140">The third walkthrough contains procedures for deploying the **ProcessPurchaseOrder** policy by using an MSI file exported from the BizTalk Server Administration console.</span></span> <span data-ttu-id="c70ea-141">次の表に、このチュートリアルの手順を示します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-141">The following table describes the procedures in this walkthrough.</span></span>  
  
    |<span data-ttu-id="c70ea-142">プロシージャ タイトル</span><span class="sxs-lookup"><span data-stu-id="c70ea-142">Procedure title</span></span>|<span data-ttu-id="c70ea-143">手順に含まれるステップごとの説明</span><span class="sxs-lookup"><span data-stu-id="c70ea-143">Procedure has step-by-step instructions for</span></span>|  
    |---------------------|---------------------------------------------------|  
    |<span data-ttu-id="c70ea-144">RuleTestApp アプリケーションを MSI ファイルにエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="c70ea-144">To export the RuleTestApp application to an MSI file</span></span>|<span data-ttu-id="c70ea-145">エクスポートするための手順について説明します、 **RuleTestApp**を MSI ファイルを後で、アプリケーションを再作成に使用されるアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="c70ea-145">Provides step-by-step instructions for exporting the **RuleTestApp** application to an MSI file, which is used later to re-create the application.</span></span>|  
    |<span data-ttu-id="c70ea-146">RuleTestApp アプリケーションを削除するには</span><span class="sxs-lookup"><span data-stu-id="c70ea-146">To delete the RuleTestApp application</span></span>|<span data-ttu-id="c70ea-147">削除するための手順について説明します、 **RuleTestApp**アプリケーションの MSI ファイルを使用してアプリケーションを再作成をテストできるようにします。</span><span class="sxs-lookup"><span data-stu-id="c70ea-147">Provides step-by-step instructions for deleting the **RuleTestApp** application so that you can test re-creating the application by using the MSI file.</span></span>|  
    |<span data-ttu-id="c70ea-148">ProcessPurchaseOrder ポリシーと POVocabulary ボキャブラリが削除されたことを確認するには</span><span class="sxs-lookup"><span data-stu-id="c70ea-148">To verify that the ProcessPurchaseOrder policy and POVocabulary vocabulary are deleted</span></span>|<span data-ttu-id="c70ea-149">ビジネス ルール作成ツールを使用していることを確認する手順について説明します、 **ProcessPurchaseOrder**ポリシーと POVocabulary ボキャブラリが削除されます。</span><span class="sxs-lookup"><span data-stu-id="c70ea-149">Provides step-by-step instructions for using the Business Rule Composer to verify that the **ProcessPurchaseOrder** policy and POVocabulary vocabulary are deleted.</span></span>|  
    |<span data-ttu-id="c70ea-150">MSI ファイルをインポートして RuleTestApp アプリケーションを再作成するには</span><span class="sxs-lookup"><span data-stu-id="c70ea-150">To import the MSI file to re-create the RuleTestApp application</span></span>|<span data-ttu-id="c70ea-151">再作成する、BizTalk Server 管理コンソールを使用して MSI ファイルをインポートする手順について説明します、 **RuleTestApp**アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="c70ea-151">Provides step-by-step instructions for using the BizTalk Server Administration console to import the MSI file to re-create the **RuleTestApp** application.</span></span>|  
    |<span data-ttu-id="c70ea-152">RuleTestApp に ProcessPurchaseOrder ポリシーが追加されたことを確認するには</span><span class="sxs-lookup"><span data-stu-id="c70ea-152">To verify that the ProcessPurchaseOrder policy is added to RuleTestApp</span></span>|<span data-ttu-id="c70ea-153">BizTalk Server 管理コンソールを使用していることを確認する手順について説明します、 **ProcessPurchaseOrder**ポリシーに追加されます、 **RuleTestApp**アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="c70ea-153">Provides step-by-step instructions for using the BizTalk Server Administration console to verify that the **ProcessPurchaseOrder** policy is added to the **RuleTestApp** application.</span></span>|  
    |<span data-ttu-id="c70ea-154">ProcessPurchaseOrder ポリシーと POVocabulary ボキャブラリが再作成されたことを確認するには</span><span class="sxs-lookup"><span data-stu-id="c70ea-154">To verify that the ProcessPurchaseOrder policy and POVocabulary vocabulary are re-created</span></span>|<span data-ttu-id="c70ea-155">ビジネス ルール作成ツールを使用していることを確認する手順について説明します、 **ProcessPurchaseOrder**ポリシーと**POVocabulary**ボキャブラリが再作成されます。</span><span class="sxs-lookup"><span data-stu-id="c70ea-155">Provides step-by-step instructions for using the Business Rule Composer to verify that the **ProcessPurchaseOrder** policy and **POVocabulary** vocabulary are re-created.</span></span>|  
    |<span data-ttu-id="c70ea-156">ソリューションをテストするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c70ea-156">To test the solution</span></span>|<span data-ttu-id="c70ea-157">ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="c70ea-157">Provides step-by-step instructions for testing the solution.</span></span>|  
  
## <a name="procedures-for-deploying-the-processpurchaseorder-policy-by-using-the-business-rules-engine-deployment-wizard"></a><span data-ttu-id="c70ea-158">ビジネス ルール エンジン展開ウィザードを使用して ProcessPurchaseOrder ポリシーを展開するための手順</span><span class="sxs-lookup"><span data-stu-id="c70ea-158">Procedures for Deploying the ProcessPurchaseOrder Policy by Using the Business Rules Engine Deployment Wizard</span></span>  
  
#### <a name="to-export-povocabulary-10-and-11-by-using-the-business-rules-engine-deployment-wizard"></a><span data-ttu-id="c70ea-159">ビジネス ルール エンジン展開ウィザードを使用して POVocabulary 1.0 および 1.1 をエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="c70ea-159">To export POVocabulary 1.0 and 1.1 by using the Business Rules Engine Deployment Wizard</span></span>  
  
1.  <span data-ttu-id="c70ea-160">**開始**] メニューの [open**ビジネス ルール エンジン展開ウィザード**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-160">On the **Start** menu, open **Business Rules Engine Deployment Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c70ea-161">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="c70ea-161">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="c70ea-162">これを行うには、アプリケーションを右クリックし、**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-162">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="c70ea-163">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c70ea-163">Click **Next**.</span></span>  
  
3.  <span data-ttu-id="c70ea-164">**展開タスク**] ページで、[**エクスポート ポリシー/ボキャブラリをファイルにデータベースから**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-164">On the **Deployment Task** page, select **Export Policy/Vocabulary to file from database**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="c70ea-165">**ポリシー ストア**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-165">On the **Policy Store** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="c70ea-166">**ポリシー/ボキャブラリのエクスポート**] ページで [**ボキャブラリ**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-166">On the **Export Policy/Vocabulary** page, click **Vocabulary**.</span></span>  
  
6.  <span data-ttu-id="c70ea-167">選択**POVocabulary.1.0**のドロップダウン リストから**ポリシー/ボキャブラリ**入力するか、XML 出力ファイル名を指定する参照**C:\BRE-walkthroughs\POVocabulary10.xml**、 をクリックし、**次**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-167">Select **POVocabulary.1.0** from the drop-down list for **Policy/Vocabulary**, type or browse to specify the XML output file name as **C:\BRE-walkthroughs\POVocabulary10.xml**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="c70ea-168">**準備ができて**] ページで [**次**。</span><span class="sxs-lookup"><span data-stu-id="c70ea-168">On the **Ready** page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="c70ea-169">**ポリシー/ボキャブラリのエクスポート**] ページで [ **[次へ]。**</span><span class="sxs-lookup"><span data-stu-id="c70ea-169">On the **Exporting Policy/Vocabulary** page, click **Next.**</span></span>  
  
9. <span data-ttu-id="c70ea-170">選択**このウィザードを再度実行**、 をクリックし、**完了**。</span><span class="sxs-lookup"><span data-stu-id="c70ea-170">Select **Run this wizard again**, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="c70ea-171">選択したので、**このウィザードを再度実行**ウィザードの最初の画面が再度表示されます。</span><span class="sxs-lookup"><span data-stu-id="c70ea-171">Because you selected **Run this wizard again**, the first screen of the wizard appears again.</span></span>  
  
10. <span data-ttu-id="c70ea-172">手順 2. ~ 6. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-172">Repeat steps 2-6.</span></span>  
  
11. <span data-ttu-id="c70ea-173">選択**POVocabulary.1.1**のドロップダウン リストから**ポリシー/ボキャブラリ**入力するか、XML 出力ファイル名を指定する参照**C:\BRE-walkthroughs\POVocabulary11.xml**、 をクリックし、**次**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-173">Select **POVocabulary.1.1** from the drop-down list for **Policy/Vocabulary**, type or browse to specify the XML output file name as **C:\BRE-walkthroughs\POVocabulary11.xml**, and then click **Next**.</span></span>  
  
12. <span data-ttu-id="c70ea-174">手順 8. ～ 9. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-174">Repeat steps 8 and 9.</span></span>  
  
13. <span data-ttu-id="c70ea-175">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c70ea-175">Click **Finish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c70ea-176">バージョン 1.0 と version 1.1 の両方をエクスポートする必要がある**POVocabulary**ため**ProcessPurchaseOrder** 1.3 の両方のバージョンによって異なります**POVocabulary**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-176">You need to export both version 1.0 and version 1.1 of **POVocabulary** because **ProcessPurchaseOrder** 1.3 depends on both versions of **POVocabulary**.</span></span> <span data-ttu-id="c70ea-177">**許可される項目の最大数**バージョン 1.1 のボキャブラリから定義を使用します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-177">The **Maximum number of items allowed** definition is used from version 1.1 of the vocabulary.</span></span> <span data-ttu-id="c70ea-178">**要求された数量**と**要求の状態**バージョン 1.0 からの定義が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c70ea-178">The **Requested Quantity** and **Request Status** definitions are used from version 1.0.</span></span>  
  
#### <a name="to-export-processpurchaseorder-13-by-using-the-business-rule-engine-deployment-wizard"></a><span data-ttu-id="c70ea-179">ビジネス ルール エンジン展開ウィザードを使用して ProcessPurchaseOrder 1.3 をエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="c70ea-179">To export ProcessPurchaseOrder 1.3 by using the Business Rule Engine Deployment Wizard</span></span>  
  
1.  <span data-ttu-id="c70ea-180">**開始**] メニューの [open**ビジネス ルール エンジン展開ウィザード**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-180">On the **Start** menu, open **Business Rules Engine Deployment Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c70ea-181">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="c70ea-181">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="c70ea-182">これを行うには、アプリケーションを右クリックし、**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-182">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="c70ea-183">**、ルール エンジン展開ウィザードへようこそ**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-183">On the **Welcome to the Rules Engine Deployment Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="c70ea-184">選択**エクスポート ポリシー/ボキャブラリをファイルにデータベースから**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-184">Select **Export Policy/Vocabulary to file from database**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="c70ea-185">**ポリシー ストア**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-185">On the **Policy Store** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="c70ea-186">いることを確認、**ポリシー**オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-186">Verify that the **Policy** option is selected.</span></span>  
  
6.  <span data-ttu-id="c70ea-187">選択**ProcessPurchaseOrder.1.3**のドロップダウン リストから**ポリシー/ボキャブラリ**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-187">Select **ProcessPurchaseOrder.1.3** from the drop-down list for **Policy/Vocabulary**.</span></span>  
  
7.  <span data-ttu-id="c70ea-188">入力するかを指定する参照**C:\BRE-walkthroughs\ProcessPOPolicy13.xml**として、XML 出力ファイル名。</span><span class="sxs-lookup"><span data-stu-id="c70ea-188">Type or browse to specify **C:\BRE-walkthroughs\ProcessPOPolicy13.xml** as the XML output file name.</span></span>  
  
8.  <span data-ttu-id="c70ea-189">をクリックして**次**4 回、順にクリックします**完了**。</span><span class="sxs-lookup"><span data-stu-id="c70ea-189">Click **Next** thrice, and then click **Finish**.</span></span>  
  
#### <a name="to-delete-processpurchaseorder-and-povocabulary"></a><span data-ttu-id="c70ea-190">ProcessPurchaseOrder および POVocabulary を削除するには</span><span class="sxs-lookup"><span data-stu-id="c70ea-190">To delete ProcessPurchaseOrder and POVocabulary</span></span>  
  
1.  <span data-ttu-id="c70ea-191">**開始**] メニューの [open**ビジネス ルール作成ツール**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-191">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="c70ea-192">開く、f5 キーを押して、またはをクリックを既にのビジネス ルール作成ツールがあるかどうかは**再読み込み**上、**ファイル**メニューを更新します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-192">If you have Business Rule Composer already open, press F5 or click **Reload** on the **File** menu to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c70ea-193">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="c70ea-193">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="c70ea-194">これを行うには、アプリケーションを右クリックし、**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-194">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="c70ea-195">ポリシー エクスプ ローラー ウィンドウで、**ポリシー**、展開**ProcessPurchaseOrder**を右クリックして**バージョン 1.0**、順にクリックします**削除**.</span><span class="sxs-lookup"><span data-stu-id="c70ea-195">In the Policy Explorer window, expand **Policies**, expand **ProcessPurchaseOrder**, right-click **Version 1.0**, and then click **Delete**.</span></span> <span data-ttu-id="c70ea-196">場合**削除**は右クリックし、無効になっています。**バージョン 1.0**、順にクリックします**Undeploy**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-196">If **Delete** is disabled, right-click **Version 1.0**, and then click **Undeploy**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c70ea-197">展開されたポリシー バージョンは削除できません。</span><span class="sxs-lookup"><span data-stu-id="c70ea-197">The deployed policy versions cannot be deleted.</span></span> <span data-ttu-id="c70ea-198">ポリシー バージョンを削除する前に、ポリシーを展開解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c70ea-198">You must undeploy a policy before deleting a policy version.</span></span>  
  
3.  <span data-ttu-id="c70ea-199">クリックして**はい**確認のメッセージ ボックスにします。</span><span class="sxs-lookup"><span data-stu-id="c70ea-199">Click **Yes** in the confirmation message box.</span></span>  
  
4.  <span data-ttu-id="c70ea-200">手順 2. および 3. 削除を**バージョン 1.1**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-200">Repeat steps 2 and 3 to delete **Version 1.1**.</span></span>  
  
5.  <span data-ttu-id="c70ea-201">手順 2. および 3. 削除を**バージョン 1.2**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-201">Repeat steps 2 and 3 to delete **Version 1.2**.</span></span>  
  
6.  <span data-ttu-id="c70ea-202">右クリック**Version 1.3 - Deployed**、 をクリックし、 **Undeploy**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-202">Right-click **Version 1.3 - Deployed**, and then click **Undeploy**.</span></span> <span data-ttu-id="c70ea-203">場合、 **Undeploy**オプションが無効になっている、この手順を無視します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-203">If the **Undeploy** option is disabled, ignore this step.</span></span>  
  
7.  <span data-ttu-id="c70ea-204">ファクト エクスプ ローラー ウィンドウで、**ボキャブラリ**を右クリックして**POVocabulary**、 をクリックし、**削除**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-204">In the Facts Explorer window, expand **Vocabularies**, right-click **POVocabulary**, and then click **Delete**.</span></span>  
  
#### <a name="to-import-from-xml-to-re-create-povocabulary-10-and-11"></a><span data-ttu-id="c70ea-205">XML からインポートして POVocabulary 1.0 および 1.1 を再作成するには</span><span class="sxs-lookup"><span data-stu-id="c70ea-205">To import from XML to re-create POVocabulary 1.0 and 1.1</span></span>  
  
1.  <span data-ttu-id="c70ea-206">**開始**] メニューの [open**ビジネス ルール エンジン展開ウィザード**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-206">On the **Start** menu, open **Business Rules Engine Deployment Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c70ea-207">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="c70ea-207">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="c70ea-208">これを行うには、アプリケーションを右クリックし、**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-208">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="c70ea-209">**、ルール エンジン展開ウィザードへようこそ**、 をクリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-209">On the **Welcome to the Rules Engine Deployment Wizard**, click **Next**.</span></span>  
  
3.  <span data-ttu-id="c70ea-210">**展開タスク**] ページで、[**インポート ポリシー/ボキャブラリをファイルからデータベースに発行し、**、順にクリックします**次**。</span><span class="sxs-lookup"><span data-stu-id="c70ea-210">On the **Deployment Task** page, select **Import and publish Policy/Vocabulary to database from file**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="c70ea-211">**ポリシー ストア**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-211">On the **Policy Store** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="c70ea-212">参照し、選択、 **POVocabulary10.xml**最初の手順で作成したファイル。</span><span class="sxs-lookup"><span data-stu-id="c70ea-212">Browse and select the **POVocabulary10.xml** file you created in the first procedure.</span></span>  
  
6.  <span data-ttu-id="c70ea-213">をクリックして**オープン**かダブルクリック**POVocabulary10.xml**。</span><span class="sxs-lookup"><span data-stu-id="c70ea-213">Click **Open** or double-click **POVocabulary10.xml**.</span></span>  
  
7.  <span data-ttu-id="c70ea-214">クリックして**次**ビジネス ルール エンジン展開ウィザードでします。</span><span class="sxs-lookup"><span data-stu-id="c70ea-214">Click **Next** in the Business Rules Engine Deployment Wizard.</span></span>  
  
8.  <span data-ttu-id="c70ea-215">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c70ea-215">Click **Next**.</span></span>  
  
9. <span data-ttu-id="c70ea-216">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c70ea-216">Click **Next**.</span></span>  
  
10. <span data-ttu-id="c70ea-217">選択**このウィザードを再度実行**、 をクリックし、**完了**。</span><span class="sxs-lookup"><span data-stu-id="c70ea-217">Select **Run this wizard again**, and then click **Finish**.</span></span>  
  
11. <span data-ttu-id="c70ea-218">手順 2 ~ 9 をインポートする**POVocabulary11.xml**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-218">Repeat steps 2-9 to import **POVocabulary11.xml**.</span></span>  
  
12. <span data-ttu-id="c70ea-219">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c70ea-219">Click **Finish**.</span></span>  
  
#### <a name="to-verify-that-povocabulary-10-and-11-are-re-created"></a><span data-ttu-id="c70ea-220">POVocabulary 1.0 および 1.1 が再作成されたことを確認するには</span><span class="sxs-lookup"><span data-stu-id="c70ea-220">To verify that POVocabulary 1.0 and 1.1 are re-created</span></span>  
  
1.  <span data-ttu-id="c70ea-221">**開始**] メニューの [open**ビジネス ルール作成ツール**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-221">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="c70ea-222">既に開かれていることがある場合、f5 キーを押すか をクリックして**再読み込み**上、**ファイル**メニューを更新します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-222">If you have it already open, press F5 or click **Reload** on the **File** menu to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c70ea-223">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="c70ea-223">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="c70ea-224">これを行うには、アプリケーションを右クリックし、**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-224">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="c70ea-225">[ファクト エクスプ ローラー] ウィンドウ、**ボキャブラリ**タブ。</span><span class="sxs-lookup"><span data-stu-id="c70ea-225">In the Facts Explorer window, click the **Vocabularies** tab.</span></span>  
  
3.  <span data-ttu-id="c70ea-226">展開**ボキャブラリ**、ください**POVocabulary**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-226">Expand **Vocabularies**, and you should see **POVocabulary**.</span></span>  
  
4.  <span data-ttu-id="c70ea-227">展開**POVocabulary**、ください**バージョン 1.0**と**バージョン 1.1**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-227">Expand **POVocabulary**, and you should see **Version 1.0** and **Version 1.1**.</span></span>  
  
#### <a name="to-import-from-xml-to-re-create-processpurchaseorder-13"></a><span data-ttu-id="c70ea-228">XML からインポートして ProcessPurchaseOrder 1.3 を再作成するには</span><span class="sxs-lookup"><span data-stu-id="c70ea-228">To import from XML to re-create ProcessPurchaseOrder 1.3</span></span>  
  
1.  <span data-ttu-id="c70ea-229">**開始**] メニューの [open**ビジネス ルール エンジン展開ウィザード**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-229">On the **Start** menu, open **Business Rules Engine Deployment Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c70ea-230">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="c70ea-230">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="c70ea-231">これを行うには、アプリケーションを右クリックし、**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-231">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="c70ea-232">**、ルール エンジン展開ウィザードへようこそ**、 をクリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-232">On the **Welcome to the Rules Engine Deployment Wizard**, click **Next**.</span></span>  
  
3.  <span data-ttu-id="c70ea-233">**展開タスク**] ページで、[**インポート ポリシー/ボキャブラリをファイルからデータベースをファイルからデータベースに発行し、**、順にクリックします**次**。</span><span class="sxs-lookup"><span data-stu-id="c70ea-233">On the **Deployment Task** page, select **Import and publish Policy/Vocabulary to database from fileto database from file**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="c70ea-234">**ポリシー ストア**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-234">On the **Policy Store** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="c70ea-235">参照し、選択、 **ProcessPOPolicy13.xml**このチュートリアルで先ほど作成したファイル。</span><span class="sxs-lookup"><span data-stu-id="c70ea-235">Browse and select the **ProcessPOPolicy13.xml** file you created earlier in this walkthrough.</span></span>  
  
6.  <span data-ttu-id="c70ea-236">をクリックして**オープン**かダブルクリック**ProcessPOPolicy13.xml**。</span><span class="sxs-lookup"><span data-stu-id="c70ea-236">Click **Open** or double-click **ProcessPOPolicy13.xml**.</span></span>  
  
7.  <span data-ttu-id="c70ea-237">クリックして**次**ビジネス ルール エンジン展開ウィザードでします。</span><span class="sxs-lookup"><span data-stu-id="c70ea-237">Click **Next** in the Business Rules Engine Deployment Wizard.</span></span>  
  
8.  <span data-ttu-id="c70ea-238">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c70ea-238">Click **Next**.</span></span>  
  
9. <span data-ttu-id="c70ea-239">**[次へ]** をクリックし、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c70ea-239">Click **Next**, and then click **Finish**.</span></span>  
  
#### <a name="to-verify-that-processpurchaseorder-13-is-re-created"></a><span data-ttu-id="c70ea-240">ProcessPurchaseOrder 1.3 が再作成されたことを確認するには</span><span class="sxs-lookup"><span data-stu-id="c70ea-240">To verify that ProcessPurchaseOrder 1.3 is re-created</span></span>  
  
1.  <span data-ttu-id="c70ea-241">**開始**] メニューの [open**ビジネス ルール作成ツール**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-241">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="c70ea-242">既に開かれていることがある場合、f5 キーを押すか をクリックして**再読み込み**上、**ファイル**メニューを更新します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-242">If you have it already open, press F5 or click **Reload** on the **File** menu to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c70ea-243">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="c70ea-243">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="c70ea-244">これを行うには、アプリケーションを右クリックし、**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-244">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="c70ea-245">ポリシー エクスプ ローラー ウィンドウで、**ポリシー**ください**ProcessPurchaseOrder**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-245">In the Policy Explorer window, expand **Policies** and you should see **ProcessPurchaseOrder**.</span></span>  
  
3.  <span data-ttu-id="c70ea-246">展開**ProcessPurchaseOrder**ください**Version 1.3 - Published**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-246">Expand **ProcessPurchaseOrder** and you should see **Version 1.3 - Published**.</span></span>  
  
## <a name="procedures-for-deploying-the-policy-by-using-an-xml-file-exported-from-the-biztalk-server-administration-console"></a><span data-ttu-id="c70ea-247">BizTalk Server 管理コンソールからエクスポートした XML ファイルを使用したポリシーの展開手順</span><span class="sxs-lookup"><span data-stu-id="c70ea-247">Procedures for Deploying the Policy by Using an XML file Exported from the BizTalk Server Administration Console</span></span>  
  
#### <a name="to-export-the-processpurchaseorder-13-policy-and-the-povocabulary-vocabulary-to-an-xml-file"></a><span data-ttu-id="c70ea-248">ProcessPurchaseOrder 1.3 ポリシーと POVocabulary ボキャブラリを XML ファイルにエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="c70ea-248">To export the ProcessPurchaseOrder 1.3 policy and the POVocabulary vocabulary to an XML file</span></span>  
  
1. <span data-ttu-id="c70ea-249">**開始**] メニューの [open[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-249">On the **Start** menu, open [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span> <span data-ttu-id="c70ea-250">このツールを既に開いている場合は、F5 キーを押して更新します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-250">If you have the tool already open, press F5 to refresh it.</span></span>  
  
2. <span data-ttu-id="c70ea-251">展開**コンソール ルート**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**、順に展開**RuleTestApp**.</span><span class="sxs-lookup"><span data-stu-id="c70ea-251">Expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, expand **Applications**, and then expand **RuleTestApp**.</span></span>  
  
3. <span data-ttu-id="c70ea-252">クリックして**ポリシー**し、ProcessPurchaseOrder 1.3 ポリシーが一覧表示されるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-252">Click **Policies** and make sure that you see the ProcessPurchaseOrder 1.3 policy in the list.</span></span>  
  
4. <span data-ttu-id="c70ea-253">右クリックして**ProcessPurchaseOrder**、 をクリックし、**エクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-253">Right-click **ProcessPurchaseOrder**, and then click **Export**.</span></span>  
  
5. <span data-ttu-id="c70ea-254">**ポリシーのエクスポート** ダイアログ ボックスで、確認、 **ProcessPurchaseOrder**ポリシーと**POVocabulary**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="c70ea-254">In the **Export Policies** dialog box, make sure the **ProcessPurchaseOrder** policy and the **POVocabulary** are selected.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="c70ea-255">右クリックし、XML ファイルに、アプリケーション内のすべてのポリシーをエクスポートする**RuleTest**  をクリックし、**エクスポート**で、**ポリシー**メニュー。</span><span class="sxs-lookup"><span data-stu-id="c70ea-255">You can export all the policies in an application to an XML file by right-clicking **RuleTest** and then clicking **Export** on the **Policies** menu.</span></span> <span data-ttu-id="c70ea-256">この方法により、このアプリケーションで使用されるすべてのポリシーとボキャブラリを、単一の XML ファイルにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="c70ea-256">This way you can export all the policies and vocabulary used by this application to a single XML file.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="c70ea-257">右クリックし、XML ファイルにすべてのアプリケーション内のすべてのポリシーをエクスポートすることができます、**アプリケーション**ノードをクリックして**エクスポート**上、**ポリシー**メニュー。</span><span class="sxs-lookup"><span data-stu-id="c70ea-257">You can export all the policies in all the applications to an XML file by right-clicking the **Applications** node and then clicking **Export** on the **Policies** menu.</span></span> <span data-ttu-id="c70ea-258">この方法により、すべてのアプリケーションで使用されるすべてのポリシーとボキャブラリを、単一の XML ファイルにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="c70ea-258">This way you can export all the policies and vocabularies used by all the applications into a single XML file.</span></span>  
  
6. <span data-ttu-id="c70ea-259">出力 XML ファイル名を指定 (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**)、をクリックし、 **Ok**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-259">Specify an output XML file name (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**), and then click **Ok**.</span></span>  
  
#### <a name="to-delete-the-processpurchaseorder-policy"></a><span data-ttu-id="c70ea-260">ProcessPurchaseOrder ポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="c70ea-260">To delete the ProcessPurchaseOrder policy</span></span>  
  
1.  <span data-ttu-id="c70ea-261">BizTalk Server 管理コンソールで、右クリック**ProcessPurchaseOrder**  をクリックし、一覧で**削除**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-261">In BizTalk Server Administration, right-click **ProcessPurchaseOrder** in the list, and then click **Remove**.</span></span>  
  
2.  <span data-ttu-id="c70ea-262">をクリックして**はい**で、**削除ポリシー**メッセージ ボックス。</span><span class="sxs-lookup"><span data-stu-id="c70ea-262">Click **Yes** in the **Remove Policy** message box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c70ea-263">展開された状態のポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="c70ea-263">If the policy is in the deployed state, it cannot be removed.</span></span> <span data-ttu-id="c70ea-264">右クリック**ProcessPurchaseOrder**、順にクリックします**Undeploy**ポリシーの展開を解除します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-264">Right-click **ProcessPurchaseOrder**, and then click **Undeploy** to undeploy the policy.</span></span> <span data-ttu-id="c70ea-265">**削除**ポリシーが展開時に、メニュー項目が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c70ea-265">The **Remove** menu item is available when the policy is undeployed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c70ea-266">ボキャブラリ、 **ProcessPurchaseOrder**ここでポリシーが依存**POVocabulary**も削除されます。</span><span class="sxs-lookup"><span data-stu-id="c70ea-266">The vocabularies on which the **ProcessPurchaseOrder** policy depends, in this case **POVocabulary**, are also deleted.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c70ea-267">アプリケーションからポリシーを削除すると、そのポリシーと依存対象のボキャブラリは、アプリケーションからだけでなくルール エンジン データベースからも削除されます。</span><span class="sxs-lookup"><span data-stu-id="c70ea-267">When you remove a policy from an application, the policy and the vocabularies that it depends on are deleted from the rule engine database as well, not just from the application.</span></span>  
  
#### <a name="to-import-the-xml-file-to-re-create-the-processpurchaseorder-policy"></a><span data-ttu-id="c70ea-268">XML ファイルをインポートして ProcessPurchaseOrder ポリシーを再作成するには</span><span class="sxs-lookup"><span data-stu-id="c70ea-268">To import the XML file to re-create the ProcessPurchaseOrder policy</span></span>  
  
1. <span data-ttu-id="c70ea-269">BizTalk Server 管理コンソールで **コンソール ルート**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、順に展開**BizTalk グループ**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-269">In BizTalk Server Administration, expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then expand **BizTalk Group**.</span></span>  
  
2. <span data-ttu-id="c70ea-270">右クリック**アプリケーション**、 をポイント**インポート**、 をクリックし、**ポリシー**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-270">Right-click **Applications**, point to **Import**, and then click **Policies**.</span></span>  
  
3. <span data-ttu-id="c70ea-271">参照、および XML ファイルをダブルクリックします (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**)、最初の手順で作成しました。</span><span class="sxs-lookup"><span data-stu-id="c70ea-271">Browse, and double-click the XML file (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**) that you created in the first procedure.</span></span>  
  
4. <span data-ttu-id="c70ea-272">展開**\<すべての成果物\>** **アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-272">Expand **\<All Artifacts\>** under **Applications**.</span></span>  
  
5. <span data-ttu-id="c70ea-273">クリックして**ポリシー**のバージョン 1.3 を確認する必要があります、 **ProcessPurchaseOrder**が一覧にします。</span><span class="sxs-lookup"><span data-stu-id="c70ea-273">Click **Policies**, and you should see version 1.3 of the **ProcessPurchaseOrder** policy in the list.</span></span>  
  
6. <span data-ttu-id="c70ea-274">F5 キーを押してビューを更新します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-274">Press F5 to refresh the view.</span></span> <span data-ttu-id="c70ea-275">**ProcessPurchaseOrder**にする必要があります、**非公開**状態。</span><span class="sxs-lookup"><span data-stu-id="c70ea-275">The **ProcessPurchaseOrder** policy should be in the **Not Published** state.</span></span>  
  
#### <a name="to-add-the-processpurchaseorder-policy-to-the-ruletestapp-application"></a><span data-ttu-id="c70ea-276">RuleTestApp アプリケーションに ProcessPurchaseOrder ポリシーを追加するには</span><span class="sxs-lookup"><span data-stu-id="c70ea-276">To add the ProcessPurchaseOrder policy to the RuleTestApp application</span></span>  
  
1.  <span data-ttu-id="c70ea-277">BizTalk Server 管理コンソールで、右クリック**ProcessPurchaseOrder**ポリシー、およびクリック**発行**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-277">In BizTalk Server Administration, right-click **ProcessPurchaseOrder** policy, and then click **Publish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c70ea-278">BizTalk アプリケーションに追加できるのは、公開済みのポリシーだけです。</span><span class="sxs-lookup"><span data-stu-id="c70ea-278">Only published policies can be added to a BizTalk application.</span></span>  
  
2.  <span data-ttu-id="c70ea-279">**アプリケーション**ノード展開**RuleTestApp**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-279">In the **Applications** node, expand **RuleTestApp**.</span></span>  
  
3.  <span data-ttu-id="c70ea-280">クリックして**ポリシー**で**RuleTestApp**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-280">Click **Policies** in **RuleTestApp**.</span></span>  
  
4.  <span data-ttu-id="c70ea-281">右側の一覧内を右クリックし、[**追加**、] をクリックし、**ポリシー**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-281">Right-click in the list on the right, point to **Add**, and then click **Policy**.</span></span>  
  
5.  <span data-ttu-id="c70ea-282">展開、 **ProcessPurchaseOrder**ノードを選択、チェック ボックスを**バージョン 1.3 (Published)**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-282">Expand the **ProcessPurchaseOrder** node, select the check box for **Version 1.3 (Published)**, and then click **OK**.</span></span> <span data-ttu-id="c70ea-283">.</span><span class="sxs-lookup"><span data-stu-id="c70ea-283">.</span></span>  
  
6.  <span data-ttu-id="c70ea-284">右クリック**ProcessPurchaseOrder**、 をクリックし、**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-284">Right-click **ProcessPurchaseOrder**, and then click **Deploy**.</span></span> <span data-ttu-id="c70ea-285">表示されない場合**ProcessPurchaseOrder**一覧で、f5 キーを押して表示を更新します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-285">If you do not see **ProcessPurchaseOrder** in the list, press F5 to refresh the view.</span></span>  
  
7.  <span data-ttu-id="c70ea-286">クリックして**はい**確認のメッセージ ボックスにします。</span><span class="sxs-lookup"><span data-stu-id="c70ea-286">Click **Yes** in the confirmation message box.</span></span>  
  
## <a name="procedures-for-deploying-the-policy-by-using-an-msi-file"></a><span data-ttu-id="c70ea-287">MSI ファイルを使用したポリシーの展開手順</span><span class="sxs-lookup"><span data-stu-id="c70ea-287">Procedures for Deploying the Policy by Using an MSI File</span></span>  
  
#### <a name="to-export-the-ruletestapp-application-to-an-msi-file"></a><span data-ttu-id="c70ea-288">RuleTestApp アプリケーションを MSI ファイルにエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="c70ea-288">To export the RuleTestApp application to an MSI file</span></span>  
  
1. <span data-ttu-id="c70ea-289">**開始**] メニューの [open **BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-289">On the **Start** menu, open **BizTalk Server Administration**.</span></span> <span data-ttu-id="c70ea-290">このツールを既に開いている場合は、F5 キーを押して更新します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-290">If you have the tool already open, press F5 to refresh it.</span></span>  
  
2. <span data-ttu-id="c70ea-291">展開**コンソール ルート**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、順に展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-291">Expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="c70ea-292">右クリックして**RuleTestApp**、 をポイント**エクスポート**、順にクリックします**MSI ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-292">Right-click **RuleTestApp**, point to **Export**, and then click **MSI file**.</span></span>  
  
4. <span data-ttu-id="c70ea-293">**MSI ファイルのエクスポート ウィザードへようこそ**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-293">On the **Welcome to the Export MSI File Wizard** page, click **Next**.</span></span>  
  
5. <span data-ttu-id="c70ea-294">**リソースの選択**ページで既定のオプションすべてを確認し、をクリックし、**次**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-294">On the **Select Resources** page, review all the default options, and then click **Next**.</span></span>  
  
6. <span data-ttu-id="c70ea-295">**IIS ホストの指定**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-295">On the **Specify IIS Hosts** page, click **Next**.</span></span>  
  
7. <span data-ttu-id="c70ea-296">**依存関係**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-296">On the **Dependencies** page, click **Next**.</span></span>  
  
8. <span data-ttu-id="c70ea-297">**先**として MSI の名前とディレクトリの指定 ページで、 **C:\BRE-Walkthroughs\RuleTestApp.msi**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-297">On the **Destination** page, specify the directory and name for the MSI as **C:\BRE-Walkthroughs\RuleTestApp.msi**.</span></span>  
  
9. <span data-ttu-id="c70ea-298">**[エクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c70ea-298">Click **Export**.</span></span>  
  
10. <span data-ttu-id="c70ea-299">**概要**] ページで [**完了**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-299">On the **Summary** page, click **Finish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c70ea-300">RuleTestApp アプリケーションをエクスポートすると、アプリケーションで使用されるポリシーとボキャブラリも MSI ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="c70ea-300">When you export the RuleTestApp application, the policies and vocabularies used by the application are also exported in the MSI file.</span></span> <span data-ttu-id="c70ea-301">後で MSI ファイルをインポートすると、ボキャブラリ、ポリシー、およびアプリケーションが、すべて再作成されます。</span><span class="sxs-lookup"><span data-stu-id="c70ea-301">Later, when you import the MSI file, the vocabulary, policy, and application are all re-created.</span></span>  
  
#### <a name="to-delete-the-ruletestapp-application"></a><span data-ttu-id="c70ea-302">RuleTestApp アプリケーションを削除するには</span><span class="sxs-lookup"><span data-stu-id="c70ea-302">To delete the RuleTestApp application</span></span>  
  
1.  <span data-ttu-id="c70ea-303">BizTalk Server 管理コンソールで、右クリック**RuleTestApp**、確認の場合と、**削除**メニューを有効または無効になっています。</span><span class="sxs-lookup"><span data-stu-id="c70ea-303">In BizTalk Server Administration, right-click **RuleTestApp**, and check if the **Delete** menu is enabled or disabled.</span></span>  
  
2.  <span data-ttu-id="c70ea-304">場合**削除**は右クリックし、無効になっています**RuleTestApp**、 をクリック**停止**を選択します**完全停止 - インスタンスの終了**、順にクリックします。**停止**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-304">If **Delete** is disabled, right-click **RuleTestApp**, click **Stop**, select **Full Stop - Terminate Instance**, and then click **Stop**.</span></span>  
  
3.  <span data-ttu-id="c70ea-305">右クリック**RuleTestApp**、 をクリックし、**削除**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-305">Right-click **RuleTestApp**, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="c70ea-306">クリックして**はい**削除を確定します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-306">Click **Yes** to confirm deletion.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c70ea-307">アプリケーションを削除すると、アプリケーション内のすべてのポリシーとそれらが依存するボキャブラリも、ルール エンジン データベースから削除されます。</span><span class="sxs-lookup"><span data-stu-id="c70ea-307">When you delete an application, all the policies in the application and dependent vocabularies are deleted from the rule engine database as well.</span></span>  
  
#### <a name="to-verify-that-the-processpurchaseorder-policy-and-povocabulary-vocabulary-are-deleted"></a><span data-ttu-id="c70ea-308">ProcessPurchaseOrder ポリシーと POVocabulary ボキャブラリが削除されたことを確認するには</span><span class="sxs-lookup"><span data-stu-id="c70ea-308">To verify that the ProcessPurchaseOrder policy and POVocabulary vocabulary are deleted</span></span>  
  
1.  <span data-ttu-id="c70ea-309">**開始**] メニューの [open**ビジネス ルール作成ツール**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-309">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="c70ea-310">既にを開き、更新、f5 キーを押してのビジネス ルール作成ツールの場合は。</span><span class="sxs-lookup"><span data-stu-id="c70ea-310">If you have Business Rule Composer already open, press F5 to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c70ea-311">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="c70ea-311">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="c70ea-312">これを行うには、アプリケーションを右クリックし、**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-312">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="c70ea-313">ポリシー エクスプ ローラー ウィンドウで、**ポリシー**、ProcessPurchaseOrder ポリシーが存在しないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-313">In the Policy Explorer window, expand **Policies**, and make sure that the ProcessPurchaseOrder policy does not exist.</span></span>  
  
3.  <span data-ttu-id="c70ea-314">ファクト エクスプ ローラー ウィンドウで、**ボキャブラリ**POVocabulary が存在しないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-314">In the Facts Explorer window, expand **Vocabularies**, and make sure that POVocabulary does not exist.</span></span>  
  
#### <a name="to-import-the-msi-file-to-re-create-the-ruletestapp-application"></a><span data-ttu-id="c70ea-315">MSI ファイルをインポートして RuleTestApp アプリケーションを再作成するには</span><span class="sxs-lookup"><span data-stu-id="c70ea-315">To import the MSI file to re-create the RuleTestApp application</span></span>  
  
1. <span data-ttu-id="c70ea-316">**開始**] メニューの [open **BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-316">On the **Start** menu, open **BizTalk Server Administration**.</span></span> <span data-ttu-id="c70ea-317">BizTalk Server 管理コンソールを既に開いている場合は、F5 キーを押して更新します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-317">If you have the BizTalk Server Administration console already open, press F5 to refresh it.</span></span>  
  
2. <span data-ttu-id="c70ea-318">展開**コンソール ルート**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、順に展開**BizTalk グループ**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-318">Expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then expand **BizTalk Group**.</span></span>  
  
3. <span data-ttu-id="c70ea-319">右クリック**アプリケーション**、 をポイント**インポート**、 をクリックし、 **MSI ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-319">Right-click **Applications**, point to **Import**, and then click **MSI file**.</span></span>  
  
4. <span data-ttu-id="c70ea-320">**のインポート ウィザードへようこそ** ページで 参照 しての前にエクスポートした MSI ファイル (RuleTestApp.msi) を選択して、**インポートする MSI ファイル**設定。</span><span class="sxs-lookup"><span data-stu-id="c70ea-320">On the **Welcome to the Import Wizard** page, browse and select the MSI file (RuleTestApp.msi) you exported earlier for the **MSI file to import** setting.</span></span>  
  
5. <span data-ttu-id="c70ea-321">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c70ea-321">Click **Next**.</span></span>  
  
6. <span data-ttu-id="c70ea-322">**アプリケーション設定**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-322">On the **Application Settings** page, click **Next**.</span></span>  
  
7. <span data-ttu-id="c70ea-323">**アプリケーション ターゲット環境の設定**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-323">On the **Application Target Environment Settings** page, click **Next**.</span></span>  
  
8. <span data-ttu-id="c70ea-324">**インポートの概要**] ページで [**インポート**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-324">On the **Import Summary** page, click **Import**.</span></span>  
  
9. <span data-ttu-id="c70ea-325">**インポートに成功しました**] ページで [**完了**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-325">On the **Import Succeeded** page, click **Finish**.</span></span> <span data-ttu-id="c70ea-326">表示する必要があります、 **RuleTestApp**下にアプリケーションが作成**アプリケーション**BizTalk Server 管理コンソールでします。</span><span class="sxs-lookup"><span data-stu-id="c70ea-326">You should see that the **RuleTestApp** application is created under **Applications** in the BizTalk Server Administration console.</span></span>  
  
#### <a name="to-verify-that-the-processpurchaseorder-policy-is-added-to-ruletestapp"></a><span data-ttu-id="c70ea-327">RuleTestApp に ProcessPurchaseOrder ポリシーが追加されたことを確認するには</span><span class="sxs-lookup"><span data-stu-id="c70ea-327">To verify that the ProcessPurchaseOrder policy is added to RuleTestApp</span></span>  
  
1.  <span data-ttu-id="c70ea-328">展開**RuleTestApp** BizTalk Server 管理コンソールでします。</span><span class="sxs-lookup"><span data-stu-id="c70ea-328">Expand **RuleTestApp** in the BizTalk Server Administration console.</span></span>  
  
2.  <span data-ttu-id="c70ea-329">選択**ポリシー**と表示されます**ProcessPurchaseOrder**右側のウィンドウの一覧。</span><span class="sxs-lookup"><span data-stu-id="c70ea-329">Select **Policies** and you should see **ProcessPurchaseOrder** in the list in the right pane.</span></span>  
  
#### <a name="to-verify-that-the-processpurchaseorder-policy-and-povocabulary-vocabulary-are-re-created"></a><span data-ttu-id="c70ea-330">ProcessPurchaseOrder ポリシーと POVocabulary ボキャブラリが再作成されたことを確認するには</span><span class="sxs-lookup"><span data-stu-id="c70ea-330">To verify that the ProcessPurchaseOrder policy and POVocabulary vocabulary are re-created</span></span>  
  
1.  <span data-ttu-id="c70ea-331">**開始**] メニューの [open**ビジネス ルール作成ツール**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-331">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="c70ea-332">既に開いている場合は、F5 キーを押して更新します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-332">If you have it already open, press F5 to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c70ea-333">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="c70ea-333">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="c70ea-334">これを行うには、アプリケーションを右クリックし、**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-334">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="c70ea-335">ポリシー エクスプ ローラー ウィンドウで、**ポリシー**、ことを確認および**ProcessPurchaseOrder**存在します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-335">In the Policy Explorer window, expand **Policies**, and make sure that **ProcessPurchaseOrder** exists.</span></span>  
  
3.  <span data-ttu-id="c70ea-336">ファクト エクスプ ローラー ウィンドウで、**ボキャブラリ**、ことを確認および**POVocabulary**存在します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-336">In the Facts Explorer window, expand **Vocabularies**, and make sure that **POVocabulary** exists.</span></span>  
  
#### <a name="to-test-the-solution"></a><span data-ttu-id="c70ea-337">ソリューションをテストするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c70ea-337">To test the solution</span></span>  
  
1. <span data-ttu-id="c70ea-338">**開始**] メニューの [open **BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-338">On the **Start** menu, open **BizTalk Server Administration**.</span></span> <span data-ttu-id="c70ea-339">BizTalk Server 管理コンソールを既に開いている場合は、F5 キーを押して更新します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-339">If you have the BizTalk Server Administration console already open, press F5 to refresh it.</span></span>  
  
2. <span data-ttu-id="c70ea-340">展開**コンソール ルート**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、順に展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-340">Expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="c70ea-341">右クリック**RuleTestApp**、 をクリックし、**開始**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-341">Right-click **RuleTestApp**, and then click **Start**.</span></span>  
  
4. <span data-ttu-id="c70ea-342">クリックして**開始**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-342">Click **Start**.</span></span>  
  
5. <span data-ttu-id="c70ea-343">コピー **SamplePO.xml**で作成した[チュートリアル: ポリシーのテスト](../core/walkthrough-testing-the-policy.md)オーケストレーションの入力ディレクトリにします。</span><span class="sxs-lookup"><span data-stu-id="c70ea-343">Copy **SamplePO.xml** that you created in [Walkthrough: Testing the Policy](../core/walkthrough-testing-the-policy.md) to the input directory for the orchestration.</span></span>  
  
6. <span data-ttu-id="c70ea-344">オーケストレーションの出力ディレクトリに、出力ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c70ea-344">You should see an output file in the output directory for the orchestration.</span></span> <span data-ttu-id="c70ea-345">出力 XML ファイルを開き、注意の値、**状態**にフィールドが設定されている**Approved**します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-345">Open the output XML file and notice that the value of the **Status** field is set to **Approved**.</span></span>  
  
7. <span data-ttu-id="c70ea-346">手順 3. と 4. を繰り返します**SamplePO2.xml**、いることを確認しの値、**状態**出力ドキュメント内のフィールドは、入力ドキュメントと同じ (**XYZ**)。</span><span class="sxs-lookup"><span data-stu-id="c70ea-346">Repeat steps 3 and 4 with **SamplePO2.xml**, and notice that the value of the **Status** field in the output document is the same as in the input document (**XYZ**).</span></span>  
  
## <a name="comments"></a><span data-ttu-id="c70ea-347">コメント</span><span class="sxs-lookup"><span data-stu-id="c70ea-347">Comments</span></span>  
  
-   <span data-ttu-id="c70ea-348">**非常に重要な**ことに注意して、アプリケーションからポリシーを削除するときをだけを削除しないアプリケーションとポリシー間の関連付けは、するも、ポリシーとその関連付けられたボキャブラリをルールから削除エンジンのデータベースです。</span><span class="sxs-lookup"><span data-stu-id="c70ea-348">It is **very important** to remember that when you remove a policy from an application, you do not just remove the association between the application and the policy; you also delete the policy and its associated vocabulary from the rule engine database.</span></span>  
  
-   <span data-ttu-id="c70ea-349">既定では、アプリケーションを開始すると、ポリシーが自動的に展開されます。</span><span class="sxs-lookup"><span data-stu-id="c70ea-349">When you start an application, by default, it deploys the policies automatically.</span></span> <span data-ttu-id="c70ea-350">同様に、アプリケーションを停止し、選択する**完全停止 - インスタンスを終了**、関連付けられているポリシーは展開解除に自動的にします。</span><span class="sxs-lookup"><span data-stu-id="c70ea-350">Similarly, when you stop an application and select **Full Stop - Terminate Instances**, the associated policies are undeployed automatically.</span></span> <span data-ttu-id="c70ea-351">選択すると**部分停止 - 実行中のインスタンスを中断**、関連付けられているポリシーが解除されません自動的にします。</span><span class="sxs-lookup"><span data-stu-id="c70ea-351">When you select **Partial Stop - Suspend running instances**, the associated policies are not undeployed automatically.</span></span>  
  
-   <span data-ttu-id="c70ea-352">ビジネス ルール作成ツールと BizTalk Server 管理コンソールで操作を実行する前には、ビューを更新して、最新の情報を確実に表示してください。</span><span class="sxs-lookup"><span data-stu-id="c70ea-352">You should refresh the views in Business Rule Composer and BizTalk Server Administration console to make sure you are looking at the latest information before performing any operation.</span></span>  
  
-   <span data-ttu-id="c70ea-353">以前のバージョンが BizTalk アプリケーションに関連付けられているポリシーに、新しいバージョンを作成する場合、ポリシーの新しいバージョンを手動でアプリケーションに追加してください。</span><span class="sxs-lookup"><span data-stu-id="c70ea-353">If you create a new version of the policy whose earlier version is associated with a BizTalk application, you should manually add the new version of the policy to the application.</span></span> <span data-ttu-id="c70ea-354">ルール エンジン データベースから削除する場合を除いて、ポリシーの古いバージョンは削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="c70ea-354">You should not remove the old version of the policy unless you really want to delete it from the rule engine database.</span></span>  
  
-   <span data-ttu-id="c70ea-355">インポート前に、複数の BRL (ビジネス ルール言語 XML ファイル) ファイルを単一の BRL ファイルに結合できます。</span><span class="sxs-lookup"><span data-stu-id="c70ea-355">You can merge two or more BRL (Business Rule Language XML file) files into a single BRL file before importing.</span></span> <span data-ttu-id="c70ea-356">次のコードは 3 つの BRL ファイルを示しています。</span><span class="sxs-lookup"><span data-stu-id="c70ea-356">The following code shows three BRL files.</span></span> <span data-ttu-id="c70ea-357">最初の BRL ファイルに含まれる、 **POVocabulary**ボキャブラリです。</span><span class="sxs-lookup"><span data-stu-id="c70ea-357">The first BRL file contains the **POVocabulary** vocabulary.</span></span> <span data-ttu-id="c70ea-358">2 番目の BRL ファイルに含まれる、 **ProcessPurchaseOrder**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="c70ea-358">The second BRL file contains the **ProcessPurchaseOrder** policy.</span></span> <span data-ttu-id="c70ea-359">3 番目の BRL ファイルには、両方が含まれています、 **POVocabulary**ボキャブラリと**ProcessPurchaseOrder**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="c70ea-359">The third BRL file contains both the **POVocabulary** vocabulary and the **ProcessPurchaseOrder** policy.</span></span> <span data-ttu-id="c70ea-360">3 番目の BRE ファイルを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-360">The third BRE file is created by performing the following steps:</span></span>  
  
    1.  <span data-ttu-id="c70ea-361">エディターの任意のファイルを使用して新しいファイルを作成し、XML ファイルとして保存します (例: POPolicyVocabulary.xml)。</span><span class="sxs-lookup"><span data-stu-id="c70ea-361">Create a new file using any file editor and save it as an XML file (for example: POPolicyVocabulary.xml).</span></span>  
  
    2.  <span data-ttu-id="c70ea-362">ボキャブラリが含まれている 1 番目の BRL ファイルから、XML コンテンツ全体をコピーします。</span><span class="sxs-lookup"><span data-stu-id="c70ea-362">Copy the entire XML content from the first BRL file containing the vocabulary.</span></span>  
  
    3.  <span data-ttu-id="c70ea-363">ルール セット ブロックのコピー (で始まる、 \<ruleset\>タグと末尾には、 \</ruleset\>タグ)、2 番目の BRL ファイルから。</span><span class="sxs-lookup"><span data-stu-id="c70ea-363">Copy the ruleset block (starts with the \<ruleset\> tag and ends with the \</ruleset\> tag) from the second BRL file.</span></span>  
  
    4.  <span data-ttu-id="c70ea-364">新しいファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="c70ea-364">Save the new file.</span></span> <span data-ttu-id="c70ea-365">この単一の XML ファイルを作成するをインポートすることができます、 **POVocabulary**ボキャブラリと**ProcessPurchaseOrder**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="c70ea-365">You can import this single XML file to create the **POVocabulary** vocabulary and the **ProcessPurchaseOrder** policy.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c70ea-366">結合された BRL ファイル内での、ボキャブラリ ノードとルール セット ノードの順序に意味はありません。</span><span class="sxs-lookup"><span data-stu-id="c70ea-366">It does not matter in which order the vocabulary and ruleset nodes are listed in the merged BRL file.</span></span> <span data-ttu-id="c70ea-367">ルール セット ノードをボキャブラリ ノードより前に置いてもかまいません。</span><span class="sxs-lookup"><span data-stu-id="c70ea-367">You can have the ruleset node ahead of the vocabulary node.</span></span>  
  
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