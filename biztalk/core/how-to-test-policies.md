---
title: ポリシーをテストする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing, policies
- Business Rule Composer, testing
- Business Rule Composer, policies
- testing, Business Rule Composer
- policies, testing
ms.assetid: 122dee26-d1f1-49a6-a6d5-a9d3d861a66b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49c682645a534f43476244fcda26453944048168
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383732"
---
# <a name="how-to-test-policies"></a><span data-ttu-id="5f393-102">ポリシーをテストする方法</span><span class="sxs-lookup"><span data-stu-id="5f393-102">How to Test Policies</span></span>
<span data-ttu-id="5f393-103">ポリシーをテストするには、ファクトがルールを実行できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f393-103">To test a policy, you need facts on which the rules can be executed.</span></span> <span data-ttu-id="5f393-104">ファクトを追加するには XML ドキュメントで値を指定またはファクトとして .NET オブジェクトの配列をエンジンに提供するには、ポリシー テスターをポイントはデータベース テーブルがファクト作成コンポーネントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5f393-104">You can add facts by specifying values in XML documents or database tables that you will point to in the policy tester, or you can use a fact creator to supply to the engine an array of .NET objects as facts.</span></span> <span data-ttu-id="5f393-105">詳細については、次を参照してください。[ファクト作成コンポーネントを作成する](../core/how-to-create-a-fact-creator.md)します。</span><span class="sxs-lookup"><span data-stu-id="5f393-105">For more information, see [Creating a Fact Creator](../core/how-to-create-a-fact-creator.md).</span></span>  
  
### <a name="to-test-a-policy-in-the-business-rule-composer"></a><span data-ttu-id="5f393-106">ビジネス ルール作成ツールでポリシーをテストするには</span><span class="sxs-lookup"><span data-stu-id="5f393-106">To test a policy in the Business Rule Composer</span></span>  
  
1.  <span data-ttu-id="5f393-107">ポリシー エクスプ ローラー ウィンドウで、テストするポリシーのバージョンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f393-107">In the Policy Explorer window, click the policy version that you want to test.</span></span>  
  
2.  <span data-ttu-id="5f393-108">をクリックして、**ポリシーのテスト**メニュー バーのボタン (緑色の矢印)。</span><span class="sxs-lookup"><span data-stu-id="5f393-108">Click the **Test Policy** button (green arrow) on the menu bar.</span></span>  
  
     <span data-ttu-id="5f393-109">上部のペインには、ポリシーのルールを参照するファクトの種類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5f393-109">The top pane displays the fact types that the policy rules reference.</span></span>  
  
3.  <span data-ttu-id="5f393-110">ファクトのインスタンスを追加するには、クリックして、 **XML ドキュメント**または**データベース テーブル**ファクトの種類をクリック**インスタンスの追加**します。</span><span class="sxs-lookup"><span data-stu-id="5f393-110">To add a fact instance, click an **XML Document** or **Database Table** fact type, and then click **Add Instance**.</span></span>  
  
4.  <span data-ttu-id="5f393-111">ファクトのインスタンスを削除する場合、対応するファクトの種類をクリックします。 をクリック**インスタンスの削除**します。</span><span class="sxs-lookup"><span data-stu-id="5f393-111">If you want to remove a fact instance, click the corresponding fact type, and then click **Remove Instance**.</span></span>  
  
5.  <span data-ttu-id="5f393-112">記述したファクト作成コンポーネントを追加する場合は、クリックして**追加**ファクト作成コンポーネントのペインでします。</span><span class="sxs-lookup"><span data-stu-id="5f393-112">If you want to add a fact creator that you have written, click **Add** in the fact creator pane.</span></span>  
  
6.  <span data-ttu-id="5f393-113">クリックして**テスト**します。</span><span class="sxs-lookup"><span data-stu-id="5f393-113">Click **Test**.</span></span>  
  
     <span data-ttu-id="5f393-114">ポリシー テストのトレース出力は、テスト出力ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5f393-114">The policy test trace output appears in the test output window.</span></span>  
  
7.  <span data-ttu-id="5f393-115">保存、クリア、選択、出力ウィンドウで右クリックするか、出力のテキストをコピーします。</span><span class="sxs-lookup"><span data-stu-id="5f393-115">Right-click in the output window to save, clear, select, or copy the output text.</span></span>  
  
     <span data-ttu-id="5f393-116">![](../core/media/ebiz-testpolicy.gif "ebiz_testpolicy")</span><span class="sxs-lookup"><span data-stu-id="5f393-116">![](../core/media/ebiz-testpolicy.gif "ebiz_testpolicy")</span></span>  
<span data-ttu-id="5f393-117">ポリシーをテストするファクトの選択</span><span class="sxs-lookup"><span data-stu-id="5f393-117">Selecting fact to test a policy</span></span>