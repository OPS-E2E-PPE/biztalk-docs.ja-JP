---
title: '手順 6: 最大スループットを検証するための持続ロード パターンのテストを実行します |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dd790354-be9f-4278-bd15-493eac8970c9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6bfc0b9670366ab2f38046fcdc5497234b51ba5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302098"
---
# <a name="step-6-perform-constant-load-pattern-tests-to-verify-maximum-sustainable-throughput"></a><span data-ttu-id="7a9ce-102">手順 6: 最大スループットを検証するための持続ロード パターンのテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="7a9ce-102">Step 6: Perform Constant Load Pattern Tests to Verify Maximum Sustainable Throughput</span></span>
<span data-ttu-id="7a9ce-103">負荷を Visual Studio 2010 を使用して、BizTalk Server ソリューションをテストする場合、」の説明に従って、概算最大持続可能なスループット (MST) ソリューションが特定されると、持続ロード パターンのテストを実行する必要があります[手順 5: ステップ ロードの実行維持可能な最大のスループットを判断するテストのパターンを](../technical-guides/step-5-complete-step-load-tests-to-determine-maximum-sustainable-throughput.md)です。</span><span class="sxs-lookup"><span data-stu-id="7a9ce-103">When load testing a BizTalk Server solution using Visual Studio 2010, a constant load pattern test should be performed once the approximate Maximum Sustainable Throughput (MST) of the solution is determined as described in [Step 5: Perform Step Load Pattern Tests to Determine Maximum Sustainable Throughput](../technical-guides/step-5-complete-step-load-tests-to-determine-maximum-sustainable-throughput.md).</span></span> <span data-ttu-id="7a9ce-104">これは、時間の経過と共に、MST が維持可能なで実際にことを確認し、前進パフォーマンス調整を行う場合、BizTalk Server アプリケーションまたは環境へ適用の効果を評価する基準ロード テストを作成するために行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a9ce-104">This should be done to confirm that the MST is in fact sustainable over time and also so as to create a baseline load test moving forward to evaluate the effects of any performance tuning applied to the BizTalk Server application or environment.</span></span>  
  
## <a name="create-and-run-a-constant-load-pattern-test"></a><span data-ttu-id="7a9ce-105">定数のロード パターン テスト作成および実行</span><span class="sxs-lookup"><span data-stu-id="7a9ce-105">Create and run a Constant Load Pattern Test</span></span>  
 <span data-ttu-id="7a9ce-106">"BTS_Messaging_ として"BTS_Messaging_Step.loadtest"ステップ ロード パターンのテストを保存するだけでは、同じテスト ミックス、カウンター セットとテストのステップ ロード パターンで使用されるカウンター セットの割り当てを使用する定数のロード パターンのテストを作成する最も簡単な方法Constant.loadtest"し、いくつか"BTS_Messaging_Constant.loadtest"に変更します。</span><span class="sxs-lookup"><span data-stu-id="7a9ce-106">The easiest way to create a Constant Load Pattern test that uses the same Test Mix, Counter Sets, and Counter Set Mappings used by the Step Load Pattern test is to simply save the Step Load Pattern test “BTS_Messaging_Step.loadtest” as “BTS_Messaging_Constant.loadtest” and then make some changes to “BTS_Messaging_Constant.loadtest”.</span></span> <span data-ttu-id="7a9ce-107">定数のロード パターンを作成する手順はテストされているフォローは、既存のテストのステップ ロード パターンに基づきます。</span><span class="sxs-lookup"><span data-stu-id="7a9ce-107">Follow these steps to create a Constant Load Pattern test that is based upon the existing Step Load Pattern test:</span></span>  
  
1.  <span data-ttu-id="7a9ce-108">既に開かれていない場合は、BTS_Messaging_Step.loadtest を開きます。</span><span class="sxs-lookup"><span data-stu-id="7a9ce-108">Open BTS_Messaging_Step.loadtest if it is not already open.</span></span>  
  
2.  <span data-ttu-id="7a9ce-109">をクリックして**ファイル**選択**LoadTests\BTS_Messaging_Step.loadtest に名前を付けて**です。</span><span class="sxs-lookup"><span data-stu-id="7a9ce-109">Click **File** and select **Save LoadTests\BTS_Messaging_Step.loadtest As**.</span></span>  
  
3.  <span data-ttu-id="7a9ce-110">**ファイルに名前を付けて**] ダイアログ ボックスで、**ファイル名**C:\Projects\LoadTest\BTSLoad\LoadTests\BTS_Messaging_Constant.loadtest を入力し、[クリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="7a9ce-110">In the **Save File As** dialog box, next to **File name**, enter C:\Projects\LoadTest\BTSLoad\LoadTests\BTS_Messaging_Constant.loadtest and then click **Save**.</span></span>  
  
4.  <span data-ttu-id="7a9ce-111">ロード テスト エディターで、シナリオの名前を変更**BTS_Messaging_Step**に**BTS_Messaging_Constant**です。</span><span class="sxs-lookup"><span data-stu-id="7a9ce-111">In the Load Test Editor, rename the scenario **BTS_Messaging_Step** to **BTS_Messaging_Constant**.</span></span> <span data-ttu-id="7a9ce-112">直下にあるシナリオの名前が表示されます、**シナリオ**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="7a9ce-112">The scenario name is displayed directly under the **Scenarios** folder.</span></span>  
  
5.  <span data-ttu-id="7a9ce-113">値のままにして**テスト ミックス**と**ネットワーク ミックス**をクリックして選択が変更されていない**ステップ ロード パターン**です。</span><span class="sxs-lookup"><span data-stu-id="7a9ce-113">Leave the values for **Test Mix** and **Network Mix** unchanged but click to select **Step Load Pattern**.</span></span>  
  
6.  <span data-ttu-id="7a9ce-114">右クリック**ステップ ロード パターン**選択**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="7a9ce-114">Right-click **Step Load Pattern** and select **Properties**.</span></span>  
  
7.  <span data-ttu-id="7a9ce-115">**プロパティ**セクションの [**ロード パターン**] の横にドロップダウン リストをクリックして**パターン**からパターンを変更および**手順**に**定数**です。</span><span class="sxs-lookup"><span data-stu-id="7a9ce-115">In the **Properties** section, under **Load Pattern** click the dropdown list next to **Pattern** and change the Pattern from **Step** to **Constant**.</span></span>  
  
8.  <span data-ttu-id="7a9ce-116">**プロパティ**セクションの **パラメーター**の値を変更**ユーザー数の定数**をユーザーの数よりも若干小さい値に、ステップ ロード パターンテストが容認できないほど大きくなりすぎない (つまり、値、**数/秒あたりに受信した BizTalk:Messaging\Documents**が一貫しての値を超えるを開始した**BizTalk:Messaging\Documents 処理数/秒**の値、 **BizTalk:Message ボックス: 一般的な Counters\Spool Size** unbounded やすくが開始されました)。</span><span class="sxs-lookup"><span data-stu-id="7a9ce-116">In the **Properties** section, under **Parameters**, change the value for **Constant User Count** to a value slightly less than the number of users at which the Step Load Pattern test was becoming unsustainable (i.e. the value for the **BizTalk:Messaging\Documents received per/Sec** began to consistently exceed the value for **BizTalk:Messaging\Documents processed/Sec** and the value of the **BizTalk:Message Box:General Counters\Spool Size** began to increase unbounded).</span></span>  
  
9. <span data-ttu-id="7a9ce-117">下にある、**実行設定**フォルダーを右クリックして**Setting1 の実行 [アクティブ]** を選択し、**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="7a9ce-117">Under the **Run Settings** folder, right-click **Run Setting1 [Active]** and select **Properties**.</span></span>  
  
10. <span data-ttu-id="7a9ce-118">プロパティの一覧をスクロールして、**タイミング**セクションし、値を入力**実行継続時間**少なくとも 10 分間の (00: 10:00) ことを確認の値は、**サンプル レート**5 秒に設定されている (00: 00:05)。</span><span class="sxs-lookup"><span data-stu-id="7a9ce-118">Scroll down the list of properties to the **Timing** section and enter a value for **Run Duration** of at least 10 minutes (00:10:00) and verify that the value for **Sample Rate** is still set to 5 seconds (00:00:05).</span></span>  
  
11. <span data-ttu-id="7a9ce-119">テスト名 (例: BTS_Messaging_Constant) を右クリックして、ロード テストを開始し、**テストの実行**メニュー オプション。</span><span class="sxs-lookup"><span data-stu-id="7a9ce-119">Start the load test by right-clicking the test name (e.g. BTS_Messaging_Constant) and then click the **Run Test** menu option.</span></span>