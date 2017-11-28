---
title: "ポリシーをテストする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- testing, policies
- Business Rule Composer, testing
- Business Rule Composer, policies
- testing, Business Rule Composer
- policies, testing
ms.assetid: 122dee26-d1f1-49a6-a6d5-a9d3d861a66b
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7a0f8c0d63d14d5a529039a6e1c8af5b363cc9c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-test-policies"></a><span data-ttu-id="7e6e2-102">ポリシーをテストする方法</span><span class="sxs-lookup"><span data-stu-id="7e6e2-102">How to Test Policies</span></span>
<span data-ttu-id="7e6e2-103">ポリシーをテストするには、ルールを実行するためのファクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="7e6e2-103">To test a policy, you need facts on which the rules can be executed.</span></span> <span data-ttu-id="7e6e2-104">XML ドキュメント、またはポリシー テスターで指定するデータベース テーブル内で値を指定することにより、ファクトを追加できます。また、ファクト作成コンポーネントを使用して、.NET オブジェクトの配列をファクトとしてエンジンに提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="7e6e2-104">You can add facts by specifying values in XML documents or database tables that you will point to in the policy tester, or you can use a fact creator to supply to the engine an array of .NET objects as facts.</span></span> <span data-ttu-id="7e6e2-105">詳細については、次を参照してください。[ファクト作成コンポーネントを作成する](../core/how-to-create-a-fact-creator.md)です。</span><span class="sxs-lookup"><span data-stu-id="7e6e2-105">For more information, see [Creating a Fact Creator](../core/how-to-create-a-fact-creator.md).</span></span>  
  
### <a name="to-test-a-policy-in-the-business-rule-composer"></a><span data-ttu-id="7e6e2-106">ビジネス ルール作成ツールでポリシーをテストするには</span><span class="sxs-lookup"><span data-stu-id="7e6e2-106">To test a policy in the Business Rule Composer</span></span>  
  
1.  <span data-ttu-id="7e6e2-107">[ポリシー エクスプローラー] ウィンドウで、テストするポリシーのバージョンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e6e2-107">In the Policy Explorer window, click the policy version that you want to test.</span></span>  
  
2.  <span data-ttu-id="7e6e2-108">クリックして、**テスト ポリシー**メニュー バー ボタン (緑色の矢印)。</span><span class="sxs-lookup"><span data-stu-id="7e6e2-108">Click the **Test Policy** button (green arrow) on the menu bar.</span></span>  
  
     <span data-ttu-id="7e6e2-109">最上部のペインに、ポリシー ルールが参照するファクトの種類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e6e2-109">The top pane displays the fact types that the policy rules reference.</span></span>  
  
3.  <span data-ttu-id="7e6e2-110">ファクトのインスタンスを追加するには、クリックして、 **XML ドキュメント**または**データベース テーブル**ファクトの種類をクリックして**インスタンスの追加**です。</span><span class="sxs-lookup"><span data-stu-id="7e6e2-110">To add a fact instance, click an **XML Document** or **Database Table** fact type, and then click **Add Instance**.</span></span>  
  
4.  <span data-ttu-id="7e6e2-111">ファクトのインスタンスを削除する場合は、対応するファクトの種類をクリック**インスタンスの削除**です。</span><span class="sxs-lookup"><span data-stu-id="7e6e2-111">If you want to remove a fact instance, click the corresponding fact type, and then click **Remove Instance**.</span></span>  
  
5.  <span data-ttu-id="7e6e2-112">記述したファクト作成コンポーネントを追加する場合は、クリックして**追加**ファクト作成コンポーネントのペインでします。</span><span class="sxs-lookup"><span data-stu-id="7e6e2-112">If you want to add a fact creator that you have written, click **Add** in the fact creator pane.</span></span>  
  
6.  <span data-ttu-id="7e6e2-113">をクリックして**テスト**です。</span><span class="sxs-lookup"><span data-stu-id="7e6e2-113">Click **Test**.</span></span>  
  
     <span data-ttu-id="7e6e2-114">ポリシーのテストのトレース出力がテスト出力ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e6e2-114">The policy test trace output appears in the test output window.</span></span>  
  
7.  <span data-ttu-id="7e6e2-115">出力テキストを保存、クリア、選択、またはコピーする場合は、出力ウィンドウ内で右クリックします。</span><span class="sxs-lookup"><span data-stu-id="7e6e2-115">Right-click in the output window to save, clear, select, or copy the output text.</span></span>  
  
     ![](../core/media/ebiz-testpolicy.gif "ebiz_testpolicy")  
<span data-ttu-id="7e6e2-116">ポリシーのテストのためのファクトの選択</span><span class="sxs-lookup"><span data-stu-id="7e6e2-116">Selecting fact to test a policy</span></span>