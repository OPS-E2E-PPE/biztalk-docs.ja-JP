---
title: 手順 6:維持可能な最大のスループットを検証するための持続ロード パターン テストの実行 |Microsoft Docs
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
ms.openlocfilehash: 28b482c6202741353987a28d4a943154a933abbf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401214"
---
# <a name="step-6-perform-constant-load-pattern-tests-to-verify-maximum-sustainable-throughput"></a><span data-ttu-id="cab0d-102">手順 6:維持可能な最大のスループットを検証するための持続ロード パターン テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="cab0d-102">Step 6: Perform Constant Load Pattern Tests to Verify Maximum Sustainable Throughput</span></span>
<span data-ttu-id="cab0d-103">ロード Visual Studio 2010 を使用して、BizTalk Server ソリューションをテストするとき、」の説明に従って、概算最大持続可能なスループット (MST) のソリューションが決定したら、持続ロード パターン テストを実行する必要があります[手順 5。維持可能な最大のスループットを判断するステップ ロード パターン テストの実行](../technical-guides/step-5-complete-step-load-tests-to-determine-maximum-sustainable-throughput.md)します。</span><span class="sxs-lookup"><span data-stu-id="cab0d-103">When load testing a BizTalk Server solution using Visual Studio 2010, a constant load pattern test should be performed once the approximate Maximum Sustainable Throughput (MST) of the solution is determined as described in [Step 5: Perform Step Load Pattern Tests to Determine Maximum Sustainable Throughput](../technical-guides/step-5-complete-step-load-tests-to-determine-maximum-sustainable-throughput.md).</span></span> <span data-ttu-id="cab0d-104">これは、時間の経過と共に、MST が維持可能な実際にあることを確認し、今後は、BizTalk Server アプリケーションまたは環境に適用されるパフォーマンス チューニングの効果を評価する基準のロード テストを作成するために実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cab0d-104">This should be done to confirm that the MST is in fact sustainable over time and also so as to create a baseline load test moving forward to evaluate the effects of any performance tuning applied to the BizTalk Server application or environment.</span></span>  
  
## <a name="create-and-run-a-constant-load-pattern-test"></a><span data-ttu-id="cab0d-105">作成し、一定のロード パターン テストの実行</span><span class="sxs-lookup"><span data-stu-id="cab0d-105">Create and run a Constant Load Pattern Test</span></span>  
 <span data-ttu-id="cab0d-106">"BTS_Messaging_"BTS_Messaging_Step.loadtest"ステップ ロード パターン テストを保存するだけでは、同じテスト ミックス、カウンター セット、およびステップ ロード パターン テストで使用されるカウンター セットの割り当てを使用する定数のロード パターン テストを作成する最も簡単な方法Constant.loadtest"と"BTS_Messaging_Constant.loadtest"をいくつか変更し、行います。</span><span class="sxs-lookup"><span data-stu-id="cab0d-106">The easiest way to create a Constant Load Pattern test that uses the same Test Mix, Counter Sets, and Counter Set Mappings used by the Step Load Pattern test is to simply save the Step Load Pattern test “BTS_Messaging_Step.loadtest” as “BTS_Messaging_Constant.loadtest” and then make some changes to “BTS_Messaging_Constant.loadtest”.</span></span> <span data-ttu-id="cab0d-107">フォローされている定数のロード パターンを作成する手順をテストでは、既存のテストのステップ ロード パターンに基づきます。</span><span class="sxs-lookup"><span data-stu-id="cab0d-107">Follow these steps to create a Constant Load Pattern test that is based upon the existing Step Load Pattern test:</span></span>  
  
1.  <span data-ttu-id="cab0d-108">開いていない場合は、BTS_Messaging_Step.loadtest を開きます。</span><span class="sxs-lookup"><span data-stu-id="cab0d-108">Open BTS_Messaging_Step.loadtest if it is not already open.</span></span>  
  
2.  <span data-ttu-id="cab0d-109">をクリックして**ファイル**選択**LoadTests\BTS_Messaging_Step.loadtest に名前を付けて**します。</span><span class="sxs-lookup"><span data-stu-id="cab0d-109">Click **File** and select **Save LoadTests\BTS_Messaging_Step.loadtest As**.</span></span>  
  
3.  <span data-ttu-id="cab0d-110">**ファイルに名前を付けて**] ダイアログ ボックスの横に**ファイル名**C:\Projects\LoadTest\BTSLoad\LoadTests\BTS_Messaging_Constant.loadtest を入力し、[クリックして**保存**します。</span><span class="sxs-lookup"><span data-stu-id="cab0d-110">In the **Save File As** dialog box, next to **File name**, enter C:\Projects\LoadTest\BTSLoad\LoadTests\BTS_Messaging_Constant.loadtest and then click **Save**.</span></span>  
  
4.  <span data-ttu-id="cab0d-111">ロード テスト エディターで、シナリオの名前を変更**BTS_Messaging_Step**に**BTS_Messaging_Constant**します。</span><span class="sxs-lookup"><span data-stu-id="cab0d-111">In the Load Test Editor, rename the scenario **BTS_Messaging_Step** to **BTS_Messaging_Constant**.</span></span> <span data-ttu-id="cab0d-112">直下にあるシナリオの名前が表示されます、**シナリオ**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="cab0d-112">The scenario name is displayed directly under the **Scenarios** folder.</span></span>  
  
5.  <span data-ttu-id="cab0d-113">値のままに**テスト ミックス**と**ネットワーク ミックス**をクリックして選択が変更されていない**ステップ ロード パターン**します。</span><span class="sxs-lookup"><span data-stu-id="cab0d-113">Leave the values for **Test Mix** and **Network Mix** unchanged but click to select **Step Load Pattern**.</span></span>  
  
6.  <span data-ttu-id="cab0d-114">右クリック**ステップ ロード パターン**選択**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="cab0d-114">Right-click **Step Load Pattern** and select **Properties**.</span></span>  
  
7.  <span data-ttu-id="cab0d-115">**プロパティ**セクションの**ロード パターン**横のドロップダウン リストをクリックして**パターン**からパターンを変更および**手順**に**定数**します。</span><span class="sxs-lookup"><span data-stu-id="cab0d-115">In the **Properties** section, under **Load Pattern** click the dropdown list next to **Pattern** and change the Pattern from **Step** to **Constant**.</span></span>  
  
8.  <span data-ttu-id="cab0d-116">**プロパティ**セクションの**パラメーター**の値を変更**持続ユーザー カウント**をユーザーの数よりも若干小さい値に、ステップ ロード パターンテストが大きすぎるになっていました (つまりの値、**数/秒あたりに受信した BizTalk:Messaging\Documents**が一貫しての値を超えるを開始した**BizTalk:Messaging\Documents 処理数/秒**の値、 **BizTalk:Message ボックス: 一般的な Counters\Spool サイズ**unbounded 増え始め)。</span><span class="sxs-lookup"><span data-stu-id="cab0d-116">In the **Properties** section, under **Parameters**, change the value for **Constant User Count** to a value slightly less than the number of users at which the Step Load Pattern test was becoming unsustainable (i.e. the value for the **BizTalk:Messaging\Documents received per/Sec** began to consistently exceed the value for **BizTalk:Messaging\Documents processed/Sec** and the value of the **BizTalk:Message Box:General Counters\Spool Size** began to increase unbounded).</span></span>  
  
9. <span data-ttu-id="cab0d-117">**実行設定**フォルダーを右クリックし**Setting1 の実行 [Active]** 選択と**プロパティ**。</span><span class="sxs-lookup"><span data-stu-id="cab0d-117">Under the **Run Settings** folder, right-click **Run Setting1 [Active]** and select **Properties**.</span></span>  
  
10. <span data-ttu-id="cab0d-118">プロパティの一覧をスクロールして、**タイミング**セクションの値を入力して**実行継続時間**少なくとも 10 分間の (00: 10:00) ことを確認しますの値は、**サンプル レート**5 秒に設定されているが (00: 00:05)。</span><span class="sxs-lookup"><span data-stu-id="cab0d-118">Scroll down the list of properties to the **Timing** section and enter a value for **Run Duration** of at least 10 minutes (00:10:00) and verify that the value for **Sample Rate** is still set to 5 seconds (00:00:05).</span></span>  
  
11. <span data-ttu-id="cab0d-119">テスト名 (例: BTS_Messaging_Constant) を右クリックして、ロード テストを開始し、**テストの実行**メニュー オプション。</span><span class="sxs-lookup"><span data-stu-id="cab0d-119">Start the load test by right-clicking the test name (e.g. BTS_Messaging_Constant) and then click the **Run Test** menu option.</span></span>