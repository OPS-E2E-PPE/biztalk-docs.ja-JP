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
ms.openlocfilehash: 99c44b8104cd17cba5430b36bf1a2aa4144f2b60
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392385"
---
# <a name="walkthrough-deploying-the-policy"></a><span data-ttu-id="3a88e-102">チュートリアル: ポリシーの展開</span><span class="sxs-lookup"><span data-stu-id="3a88e-102">Walkthrough: Deploying the Policy</span></span>
<span data-ttu-id="3a88e-103">このチュートリアルを展開するための手順について説明します、 **ProcessPurchaseOrder**次の 3 つの方法でポリシー。</span><span class="sxs-lookup"><span data-stu-id="3a88e-103">This walkthrough provides step-by-step instructions for deploying the **ProcessPurchaseOrder** policy in the following three ways:</span></span>  
  
-   <span data-ttu-id="3a88e-104">エクスポートして、ビジネス ルール エンジン展開ウィザードを使用して、ポリシーをインポートします。</span><span class="sxs-lookup"><span data-stu-id="3a88e-104">Exporting and importing the policy by using the Business Rules Engine Deployment Wizard.</span></span>  
  
-   <span data-ttu-id="3a88e-105">XML ファイルと XML ファイルから BizTalk Server 管理コンソールを使用して、ポリシーをインポートするには、ポリシーをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="3a88e-105">Exporting the policy to an XML file and importing the policy from an XML file by using the BizTalk Server Administration console.</span></span>  
  
-   <span data-ttu-id="3a88e-106">MSI ファイルの一部として、ポリシーをエクスポートし、BizTalk Server 管理コンソールを使用して MSI ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="3a88e-106">Exporting the policy as part of an MSI file and importing the MSI file by using BizTalk Server Administration console.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3a88e-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="3a88e-107">Prerequisites</span></span>  
 <span data-ttu-id="3a88e-108">完了する必要があります、[チュートリアル。ポリシー実行の追跡](../core/walkthrough-tracking-policy-execution.md)このチュートリアルを実行する前にチュートリアル。</span><span class="sxs-lookup"><span data-stu-id="3a88e-108">You must complete the [Walkthrough: Tracking Policy Execution](../core/walkthrough-tracking-policy-execution.md) walkthrough before performing this walkthrough.</span></span>  
  
## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="3a88e-109">このチュートリアルの概要</span><span class="sxs-lookup"><span data-stu-id="3a88e-109">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="3a88e-110">このトピックには、次の 3 つのチュートリアルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3a88e-110">This topic  contains the following three walkthroughs:</span></span>  
  
1.  <span data-ttu-id="3a88e-111">最初のチュートリアルには展開手順が含まれています、 **ProcessPurchaseOrder**ビジネス ルール エンジン展開ウィザードを使用してポリシー。</span><span class="sxs-lookup"><span data-stu-id="3a88e-111">The first walkthrough contains procedures for deploying the **ProcessPurchaseOrder** policy by using the Business Rules Engine Deployment Wizard.</span></span> <span data-ttu-id="3a88e-112">次の表では、このチュートリアルの手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-112">The following table describes the procedures in this walkthrough.</span></span>  
  
    |<span data-ttu-id="3a88e-113">プロシージャ タイトル</span><span class="sxs-lookup"><span data-stu-id="3a88e-113">Procedure title</span></span>|<span data-ttu-id="3a88e-114">手順の説明</span><span class="sxs-lookup"><span data-stu-id="3a88e-114">Procedure description</span></span>|  
    |---------------------|---------------------------|  
    |<span data-ttu-id="3a88e-115">ビジネス ルール エンジン展開ウィザードを使用して POVocabulary 1.0 および 1.1 をエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="3a88e-115">To export POVocabulary 1.0 and 1.1 by using the Business Rules Engine Deployment Wizard</span></span>|<span data-ttu-id="3a88e-116">バージョン 1.0 および 1.1 をエクスポートするための手順について説明します、 **POVocabulary**ボキャブラリを XML には、ビジネス ルール エンジン展開ウィザードを使用してファイルします。</span><span class="sxs-lookup"><span data-stu-id="3a88e-116">Provides step-by-step instructions for exporting versions 1.0 and 1.1 of the **POVocabulary** vocabulary to XML files by using the Business Rules Engine Deployment Wizard.</span></span>|  
    |<span data-ttu-id="3a88e-117">ビジネス ルール エンジン展開ウィザードを使用して ProcessPurchaseOrder 1.3 をエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="3a88e-117">To export ProcessPurchaseOrder 1.3 by using the Business Rules Engine Deployment Wizard</span></span>|<span data-ttu-id="3a88e-118">バージョン 1.3 をエクスポートするための手順について説明します、 **ProcessPurchaseOrder**ビジネス ルール エンジン展開ウィザードを使用して XML ファイルにポリシー。</span><span class="sxs-lookup"><span data-stu-id="3a88e-118">Provides step-by-step instructions for exporting version 1.3 of the **ProcessPurchaseOrder** policy to an XML file by using the Business Rules Engine Deployment Wizard.</span></span>|  
    |<span data-ttu-id="3a88e-119">ProcessPurchaseOrder および POVocabulary を削除するには</span><span class="sxs-lookup"><span data-stu-id="3a88e-119">To delete ProcessPurchaseOrder and POVocabulary</span></span>|<span data-ttu-id="3a88e-120">削除するための手順について説明します、 **ProcessPurchaseOrder**ポリシーと**POVocabulary**ボキャブラリを再作成するファイル、XML のインポートをテストできるようにします。</span><span class="sxs-lookup"><span data-stu-id="3a88e-120">Provides step-by-step instructions for deleting the **ProcessPurchaseOrder** policy and **POVocabulary** vocabulary so that you can test importing the XML files to re-create them.</span></span>|  
    |<span data-ttu-id="3a88e-121">POVocabulary 1.0 および 1.1 を再作成する XML からインポートするには</span><span class="sxs-lookup"><span data-stu-id="3a88e-121">To import from XML to re-create POVocabulary 1.0 and 1.1</span></span>|<span data-ttu-id="3a88e-122">再作成する最初の手順で作成したボキャブラリ XML ファイルをインポートするための手順を提供します、 **POVocabulary**ボキャブラリです。</span><span class="sxs-lookup"><span data-stu-id="3a88e-122">Provides step-by-step instructions for importing the vocabulary XML file you created in the first procedure to re-create the **POVocabulary** vocabulary.</span></span>|  
    |<span data-ttu-id="3a88e-123">確認するには、その POVocabulary 1.0 および 1.1 が再作成されます。</span><span class="sxs-lookup"><span data-stu-id="3a88e-123">To verify that POVocabulary 1.0 and 1.1 are re-created</span></span>|<span data-ttu-id="3a88e-124">ビジネス ルール作成ツールを使用して検証するための手順は、のバージョン 1.0 および 1.1 **POVocabulary**は再作成します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-124">Provides step-by-step instructions for using the Business Rule Composer to verify that versions 1.0 and 1.1 of **POVocabulary** are re-created.</span></span>|  
    |<span data-ttu-id="3a88e-125">ProcessPurchaseOrder 1.3 を再作成する XML からインポートするには</span><span class="sxs-lookup"><span data-stu-id="3a88e-125">To import from XML to re-create ProcessPurchaseOrder 1.3</span></span>|<span data-ttu-id="3a88e-126">バージョン 1.3 を再作成する 2 番目の手順で作成したポリシー XML ファイルをインポートするための手順を提供します、 **ProcessPurchaseOrder**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="3a88e-126">Provides step-by-step instructions for importing the policy XML file you created in the second procedure to re-create version 1.3 of the **ProcessPurchaseOrder** policy.</span></span>|  
    |<span data-ttu-id="3a88e-127">ProcessPurchaseOrder 1.3 が再作成されたことを確認するには</span><span class="sxs-lookup"><span data-stu-id="3a88e-127">To verify that ProcessPurchaseOrder 1.3 is re-created</span></span>|<span data-ttu-id="3a88e-128">ビジネス ルール作成ツールを使用して、バージョン 1.3 を検証するための手順について説明します、 **ProcessPurchaseOrder**ポリシーが再作成されます。</span><span class="sxs-lookup"><span data-stu-id="3a88e-128">Provides step-by-step instructions for using the Business Rule Composer to verify that version 1.3 of the **ProcessPurchaseOrder** policy is re-created.</span></span>|  
  
2.  <span data-ttu-id="3a88e-129">2 番目のチュートリアルには展開手順が含まれています、 **ProcessPurchaseOrder**次の BizTalk Server 管理コンソールからエクスポートされたポリシー XML ファイルを使用してテーブルには、この手順がについて説明しますチュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="3a88e-129">The second walkthrough contains procedures for deploying the **ProcessPurchaseOrder** policy by using an XML file exported from the BizTalk Server Administration console The following table describes the procedures in this walkthrough.</span></span>  
  
    |<span data-ttu-id="3a88e-130">プロシージャ タイトル</span><span class="sxs-lookup"><span data-stu-id="3a88e-130">Procedure title</span></span>|<span data-ttu-id="3a88e-131">手順の説明</span><span class="sxs-lookup"><span data-stu-id="3a88e-131">Procedure description</span></span>|  
    |---------------------|---------------------------|  
    |<span data-ttu-id="3a88e-132">ProcessPurchaseOrder 1.3 ポリシーと POVocabulary ボキャブラリを XML ファイルにエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="3a88e-132">To export the ProcessPurchaseOrder 1.3 policy and the POVocabulary vocabulary to an XML file</span></span>|<span data-ttu-id="3a88e-133">BizTalk Server 管理コンソールを使用してエクスポートする手順について説明します、 **ProcessPurchaseOrder**ポリシーと**POVocabulary**ボキャブラリを XML ファイルにします。</span><span class="sxs-lookup"><span data-stu-id="3a88e-133">Provides step-by-step instructions for using the BizTalk Server Administration console to export the **ProcessPurchaseOrder** policy and the **POVocabulary** vocabulary to an XML file.</span></span>|  
    |<span data-ttu-id="3a88e-134">ProcessPurchaseOrder ポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="3a88e-134">To delete the ProcessPurchaseOrder policy</span></span>|<span data-ttu-id="3a88e-135">削除するための手順について説明します、 **ProcessPurchaseOrder**からポリシー **RuleTestApp**とルール エンジン データベース。</span><span class="sxs-lookup"><span data-stu-id="3a88e-135">Provides step-by-step instructions for deleting the **ProcessPurchaseOrder** policy from **RuleTestApp** and the rule engine database.</span></span>|  
    |<span data-ttu-id="3a88e-136">ProcessPurchaseOrder ポリシーを再作成する XML ファイルをインポートするには</span><span class="sxs-lookup"><span data-stu-id="3a88e-136">To import the XML file to re-create the ProcessPurchaseOrder policy</span></span>|<span data-ttu-id="3a88e-137">再作成する最初の手順でエクスポートした XML ファイルをインポートするための手順を提供します、 **ProcessPurchaseOrder**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="3a88e-137">Provides step-by-step instructions for importing the XML file you exported in the first procedure to re-create the **ProcessPurchaseOrder** policy.</span></span>|  
    |<span data-ttu-id="3a88e-138">RuleTestApp アプリケーションに ProcessPurchaseOrder ポリシーを追加するには</span><span class="sxs-lookup"><span data-stu-id="3a88e-138">To add the ProcessPurchaseOrder policy to the RuleTestApp application</span></span>|<span data-ttu-id="3a88e-139">追加するための手順について説明します、 **ProcessPurchaseOrder**ポリシーを**RuleTestApp**アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="3a88e-139">Provides step-by-step instructions for adding the **ProcessPurchaseOrder** policy to the **RuleTestApp** application.</span></span>|  
  
3.  <span data-ttu-id="3a88e-140">3 番目のチュートリアルには展開手順が含まれています、 **ProcessPurchaseOrder** MSI ファイルを使用してポリシーが BizTalk Server 管理コンソールからエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="3a88e-140">The third walkthrough contains procedures for deploying the **ProcessPurchaseOrder** policy by using an MSI file exported from the BizTalk Server Administration console.</span></span> <span data-ttu-id="3a88e-141">次の表では、このチュートリアルの手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-141">The following table describes the procedures in this walkthrough.</span></span>  
  
    |<span data-ttu-id="3a88e-142">プロシージャ タイトル</span><span class="sxs-lookup"><span data-stu-id="3a88e-142">Procedure title</span></span>|<span data-ttu-id="3a88e-143">手順の詳細な手順では</span><span class="sxs-lookup"><span data-stu-id="3a88e-143">Procedure has step-by-step instructions for</span></span>|  
    |---------------------|---------------------------------------------------|  
    |<span data-ttu-id="3a88e-144">RuleTestApp アプリケーションを MSI ファイルをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="3a88e-144">To export the RuleTestApp application to an MSI file</span></span>|<span data-ttu-id="3a88e-145">エクスポートするための手順について説明します、 **RuleTestApp**を MSI ファイルを後で、アプリケーションを再作成に使用されるアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="3a88e-145">Provides step-by-step instructions for exporting the **RuleTestApp** application to an MSI file, which is used later to re-create the application.</span></span>|  
    |<span data-ttu-id="3a88e-146">RuleTestApp アプリケーションを削除するには</span><span class="sxs-lookup"><span data-stu-id="3a88e-146">To delete the RuleTestApp application</span></span>|<span data-ttu-id="3a88e-147">削除するための手順について説明します、 **RuleTestApp**アプリケーションの MSI ファイルを使用してアプリケーションを再作成をテストできるようにします。</span><span class="sxs-lookup"><span data-stu-id="3a88e-147">Provides step-by-step instructions for deleting the **RuleTestApp** application so that you can test re-creating the application by using the MSI file.</span></span>|  
    |<span data-ttu-id="3a88e-148">ProcessPurchaseOrder ポリシーと POVocabulary ボキャブラリが削除されたことを確認するには</span><span class="sxs-lookup"><span data-stu-id="3a88e-148">To verify that the ProcessPurchaseOrder policy and POVocabulary vocabulary are deleted</span></span>|<span data-ttu-id="3a88e-149">ビジネス ルール作成ツールを使用していることを確認する手順について説明します、 **ProcessPurchaseOrder**ポリシーと POVocabulary ボキャブラリが削除されます。</span><span class="sxs-lookup"><span data-stu-id="3a88e-149">Provides step-by-step instructions for using the Business Rule Composer to verify that the **ProcessPurchaseOrder** policy and POVocabulary vocabulary are deleted.</span></span>|  
    |<span data-ttu-id="3a88e-150">RuleTestApp アプリケーションを再作成する MSI ファイルをインポートするには</span><span class="sxs-lookup"><span data-stu-id="3a88e-150">To import the MSI file to re-create the RuleTestApp application</span></span>|<span data-ttu-id="3a88e-151">再作成する、BizTalk Server 管理コンソールを使用して MSI ファイルをインポートする手順について説明します、 **RuleTestApp**アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="3a88e-151">Provides step-by-step instructions for using the BizTalk Server Administration console to import the MSI file to re-create the **RuleTestApp** application.</span></span>|  
    |<span data-ttu-id="3a88e-152">RuleTestApp に ProcessPurchaseOrder ポリシーが追加されたことを確認するには</span><span class="sxs-lookup"><span data-stu-id="3a88e-152">To verify that the ProcessPurchaseOrder policy is added to RuleTestApp</span></span>|<span data-ttu-id="3a88e-153">BizTalk Server 管理コンソールを使用していることを確認する手順について説明します、 **ProcessPurchaseOrder**ポリシーに追加されます、 **RuleTestApp**アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="3a88e-153">Provides step-by-step instructions for using the BizTalk Server Administration console to verify that the **ProcessPurchaseOrder** policy is added to the **RuleTestApp** application.</span></span>|  
    |<span data-ttu-id="3a88e-154">ProcessPurchaseOrder ポリシーと POVocabulary ボキャブラリが再作成されたことを確認するには</span><span class="sxs-lookup"><span data-stu-id="3a88e-154">To verify that the ProcessPurchaseOrder policy and POVocabulary vocabulary are re-created</span></span>|<span data-ttu-id="3a88e-155">ビジネス ルール作成ツールを使用していることを確認する手順について説明します、 **ProcessPurchaseOrder**ポリシーと**POVocabulary**ボキャブラリが再作成されます。</span><span class="sxs-lookup"><span data-stu-id="3a88e-155">Provides step-by-step instructions for using the Business Rule Composer to verify that the **ProcessPurchaseOrder** policy and **POVocabulary** vocabulary are re-created.</span></span>|  
    |<span data-ttu-id="3a88e-156">ソリューションをテストするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3a88e-156">To test the solution</span></span>|<span data-ttu-id="3a88e-157">ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="3a88e-157">Provides step-by-step instructions for testing the solution.</span></span>|  
  
## <a name="procedures-for-deploying-the-processpurchaseorder-policy-by-using-the-business-rules-engine-deployment-wizard"></a><span data-ttu-id="3a88e-158">ビジネス ルール エンジン展開ウィザードを使用して ProcessPurchaseOrder ポリシーを展開するための手順</span><span class="sxs-lookup"><span data-stu-id="3a88e-158">Procedures for Deploying the ProcessPurchaseOrder Policy by Using the Business Rules Engine Deployment Wizard</span></span>  
  
#### <a name="to-export-povocabulary-10-and-11-by-using-the-business-rules-engine-deployment-wizard"></a><span data-ttu-id="3a88e-159">ビジネス ルール エンジン展開ウィザードを使用して POVocabulary 1.0 および 1.1 をエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="3a88e-159">To export POVocabulary 1.0 and 1.1 by using the Business Rules Engine Deployment Wizard</span></span>  
  
1.  <span data-ttu-id="3a88e-160">**開始**] メニューの [open**ビジネス ルール エンジン展開ウィザード**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-160">On the **Start** menu, open **Business Rules Engine Deployment Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3a88e-161">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="3a88e-161">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="3a88e-162">これを行うには、アプリケーションを右クリックし、**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-162">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="3a88e-163">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3a88e-163">Click **Next**.</span></span>  
  
3.  <span data-ttu-id="3a88e-164">**展開タスク**] ページで、[**エクスポート ポリシー/ボキャブラリをファイルにデータベースから**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-164">On the **Deployment Task** page, select **Export Policy/Vocabulary to file from database**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="3a88e-165">**ポリシー ストア**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-165">On the **Policy Store** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="3a88e-166">**ポリシー/ボキャブラリのエクスポート**] ページで [**ボキャブラリ**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-166">On the **Export Policy/Vocabulary** page, click **Vocabulary**.</span></span>  
  
6.  <span data-ttu-id="3a88e-167">選択**POVocabulary.1.0**のドロップダウン リストから**ポリシー/ボキャブラリ**入力するか、XML 出力ファイル名を指定する参照**C:\BRE-walkthroughs\POVocabulary10.xml**、 をクリックし、**次**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-167">Select **POVocabulary.1.0** from the drop-down list for **Policy/Vocabulary**, type or browse to specify the XML output file name as **C:\BRE-walkthroughs\POVocabulary10.xml**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="3a88e-168">**準備ができて**] ページで [**次**。</span><span class="sxs-lookup"><span data-stu-id="3a88e-168">On the **Ready** page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="3a88e-169">**ポリシー/ボキャブラリのエクスポート**] ページで [ **[次へ]。**</span><span class="sxs-lookup"><span data-stu-id="3a88e-169">On the **Exporting Policy/Vocabulary** page, click **Next.**</span></span>  
  
9. <span data-ttu-id="3a88e-170">選択**このウィザードを再度実行**、 をクリックし、**完了**。</span><span class="sxs-lookup"><span data-stu-id="3a88e-170">Select **Run this wizard again**, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="3a88e-171">選択したので、**このウィザードを再度実行**ウィザードの最初の画面が再度表示されます。</span><span class="sxs-lookup"><span data-stu-id="3a88e-171">Because you selected **Run this wizard again**, the first screen of the wizard appears again.</span></span>  
  
10. <span data-ttu-id="3a88e-172">手順 2. ~ 6. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-172">Repeat steps 2-6.</span></span>  
  
11. <span data-ttu-id="3a88e-173">選択**POVocabulary.1.1**のドロップダウン リストから**ポリシー/ボキャブラリ**入力するか、XML 出力ファイル名を指定する参照**C:\BRE-walkthroughs\POVocabulary11.xml**、 をクリックし、**次**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-173">Select **POVocabulary.1.1** from the drop-down list for **Policy/Vocabulary**, type or browse to specify the XML output file name as **C:\BRE-walkthroughs\POVocabulary11.xml**, and then click **Next**.</span></span>  
  
12. <span data-ttu-id="3a88e-174">手順 8. と 9. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-174">Repeat steps 8 and 9.</span></span>  
  
13. <span data-ttu-id="3a88e-175">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3a88e-175">Click **Finish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3a88e-176">バージョン 1.0 と version 1.1 の両方をエクスポートする必要がある**POVocabulary**ため**ProcessPurchaseOrder** 1.3 の両方のバージョンによって異なります**POVocabulary**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-176">You need to export both version 1.0 and version 1.1 of **POVocabulary** because **ProcessPurchaseOrder** 1.3 depends on both versions of **POVocabulary**.</span></span> <span data-ttu-id="3a88e-177">**許可される項目の最大数**バージョン 1.1 のボキャブラリから定義を使用します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-177">The **Maximum number of items allowed** definition is used from version 1.1 of the vocabulary.</span></span> <span data-ttu-id="3a88e-178">**要求された数量**と**要求の状態**バージョン 1.0 からの定義が使用されます。</span><span class="sxs-lookup"><span data-stu-id="3a88e-178">The **Requested Quantity** and **Request Status** definitions are used from version 1.0.</span></span>  
  
#### <a name="to-export-processpurchaseorder-13-by-using-the-business-rule-engine-deployment-wizard"></a><span data-ttu-id="3a88e-179">ビジネス ルール エンジン展開ウィザードを使用して ProcessPurchaseOrder 1.3 をエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="3a88e-179">To export ProcessPurchaseOrder 1.3 by using the Business Rule Engine Deployment Wizard</span></span>  
  
1.  <span data-ttu-id="3a88e-180">**開始**] メニューの [open**ビジネス ルール エンジン展開ウィザード**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-180">On the **Start** menu, open **Business Rules Engine Deployment Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3a88e-181">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="3a88e-181">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="3a88e-182">これを行うには、アプリケーションを右クリックし、**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-182">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="3a88e-183">**、ルール エンジン展開ウィザードへようこそ**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-183">On the **Welcome to the Rules Engine Deployment Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="3a88e-184">選択**エクスポート ポリシー/ボキャブラリをファイルにデータベースから**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-184">Select **Export Policy/Vocabulary to file from database**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="3a88e-185">**ポリシー ストア**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-185">On the **Policy Store** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="3a88e-186">いることを確認、**ポリシー**オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-186">Verify that the **Policy** option is selected.</span></span>  
  
6.  <span data-ttu-id="3a88e-187">選択**ProcessPurchaseOrder.1.3**のドロップダウン リストから**ポリシー/ボキャブラリ**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-187">Select **ProcessPurchaseOrder.1.3** from the drop-down list for **Policy/Vocabulary**.</span></span>  
  
7.  <span data-ttu-id="3a88e-188">入力するかを指定する参照**C:\BRE-walkthroughs\ProcessPOPolicy13.xml**として、XML 出力ファイル名。</span><span class="sxs-lookup"><span data-stu-id="3a88e-188">Type or browse to specify **C:\BRE-walkthroughs\ProcessPOPolicy13.xml** as the XML output file name.</span></span>  
  
8.  <span data-ttu-id="3a88e-189">をクリックして**次**4 回、順にクリックします**完了**。</span><span class="sxs-lookup"><span data-stu-id="3a88e-189">Click **Next** thrice, and then click **Finish**.</span></span>  
  
#### <a name="to-delete-processpurchaseorder-and-povocabulary"></a><span data-ttu-id="3a88e-190">ProcessPurchaseOrder および POVocabulary を削除するには</span><span class="sxs-lookup"><span data-stu-id="3a88e-190">To delete ProcessPurchaseOrder and POVocabulary</span></span>  
  
1.  <span data-ttu-id="3a88e-191">**開始**] メニューの [open**ビジネス ルール作成ツール**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-191">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="3a88e-192">開く、f5 キーを押して、またはをクリックを既にのビジネス ルール作成ツールがあるかどうかは**再読み込み**上、**ファイル**メニューを更新します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-192">If you have Business Rule Composer already open, press F5 or click **Reload** on the **File** menu to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3a88e-193">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="3a88e-193">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="3a88e-194">これを行うには、アプリケーションを右クリックし、**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-194">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="3a88e-195">ポリシー エクスプ ローラー ウィンドウで、**ポリシー**、展開**ProcessPurchaseOrder**を右クリックして**バージョン 1.0**、順にクリックします**削除**.</span><span class="sxs-lookup"><span data-stu-id="3a88e-195">In the Policy Explorer window, expand **Policies**, expand **ProcessPurchaseOrder**, right-click **Version 1.0**, and then click **Delete**.</span></span> <span data-ttu-id="3a88e-196">場合**削除**は右クリックし、無効になっています。**バージョン 1.0**、順にクリックします**Undeploy**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-196">If **Delete** is disabled, right-click **Version 1.0**, and then click **Undeploy**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3a88e-197">展開されたポリシー バージョンを削除できません。</span><span class="sxs-lookup"><span data-stu-id="3a88e-197">The deployed policy versions cannot be deleted.</span></span> <span data-ttu-id="3a88e-198">ポリシーのバージョンを削除する前に、ポリシーの展開を解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a88e-198">You must undeploy a policy before deleting a policy version.</span></span>  
  
3.  <span data-ttu-id="3a88e-199">クリックして**はい**確認のメッセージ ボックスにします。</span><span class="sxs-lookup"><span data-stu-id="3a88e-199">Click **Yes** in the confirmation message box.</span></span>  
  
4.  <span data-ttu-id="3a88e-200">手順 2. および 3. 削除を**バージョン 1.1**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-200">Repeat steps 2 and 3 to delete **Version 1.1**.</span></span>  
  
5.  <span data-ttu-id="3a88e-201">手順 2. および 3. 削除を**バージョン 1.2**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-201">Repeat steps 2 and 3 to delete **Version 1.2**.</span></span>  
  
6.  <span data-ttu-id="3a88e-202">右クリック**Version 1.3 - Deployed**、 をクリックし、 **Undeploy**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-202">Right-click **Version 1.3 - Deployed**, and then click **Undeploy**.</span></span> <span data-ttu-id="3a88e-203">場合、 **Undeploy**オプションが無効になっている、この手順を無視します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-203">If the **Undeploy** option is disabled, ignore this step.</span></span>  
  
7.  <span data-ttu-id="3a88e-204">ファクト エクスプ ローラー ウィンドウで、**ボキャブラリ**を右クリックして**POVocabulary**、 をクリックし、**削除**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-204">In the Facts Explorer window, expand **Vocabularies**, right-click **POVocabulary**, and then click **Delete**.</span></span>  
  
#### <a name="to-import-from-xml-to-re-create-povocabulary-10-and-11"></a><span data-ttu-id="3a88e-205">POVocabulary 1.0 および 1.1 を再作成する XML からインポートするには</span><span class="sxs-lookup"><span data-stu-id="3a88e-205">To import from XML to re-create POVocabulary 1.0 and 1.1</span></span>  
  
1.  <span data-ttu-id="3a88e-206">**開始**] メニューの [open**ビジネス ルール エンジン展開ウィザード**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-206">On the **Start** menu, open **Business Rules Engine Deployment Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3a88e-207">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="3a88e-207">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="3a88e-208">これを行うには、アプリケーションを右クリックし、**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-208">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="3a88e-209">**、ルール エンジン展開ウィザードへようこそ**、 をクリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-209">On the **Welcome to the Rules Engine Deployment Wizard**, click **Next**.</span></span>  
  
3.  <span data-ttu-id="3a88e-210">**展開タスク**] ページで、[**インポート ポリシー/ボキャブラリをファイルからデータベースに発行し、**、順にクリックします**次**。</span><span class="sxs-lookup"><span data-stu-id="3a88e-210">On the **Deployment Task** page, select **Import and publish Policy/Vocabulary to database from file**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="3a88e-211">**ポリシー ストア**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-211">On the **Policy Store** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="3a88e-212">参照し、選択、 **POVocabulary10.xml**最初の手順で作成したファイル。</span><span class="sxs-lookup"><span data-stu-id="3a88e-212">Browse and select the **POVocabulary10.xml** file you created in the first procedure.</span></span>  
  
6.  <span data-ttu-id="3a88e-213">をクリックして**オープン**かダブルクリック**POVocabulary10.xml**。</span><span class="sxs-lookup"><span data-stu-id="3a88e-213">Click **Open** or double-click **POVocabulary10.xml**.</span></span>  
  
7.  <span data-ttu-id="3a88e-214">クリックして**次**ビジネス ルール エンジン展開ウィザードでします。</span><span class="sxs-lookup"><span data-stu-id="3a88e-214">Click **Next** in the Business Rules Engine Deployment Wizard.</span></span>  
  
8.  <span data-ttu-id="3a88e-215">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3a88e-215">Click **Next**.</span></span>  
  
9. <span data-ttu-id="3a88e-216">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3a88e-216">Click **Next**.</span></span>  
  
10. <span data-ttu-id="3a88e-217">選択**このウィザードを再度実行**、 をクリックし、**完了**。</span><span class="sxs-lookup"><span data-stu-id="3a88e-217">Select **Run this wizard again**, and then click **Finish**.</span></span>  
  
11. <span data-ttu-id="3a88e-218">手順 2 ~ 9 をインポートする**POVocabulary11.xml**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-218">Repeat steps 2-9 to import **POVocabulary11.xml**.</span></span>  
  
12. <span data-ttu-id="3a88e-219">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3a88e-219">Click **Finish**.</span></span>  
  
#### <a name="to-verify-that-povocabulary-10-and-11-are-re-created"></a><span data-ttu-id="3a88e-220">確認するには、その POVocabulary 1.0 および 1.1 が再作成されます。</span><span class="sxs-lookup"><span data-stu-id="3a88e-220">To verify that POVocabulary 1.0 and 1.1 are re-created</span></span>  
  
1.  <span data-ttu-id="3a88e-221">**開始**] メニューの [open**ビジネス ルール作成ツール**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-221">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="3a88e-222">既に開かれていることがある場合、f5 キーを押すか をクリックして**再読み込み**上、**ファイル**メニューを更新します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-222">If you have it already open, press F5 or click **Reload** on the **File** menu to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3a88e-223">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="3a88e-223">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="3a88e-224">これを行うには、アプリケーションを右クリックし、**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-224">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="3a88e-225">[ファクト エクスプ ローラー] ウィンドウ、**ボキャブラリ**タブ。</span><span class="sxs-lookup"><span data-stu-id="3a88e-225">In the Facts Explorer window, click the **Vocabularies** tab.</span></span>  
  
3.  <span data-ttu-id="3a88e-226">展開**ボキャブラリ**、ください**POVocabulary**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-226">Expand **Vocabularies**, and you should see **POVocabulary**.</span></span>  
  
4.  <span data-ttu-id="3a88e-227">展開**POVocabulary**、ください**バージョン 1.0**と**バージョン 1.1**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-227">Expand **POVocabulary**, and you should see **Version 1.0** and **Version 1.1**.</span></span>  
  
#### <a name="to-import-from-xml-to-re-create-processpurchaseorder-13"></a><span data-ttu-id="3a88e-228">ProcessPurchaseOrder 1.3 を再作成する XML からインポートするには</span><span class="sxs-lookup"><span data-stu-id="3a88e-228">To import from XML to re-create ProcessPurchaseOrder 1.3</span></span>  
  
1.  <span data-ttu-id="3a88e-229">**開始**] メニューの [open**ビジネス ルール エンジン展開ウィザード**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-229">On the **Start** menu, open **Business Rules Engine Deployment Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3a88e-230">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="3a88e-230">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="3a88e-231">これを行うには、アプリケーションを右クリックし、**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-231">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="3a88e-232">**、ルール エンジン展開ウィザードへようこそ**、 をクリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-232">On the **Welcome to the Rules Engine Deployment Wizard**, click **Next**.</span></span>  
  
3.  <span data-ttu-id="3a88e-233">**展開タスク**] ページで、[**インポート ポリシー/ボキャブラリをファイルからデータベースをファイルからデータベースに発行し、**、順にクリックします**次**。</span><span class="sxs-lookup"><span data-stu-id="3a88e-233">On the **Deployment Task** page, select **Import and publish Policy/Vocabulary to database from fileto database from file**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="3a88e-234">**ポリシー ストア**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-234">On the **Policy Store** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="3a88e-235">参照し、選択、 **ProcessPOPolicy13.xml**このチュートリアルで先ほど作成したファイル。</span><span class="sxs-lookup"><span data-stu-id="3a88e-235">Browse and select the **ProcessPOPolicy13.xml** file you created earlier in this walkthrough.</span></span>  
  
6.  <span data-ttu-id="3a88e-236">をクリックして**オープン**かダブルクリック**ProcessPOPolicy13.xml**。</span><span class="sxs-lookup"><span data-stu-id="3a88e-236">Click **Open** or double-click **ProcessPOPolicy13.xml**.</span></span>  
  
7.  <span data-ttu-id="3a88e-237">クリックして**次**ビジネス ルール エンジン展開ウィザードでします。</span><span class="sxs-lookup"><span data-stu-id="3a88e-237">Click **Next** in the Business Rules Engine Deployment Wizard.</span></span>  
  
8.  <span data-ttu-id="3a88e-238">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3a88e-238">Click **Next**.</span></span>  
  
9. <span data-ttu-id="3a88e-239">**[次へ]** をクリックし、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3a88e-239">Click **Next**, and then click **Finish**.</span></span>  
  
#### <a name="to-verify-that-processpurchaseorder-13-is-re-created"></a><span data-ttu-id="3a88e-240">ProcessPurchaseOrder 1.3 が再作成されたことを確認するには</span><span class="sxs-lookup"><span data-stu-id="3a88e-240">To verify that ProcessPurchaseOrder 1.3 is re-created</span></span>  
  
1.  <span data-ttu-id="3a88e-241">**開始**] メニューの [open**ビジネス ルール作成ツール**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-241">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="3a88e-242">既に開かれていることがある場合、f5 キーを押すか をクリックして**再読み込み**上、**ファイル**メニューを更新します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-242">If you have it already open, press F5 or click **Reload** on the **File** menu to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3a88e-243">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="3a88e-243">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="3a88e-244">これを行うには、アプリケーションを右クリックし、**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-244">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="3a88e-245">ポリシー エクスプ ローラー ウィンドウで、**ポリシー**ください**ProcessPurchaseOrder**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-245">In the Policy Explorer window, expand **Policies** and you should see **ProcessPurchaseOrder**.</span></span>  
  
3.  <span data-ttu-id="3a88e-246">展開**ProcessPurchaseOrder**ください**Version 1.3 - Published**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-246">Expand **ProcessPurchaseOrder** and you should see **Version 1.3 - Published**.</span></span>  
  
## <a name="procedures-for-deploying-the-policy-by-using-an-xml-file-exported-from-the-biztalk-server-administration-console"></a><span data-ttu-id="3a88e-247">BizTalk Server 管理コンソールからエクスポートされたファイルの XML を使用して、ポリシーを展開するための手順</span><span class="sxs-lookup"><span data-stu-id="3a88e-247">Procedures for Deploying the Policy by Using an XML file Exported from the BizTalk Server Administration Console</span></span>  
  
#### <a name="to-export-the-processpurchaseorder-13-policy-and-the-povocabulary-vocabulary-to-an-xml-file"></a><span data-ttu-id="3a88e-248">ProcessPurchaseOrder 1.3 ポリシーと POVocabulary ボキャブラリを XML ファイルにエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="3a88e-248">To export the ProcessPurchaseOrder 1.3 policy and the POVocabulary vocabulary to an XML file</span></span>  
  
1. <span data-ttu-id="3a88e-249">**開始**] メニューの [open[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-249">On the **Start** menu, open [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span> <span data-ttu-id="3a88e-250">既に開かれているツールがあれば、f5 キーを押して更新します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-250">If you have the tool already open, press F5 to refresh it.</span></span>  
  
2. <span data-ttu-id="3a88e-251">展開**コンソール ルート**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**、順に展開**RuleTestApp**.</span><span class="sxs-lookup"><span data-stu-id="3a88e-251">Expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, expand **Applications**, and then expand **RuleTestApp**.</span></span>  
  
3. <span data-ttu-id="3a88e-252">クリックして**ポリシー**し、ProcessPurchaseOrder 1.3 ポリシーが一覧表示されるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-252">Click **Policies** and make sure that you see the ProcessPurchaseOrder 1.3 policy in the list.</span></span>  
  
4. <span data-ttu-id="3a88e-253">右クリックして**ProcessPurchaseOrder**、 をクリックし、**エクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-253">Right-click **ProcessPurchaseOrder**, and then click **Export**.</span></span>  
  
5. <span data-ttu-id="3a88e-254">**ポリシーのエクスポート** ダイアログ ボックスで、確認、 **ProcessPurchaseOrder**ポリシーと**POVocabulary**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="3a88e-254">In the **Export Policies** dialog box, make sure the **ProcessPurchaseOrder** policy and the **POVocabulary** are selected.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="3a88e-255">右クリックし、XML ファイルに、アプリケーション内のすべてのポリシーをエクスポートする**RuleTest**  をクリックし、**エクスポート**で、**ポリシー**メニュー。</span><span class="sxs-lookup"><span data-stu-id="3a88e-255">You can export all the policies in an application to an XML file by right-clicking **RuleTest** and then clicking **Export** on the **Policies** menu.</span></span> <span data-ttu-id="3a88e-256">このようにすべてのポリシーと単一の XML ファイルには、このアプリケーションで使用されるボキャブラリをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="3a88e-256">This way you can export all the policies and vocabulary used by this application to a single XML file.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="3a88e-257">右クリックし、XML ファイルにすべてのアプリケーション内のすべてのポリシーをエクスポートすることができます、**アプリケーション**ノードをクリックして**エクスポート**上、**ポリシー**メニュー。</span><span class="sxs-lookup"><span data-stu-id="3a88e-257">You can export all the policies in all the applications to an XML file by right-clicking the **Applications** node and then clicking **Export** on the **Policies** menu.</span></span> <span data-ttu-id="3a88e-258">このように、すべてのポリシーと 1 つの XML ファイルにすべてのアプリケーションで使用されているボキャブラリをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="3a88e-258">This way you can export all the policies and vocabularies used by all the applications into a single XML file.</span></span>  
  
6. <span data-ttu-id="3a88e-259">出力 XML ファイル名を指定 (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**)、をクリックし、 **Ok**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-259">Specify an output XML file name (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**), and then click **Ok**.</span></span>  
  
#### <a name="to-delete-the-processpurchaseorder-policy"></a><span data-ttu-id="3a88e-260">ProcessPurchaseOrder ポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="3a88e-260">To delete the ProcessPurchaseOrder policy</span></span>  
  
1.  <span data-ttu-id="3a88e-261">BizTalk Server 管理コンソールで、右クリック**ProcessPurchaseOrder**  をクリックし、一覧で**削除**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-261">In BizTalk Server Administration, right-click **ProcessPurchaseOrder** in the list, and then click **Remove**.</span></span>  
  
2.  <span data-ttu-id="3a88e-262">をクリックして**はい**で、**削除ポリシー**メッセージ ボックス。</span><span class="sxs-lookup"><span data-stu-id="3a88e-262">Click **Yes** in the **Remove Policy** message box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3a88e-263">ポリシーが展開された状態にある場合は削除できません。</span><span class="sxs-lookup"><span data-stu-id="3a88e-263">If the policy is in the deployed state, it cannot be removed.</span></span> <span data-ttu-id="3a88e-264">右クリック**ProcessPurchaseOrder**、順にクリックします**Undeploy**ポリシーの展開を解除します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-264">Right-click **ProcessPurchaseOrder**, and then click **Undeploy** to undeploy the policy.</span></span> <span data-ttu-id="3a88e-265">**削除**ポリシーが展開時に、メニュー項目が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3a88e-265">The **Remove** menu item is available when the policy is undeployed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3a88e-266">ボキャブラリ、 **ProcessPurchaseOrder**ここでポリシーが依存**POVocabulary**も削除されます。</span><span class="sxs-lookup"><span data-stu-id="3a88e-266">The vocabularies on which the **ProcessPurchaseOrder** policy depends, in this case **POVocabulary**, are also deleted.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3a88e-267">アプリケーションからポリシーを削除するときに、ポリシーとボキャブラリに依存しているがアプリケーションからだけでなく同様に、ルール エンジン データベースから削除します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-267">When you remove a policy from an application, the policy and the vocabularies that it depends on are deleted from the rule engine database as well, not just from the application.</span></span>  
  
#### <a name="to-import-the-xml-file-to-re-create-the-processpurchaseorder-policy"></a><span data-ttu-id="3a88e-268">ProcessPurchaseOrder ポリシーを再作成する XML ファイルをインポートするには</span><span class="sxs-lookup"><span data-stu-id="3a88e-268">To import the XML file to re-create the ProcessPurchaseOrder policy</span></span>  
  
1. <span data-ttu-id="3a88e-269">BizTalk Server 管理コンソールで **コンソール ルート**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、順に展開**BizTalk グループ**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-269">In BizTalk Server Administration, expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then expand **BizTalk Group**.</span></span>  
  
2. <span data-ttu-id="3a88e-270">右クリック**アプリケーション**、 をポイント**インポート**、 をクリックし、**ポリシー**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-270">Right-click **Applications**, point to **Import**, and then click **Policies**.</span></span>  
  
3. <span data-ttu-id="3a88e-271">参照、および XML ファイルをダブルクリックします (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**)、最初の手順で作成しました。</span><span class="sxs-lookup"><span data-stu-id="3a88e-271">Browse, and double-click the XML file (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**) that you created in the first procedure.</span></span>  
  
4. <span data-ttu-id="3a88e-272">展開**\<すべての成果物\>** **アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-272">Expand **\<All Artifacts\>** under **Applications**.</span></span>  
  
5. <span data-ttu-id="3a88e-273">クリックして**ポリシー**のバージョン 1.3 を確認する必要があります、 **ProcessPurchaseOrder**が一覧にします。</span><span class="sxs-lookup"><span data-stu-id="3a88e-273">Click **Policies**, and you should see version 1.3 of the **ProcessPurchaseOrder** policy in the list.</span></span>  
  
6. <span data-ttu-id="3a88e-274">F5 キーを押して表示を更新します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-274">Press F5 to refresh the view.</span></span> <span data-ttu-id="3a88e-275">**ProcessPurchaseOrder**にする必要があります、**非公開**状態。</span><span class="sxs-lookup"><span data-stu-id="3a88e-275">The **ProcessPurchaseOrder** policy should be in the **Not Published** state.</span></span>  
  
#### <a name="to-add-the-processpurchaseorder-policy-to-the-ruletestapp-application"></a><span data-ttu-id="3a88e-276">RuleTestApp アプリケーションに ProcessPurchaseOrder ポリシーを追加するには</span><span class="sxs-lookup"><span data-stu-id="3a88e-276">To add the ProcessPurchaseOrder policy to the RuleTestApp application</span></span>  
  
1.  <span data-ttu-id="3a88e-277">BizTalk Server 管理コンソールで、右クリック**ProcessPurchaseOrder**ポリシー、およびクリック**発行**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-277">In BizTalk Server Administration, right-click **ProcessPurchaseOrder** policy, and then click **Publish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3a88e-278">公開済みのポリシーは、BizTalk アプリケーションに追加できます。</span><span class="sxs-lookup"><span data-stu-id="3a88e-278">Only published policies can be added to a BizTalk application.</span></span>  
  
2.  <span data-ttu-id="3a88e-279">**アプリケーション**ノード展開**RuleTestApp**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-279">In the **Applications** node, expand **RuleTestApp**.</span></span>  
  
3.  <span data-ttu-id="3a88e-280">クリックして**ポリシー**で**RuleTestApp**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-280">Click **Policies** in **RuleTestApp**.</span></span>  
  
4.  <span data-ttu-id="3a88e-281">右側の一覧内を右クリックし、[**追加**、] をクリックし、**ポリシー**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-281">Right-click in the list on the right, point to **Add**, and then click **Policy**.</span></span>  
  
5.  <span data-ttu-id="3a88e-282">展開、 **ProcessPurchaseOrder**ノードを選択、チェック ボックスを**バージョン 1.3 (Published)**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-282">Expand the **ProcessPurchaseOrder** node, select the check box for **Version 1.3 (Published)**, and then click **OK**.</span></span> <span data-ttu-id="3a88e-283">.</span><span class="sxs-lookup"><span data-stu-id="3a88e-283">.</span></span>  
  
6.  <span data-ttu-id="3a88e-284">右クリック**ProcessPurchaseOrder**、 をクリックし、**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-284">Right-click **ProcessPurchaseOrder**, and then click **Deploy**.</span></span> <span data-ttu-id="3a88e-285">表示されない場合**ProcessPurchaseOrder**一覧で、f5 キーを押して表示を更新します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-285">If you do not see **ProcessPurchaseOrder** in the list, press F5 to refresh the view.</span></span>  
  
7.  <span data-ttu-id="3a88e-286">クリックして**はい**確認のメッセージ ボックスにします。</span><span class="sxs-lookup"><span data-stu-id="3a88e-286">Click **Yes** in the confirmation message box.</span></span>  
  
## <a name="procedures-for-deploying-the-policy-by-using-an-msi-file"></a><span data-ttu-id="3a88e-287">MSI ファイルを使用して、ポリシーを展開するための手順</span><span class="sxs-lookup"><span data-stu-id="3a88e-287">Procedures for Deploying the Policy by Using an MSI File</span></span>  
  
#### <a name="to-export-the-ruletestapp-application-to-an-msi-file"></a><span data-ttu-id="3a88e-288">RuleTestApp アプリケーションを MSI ファイルをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="3a88e-288">To export the RuleTestApp application to an MSI file</span></span>  
  
1. <span data-ttu-id="3a88e-289">**開始**] メニューの [open **BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-289">On the **Start** menu, open **BizTalk Server Administration**.</span></span> <span data-ttu-id="3a88e-290">既に開かれているツールがあれば、f5 キーを押して更新します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-290">If you have the tool already open, press F5 to refresh it.</span></span>  
  
2. <span data-ttu-id="3a88e-291">展開**コンソール ルート**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、順に展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-291">Expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="3a88e-292">右クリックして**RuleTestApp**、 をポイント**エクスポート**、順にクリックします**MSI ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-292">Right-click **RuleTestApp**, point to **Export**, and then click **MSI file**.</span></span>  
  
4. <span data-ttu-id="3a88e-293">**MSI ファイルのエクスポート ウィザードへようこそ**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-293">On the **Welcome to the Export MSI File Wizard** page, click **Next**.</span></span>  
  
5. <span data-ttu-id="3a88e-294">**リソースの選択**ページで既定のオプションすべてを確認し、をクリックし、**次**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-294">On the **Select Resources** page, review all the default options, and then click **Next**.</span></span>  
  
6. <span data-ttu-id="3a88e-295">**IIS ホストの指定**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-295">On the **Specify IIS Hosts** page, click **Next**.</span></span>  
  
7. <span data-ttu-id="3a88e-296">**依存関係**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-296">On the **Dependencies** page, click **Next**.</span></span>  
  
8. <span data-ttu-id="3a88e-297">**先**として MSI の名前とディレクトリの指定 ページで、 **C:\BRE-Walkthroughs\RuleTestApp.msi**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-297">On the **Destination** page, specify the directory and name for the MSI as **C:\BRE-Walkthroughs\RuleTestApp.msi**.</span></span>  
  
9. <span data-ttu-id="3a88e-298">**[エクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3a88e-298">Click **Export**.</span></span>  
  
10. <span data-ttu-id="3a88e-299">**概要**] ページで [**完了**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-299">On the **Summary** page, click **Finish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3a88e-300">RuleTestApp アプリケーションをエクスポートするときに、ポリシーとボキャブラリを使って、アプリケーションは MSI ファイルにもエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="3a88e-300">When you export the RuleTestApp application, the policies and vocabularies used by the application are also exported in the MSI file.</span></span> <span data-ttu-id="3a88e-301">後で、MSI ファイル、ボキャブラリ、ポリシー、およびアプリケーションをインポートすると、すべて再作成します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-301">Later, when you import the MSI file, the vocabulary, policy, and application are all re-created.</span></span>  
  
#### <a name="to-delete-the-ruletestapp-application"></a><span data-ttu-id="3a88e-302">RuleTestApp アプリケーションを削除するには</span><span class="sxs-lookup"><span data-stu-id="3a88e-302">To delete the RuleTestApp application</span></span>  
  
1.  <span data-ttu-id="3a88e-303">BizTalk Server 管理コンソールで、右クリック**RuleTestApp**、確認の場合と、**削除**メニューを有効または無効になっています。</span><span class="sxs-lookup"><span data-stu-id="3a88e-303">In BizTalk Server Administration, right-click **RuleTestApp**, and check if the **Delete** menu is enabled or disabled.</span></span>  
  
2.  <span data-ttu-id="3a88e-304">場合**削除**は右クリックし、無効になっています**RuleTestApp**、 をクリック**停止**を選択します**完全停止 - インスタンスの終了**、順にクリックします。**停止**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-304">If **Delete** is disabled, right-click **RuleTestApp**, click **Stop**, select **Full Stop - Terminate Instance**, and then click **Stop**.</span></span>  
  
3.  <span data-ttu-id="3a88e-305">右クリック**RuleTestApp**、 をクリックし、**削除**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-305">Right-click **RuleTestApp**, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="3a88e-306">クリックして**はい**削除を確定します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-306">Click **Yes** to confirm deletion.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3a88e-307">アプリケーションを削除するときにすべてのポリシー、アプリケーションと依存するボキャブラリをルール エンジン データベースから削除されます。</span><span class="sxs-lookup"><span data-stu-id="3a88e-307">When you delete an application, all the policies in the application and dependent vocabularies are deleted from the rule engine database as well.</span></span>  
  
#### <a name="to-verify-that-the-processpurchaseorder-policy-and-povocabulary-vocabulary-are-deleted"></a><span data-ttu-id="3a88e-308">ProcessPurchaseOrder ポリシーと POVocabulary ボキャブラリが削除されたことを確認するには</span><span class="sxs-lookup"><span data-stu-id="3a88e-308">To verify that the ProcessPurchaseOrder policy and POVocabulary vocabulary are deleted</span></span>  
  
1.  <span data-ttu-id="3a88e-309">**開始**] メニューの [open**ビジネス ルール作成ツール**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-309">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="3a88e-310">既にを開き、更新、f5 キーを押してのビジネス ルール作成ツールの場合は。</span><span class="sxs-lookup"><span data-stu-id="3a88e-310">If you have Business Rule Composer already open, press F5 to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3a88e-311">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="3a88e-311">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="3a88e-312">これを行うには、アプリケーションを右クリックし、**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-312">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="3a88e-313">ポリシー エクスプ ローラー ウィンドウで、**ポリシー**、ProcessPurchaseOrder ポリシーが存在しないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-313">In the Policy Explorer window, expand **Policies**, and make sure that the ProcessPurchaseOrder policy does not exist.</span></span>  
  
3.  <span data-ttu-id="3a88e-314">ファクト エクスプ ローラー ウィンドウで、**ボキャブラリ**POVocabulary が存在しないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-314">In the Facts Explorer window, expand **Vocabularies**, and make sure that POVocabulary does not exist.</span></span>  
  
#### <a name="to-import-the-msi-file-to-re-create-the-ruletestapp-application"></a><span data-ttu-id="3a88e-315">RuleTestApp アプリケーションを再作成する MSI ファイルをインポートするには</span><span class="sxs-lookup"><span data-stu-id="3a88e-315">To import the MSI file to re-create the RuleTestApp application</span></span>  
  
1. <span data-ttu-id="3a88e-316">**開始**] メニューの [open **BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-316">On the **Start** menu, open **BizTalk Server Administration**.</span></span> <span data-ttu-id="3a88e-317">BizTalk Server 管理コンソールを既に開いている場合は、F5 キーを押して更新します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-317">If you have the BizTalk Server Administration console already open, press F5 to refresh it.</span></span>  
  
2. <span data-ttu-id="3a88e-318">展開**コンソール ルート**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、順に展開**BizTalk グループ**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-318">Expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then expand **BizTalk Group**.</span></span>  
  
3. <span data-ttu-id="3a88e-319">右クリック**アプリケーション**、 をポイント**インポート**、 をクリックし、 **MSI ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-319">Right-click **Applications**, point to **Import**, and then click **MSI file**.</span></span>  
  
4. <span data-ttu-id="3a88e-320">**のインポート ウィザードへようこそ** ページで 参照 しての前にエクスポートした MSI ファイル (RuleTestApp.msi) を選択して、**インポートする MSI ファイル**設定。</span><span class="sxs-lookup"><span data-stu-id="3a88e-320">On the **Welcome to the Import Wizard** page, browse and select the MSI file (RuleTestApp.msi) you exported earlier for the **MSI file to import** setting.</span></span>  
  
5. <span data-ttu-id="3a88e-321">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3a88e-321">Click **Next**.</span></span>  
  
6. <span data-ttu-id="3a88e-322">**アプリケーション設定**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-322">On the **Application Settings** page, click **Next**.</span></span>  
  
7. <span data-ttu-id="3a88e-323">**アプリケーション ターゲット環境の設定**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-323">On the **Application Target Environment Settings** page, click **Next**.</span></span>  
  
8. <span data-ttu-id="3a88e-324">**インポートの概要**] ページで [**インポート**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-324">On the **Import Summary** page, click **Import**.</span></span>  
  
9. <span data-ttu-id="3a88e-325">**インポートに成功しました**] ページで [**完了**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-325">On the **Import Succeeded** page, click **Finish**.</span></span> <span data-ttu-id="3a88e-326">表示する必要があります、 **RuleTestApp**下にアプリケーションが作成**アプリケーション**BizTalk Server 管理コンソールでします。</span><span class="sxs-lookup"><span data-stu-id="3a88e-326">You should see that the **RuleTestApp** application is created under **Applications** in the BizTalk Server Administration console.</span></span>  
  
#### <a name="to-verify-that-the-processpurchaseorder-policy-is-added-to-ruletestapp"></a><span data-ttu-id="3a88e-327">RuleTestApp に ProcessPurchaseOrder ポリシーが追加されたことを確認するには</span><span class="sxs-lookup"><span data-stu-id="3a88e-327">To verify that the ProcessPurchaseOrder policy is added to RuleTestApp</span></span>  
  
1.  <span data-ttu-id="3a88e-328">展開**RuleTestApp** BizTalk Server 管理コンソールでします。</span><span class="sxs-lookup"><span data-stu-id="3a88e-328">Expand **RuleTestApp** in the BizTalk Server Administration console.</span></span>  
  
2.  <span data-ttu-id="3a88e-329">選択**ポリシー**と表示されます**ProcessPurchaseOrder**右側のウィンドウの一覧。</span><span class="sxs-lookup"><span data-stu-id="3a88e-329">Select **Policies** and you should see **ProcessPurchaseOrder** in the list in the right pane.</span></span>  
  
#### <a name="to-verify-that-the-processpurchaseorder-policy-and-povocabulary-vocabulary-are-re-created"></a><span data-ttu-id="3a88e-330">ProcessPurchaseOrder ポリシーと POVocabulary ボキャブラリが再作成されたことを確認するには</span><span class="sxs-lookup"><span data-stu-id="3a88e-330">To verify that the ProcessPurchaseOrder policy and POVocabulary vocabulary are re-created</span></span>  
  
1.  <span data-ttu-id="3a88e-331">**開始**] メニューの [open**ビジネス ルール作成ツール**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-331">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="3a88e-332">これがある場合、既に開かれている f5 キーを押して更新します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-332">If you have it already open, press F5 to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3a88e-333">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="3a88e-333">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="3a88e-334">これを行うには、アプリケーションを右クリックし、**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-334">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="3a88e-335">ポリシー エクスプ ローラー ウィンドウで、**ポリシー**、ことを確認および**ProcessPurchaseOrder**存在します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-335">In the Policy Explorer window, expand **Policies**, and make sure that **ProcessPurchaseOrder** exists.</span></span>  
  
3.  <span data-ttu-id="3a88e-336">ファクト エクスプ ローラー ウィンドウで、**ボキャブラリ**、ことを確認および**POVocabulary**存在します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-336">In the Facts Explorer window, expand **Vocabularies**, and make sure that **POVocabulary** exists.</span></span>  
  
#### <a name="to-test-the-solution"></a><span data-ttu-id="3a88e-337">ソリューションをテストするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3a88e-337">To test the solution</span></span>  
  
1. <span data-ttu-id="3a88e-338">**開始**] メニューの [open **BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-338">On the **Start** menu, open **BizTalk Server Administration**.</span></span> <span data-ttu-id="3a88e-339">BizTalk Server 管理コンソールを既に開いている場合は、F5 キーを押して更新します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-339">If you have the BizTalk Server Administration console already open, press F5 to refresh it.</span></span>  
  
2. <span data-ttu-id="3a88e-340">展開**コンソール ルート**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、順に展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-340">Expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="3a88e-341">右クリック**RuleTestApp**、 をクリックし、**開始**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-341">Right-click **RuleTestApp**, and then click **Start**.</span></span>  
  
4. <span data-ttu-id="3a88e-342">クリックして**開始**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-342">Click **Start**.</span></span>  
  
5. <span data-ttu-id="3a88e-343">コピー **SamplePO.xml**で作成した[チュートリアル。ポリシーのテスト](../core/walkthrough-testing-the-policy.md)オーケストレーションの入力ディレクトリにします。</span><span class="sxs-lookup"><span data-stu-id="3a88e-343">Copy **SamplePO.xml** that you created in [Walkthrough: Testing the Policy](../core/walkthrough-testing-the-policy.md) to the input directory for the orchestration.</span></span>  
  
6. <span data-ttu-id="3a88e-344">オーケストレーションの出力ディレクトリに出力ファイルを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a88e-344">You should see an output file in the output directory for the orchestration.</span></span> <span data-ttu-id="3a88e-345">出力 XML ファイルを開き、注意の値、**状態**にフィールドが設定されている**Approved**します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-345">Open the output XML file and notice that the value of the **Status** field is set to **Approved**.</span></span>  
  
7. <span data-ttu-id="3a88e-346">手順 3. と 4. を繰り返します**SamplePO2.xml**、いることを確認しの値、**状態**出力ドキュメント内のフィールドは、入力ドキュメントと同じ (**XYZ**)。</span><span class="sxs-lookup"><span data-stu-id="3a88e-346">Repeat steps 3 and 4 with **SamplePO2.xml**, and notice that the value of the **Status** field in the output document is the same as in the input document (**XYZ**).</span></span>  
  
## <a name="comments"></a><span data-ttu-id="3a88e-347">コメント</span><span class="sxs-lookup"><span data-stu-id="3a88e-347">Comments</span></span>  
  
-   <span data-ttu-id="3a88e-348">**非常に重要な**ことに注意して、アプリケーションからポリシーを削除するときをだけを削除しないアプリケーションとポリシー間の関連付けは、するも、ポリシーとその関連付けられたボキャブラリをルールから削除エンジンのデータベースです。</span><span class="sxs-lookup"><span data-stu-id="3a88e-348">It is **very important** to remember that when you remove a policy from an application, you do not just remove the association between the application and the policy; you also delete the policy and its associated vocabulary from the rule engine database.</span></span>  
  
-   <span data-ttu-id="3a88e-349">既定では、アプリケーションを起動するときに、ポリシーを自動的に配置します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-349">When you start an application, by default, it deploys the policies automatically.</span></span> <span data-ttu-id="3a88e-350">同様に、アプリケーションを停止し、選択する**完全停止 - インスタンスを終了**、関連付けられているポリシーは展開解除に自動的にします。</span><span class="sxs-lookup"><span data-stu-id="3a88e-350">Similarly, when you stop an application and select **Full Stop - Terminate Instances**, the associated policies are undeployed automatically.</span></span> <span data-ttu-id="3a88e-351">選択すると**部分停止 - 実行中のインスタンスを中断**、関連付けられているポリシーが解除されません自動的にします。</span><span class="sxs-lookup"><span data-stu-id="3a88e-351">When you select **Partial Stop - Suspend running instances**, the associated policies are not undeployed automatically.</span></span>  
  
-   <span data-ttu-id="3a88e-352">ビジネス ルール作成ツールと BizTalk Server 管理コンソールのいずれかの操作を実行する前に最新の情報が表示されているかどうかを確認するビューを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a88e-352">You should refresh the views in Business Rule Composer and BizTalk Server Administration console to make sure you are looking at the latest information before performing any operation.</span></span>  
  
-   <span data-ttu-id="3a88e-353">以前のバージョンが BizTalk アプリケーションに関連付けられたポリシーの新しいバージョンを作成する場合は、アプリケーションに新しいバージョンのポリシーを手動で追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a88e-353">If you create a new version of the policy whose earlier version is associated with a BizTalk application, you should manually add the new version of the policy to the application.</span></span> <span data-ttu-id="3a88e-354">実際に、ルール エンジン データベースから削除する場合、古いバージョンのポリシーを削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="3a88e-354">You should not remove the old version of the policy unless you really want to delete it from the rule engine database.</span></span>  
  
-   <span data-ttu-id="3a88e-355">インポートする前に、単一の BRL ファイルに 2 つまたは複数の BRL (ビジネス ルール言語 XML ファイル) ファイルをマージできます。</span><span class="sxs-lookup"><span data-stu-id="3a88e-355">You can merge two or more BRL (Business Rule Language XML file) files into a single BRL file before importing.</span></span> <span data-ttu-id="3a88e-356">次のコードでは、3 つの BRL ファイルを示します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-356">The following code shows three BRL files.</span></span> <span data-ttu-id="3a88e-357">最初の BRL ファイルに含まれる、 **POVocabulary**ボキャブラリです。</span><span class="sxs-lookup"><span data-stu-id="3a88e-357">The first BRL file contains the **POVocabulary** vocabulary.</span></span> <span data-ttu-id="3a88e-358">2 番目の BRL ファイルに含まれる、 **ProcessPurchaseOrder**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="3a88e-358">The second BRL file contains the **ProcessPurchaseOrder** policy.</span></span> <span data-ttu-id="3a88e-359">3 番目の BRL ファイルには、両方が含まれています、 **POVocabulary**ボキャブラリと**ProcessPurchaseOrder**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="3a88e-359">The third BRL file contains both the **POVocabulary** vocabulary and the **ProcessPurchaseOrder** policy.</span></span> <span data-ttu-id="3a88e-360">3 番目の BRE ファイルは、次の手順を実行することによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="3a88e-360">The third BRE file is created by performing the following steps:</span></span>  
  
    1.  <span data-ttu-id="3a88e-361">エディターの任意のファイルを使用して新しいファイルを作成し、XML ファイルとして保存します (例。POPolicyVocabulary.xml)。</span><span class="sxs-lookup"><span data-stu-id="3a88e-361">Create a new file using any file editor and save it as an XML file (for example: POPolicyVocabulary.xml).</span></span>  
  
    2.  <span data-ttu-id="3a88e-362">ボキャブラリを含む最初の BRL ファイルから XML コンテンツ全体をコピーします。</span><span class="sxs-lookup"><span data-stu-id="3a88e-362">Copy the entire XML content from the first BRL file containing the vocabulary.</span></span>  
  
    3.  <span data-ttu-id="3a88e-363">ルール セット ブロックのコピー (で始まる、 \<ruleset\>タグと末尾には、 \</ruleset\>タグ)、2 番目の BRL ファイルから。</span><span class="sxs-lookup"><span data-stu-id="3a88e-363">Copy the ruleset block (starts with the \<ruleset\> tag and ends with the \</ruleset\> tag) from the second BRL file.</span></span>  
  
    4.  <span data-ttu-id="3a88e-364">新しいファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="3a88e-364">Save the new file.</span></span> <span data-ttu-id="3a88e-365">この単一の XML ファイルを作成するをインポートすることができます、 **POVocabulary**ボキャブラリと**ProcessPurchaseOrder**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="3a88e-365">You can import this single XML file to create the **POVocabulary** vocabulary and the **ProcessPurchaseOrder** policy.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3a88e-366">関係ありません順序ボキャブラリと ruleset ノードは、結合された BRL ファイルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3a88e-366">It does not matter in which order the vocabulary and ruleset nodes are listed in the merged BRL file.</span></span> <span data-ttu-id="3a88e-367">ルール セット ノードをボキャブラリ ノードよりことができます。</span><span class="sxs-lookup"><span data-stu-id="3a88e-367">You can have the ruleset node ahead of the vocabulary node.</span></span>  
  
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