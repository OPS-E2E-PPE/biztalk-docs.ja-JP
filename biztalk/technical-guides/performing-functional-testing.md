---
title: 機能テストの実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b9c8c95-5a25-4255-a4c2-e26c67b7a620
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e0f1736ddc0956de470ebdc1f3f1a6adaa2f8f94
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291340"
---
# <a name="performing-functional-testing"></a><span data-ttu-id="c8629-102">機能テストの実行</span><span class="sxs-lookup"><span data-stu-id="c8629-102">Performing Functional Testing</span></span>
<span data-ttu-id="c8629-103">機能テストを使用する特定の BizTalk アプリケーションのコンテキストで特定のエンド ツー エンド シナリオまたは特定のユース ケースをテストします。</span><span class="sxs-lookup"><span data-stu-id="c8629-103">You use functional testing to test a specific end-to-end scenario or a given use case in the context of a particular BizTalk application.</span></span> <span data-ttu-id="c8629-104">機能テストには、障害のパスを含む、特定のシナリオのすべての可能なパスがについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c8629-104">A functional test should cover all the possible paths through a given scenario, including the failure paths.</span></span> <span data-ttu-id="c8629-105">アプリケーションが適切に処理エラーの条件を使用することを確認するエラー パスを評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8629-105">Failure paths should be evaluated to ensure that the application deals with failure conditions appropriately.</span></span>  
  
 <span data-ttu-id="c8629-106">すべてのアイテム (オーケストレーション、カスタム パイプライン コンポーネントでは、カスタム アセンブリなど) を呼び出す必要があるし、もこれらのオブジェクトのすべてのコード分岐をテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8629-106">All the artifacts (such as orchestrations, custom pipeline components, and custom assemblies) should be invoked, and all the code branches through these objects should be tested as well.</span></span> <span data-ttu-id="c8629-107">メッセージがシステムを正しくフローすることを確認するメッセージの有効なすべての組み合わせを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8629-107">All the possible combinations of messages should be exercised to ensure that messages flow through the system correctly.</span></span> <span data-ttu-id="c8629-108">無効なメッセージは、エラーが発生した場合、予想される方法で、アプリケーションが反応するかどうかを確認し、オーケストレーションおよびカスタム コンポーネントのすべての例外ブロックに含まれるコードをテストするもテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8629-108">Invalid messages should be tested as well to make sure that the application reacts in the expected way in case of error and to test the code contained in all the exception blocks of orchestrations and custom components.</span></span>  
  
## <a name="automating-functional-testing"></a><span data-ttu-id="c8629-109">機能テストの自動化</span><span class="sxs-lookup"><span data-stu-id="c8629-109">Automating Functional Testing</span></span>  
 <span data-ttu-id="c8629-110">繰り返せることから、ようにし、人的エラーを回避されますが、高速にするように、機能テストを自動化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8629-110">You should automate functional testing so that it is fast, so that it can be repeated, and so that it will avoid human errors.</span></span> <span data-ttu-id="c8629-111">**BizUnit**デザイン迅速にテスト_ケースを開発者向けに設計された宣言型のテスト フレームワークです。</span><span class="sxs-lookup"><span data-stu-id="c8629-111">**BizUnit** is a declarative test framework designed to enable developers to rapidly design test cases.</span></span> <span data-ttu-id="c8629-112">実際には、XML のための BizUnit テスト_ケースと呼ばれる XML 構成ファイルでは、テストを実行する方法を定義するだけです。</span><span class="sxs-lookup"><span data-stu-id="c8629-112">In fact, an XML configuration file called BizUnit XML test case is enough to define how a test should be performed.</span></span> <span data-ttu-id="c8629-113">テストを実行する独自のカスタム ドライバーを作成することも簡単にご利用の詳細は**Visual Studio Unit Testing**または**NUnit**をホストし、テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="c8629-113">To run tests you can create your own custom driver or more easily leverage **Visual Studio Unit Testing** or **NUnit** to host and run your tests.</span></span>  
  
 <span data-ttu-id="c8629-114">すべての XML のための BizUnit テスト_ケースには、3 つのフェーズが含まれています。**TestSetup**、 **TestExecution**、および**TestCleanup**します。</span><span class="sxs-lookup"><span data-stu-id="c8629-114">Every BizUnit XML test case contains three phases: **TestSetup**, **TestExecution**, and **TestCleanup**.</span></span> <span data-ttu-id="c8629-115">これらの各フェーズは、0 個以上のテスト ステップを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c8629-115">Each of these phases can contain zero or more test steps.</span></span> <span data-ttu-id="c8629-116">各ステップは、作業単位を表し、特定のタスクを実行するように .NET クラスとして実装されます。</span><span class="sxs-lookup"><span data-stu-id="c8629-116">Each step represents a unit of work and is implemented as a .NET class designed to perform a certain task.</span></span> <span data-ttu-id="c8629-117">このフレームワークは、コンポーネントの豊富なセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="c8629-117">This framework provides a rich set of components.</span></span> <span data-ttu-id="c8629-118">ただし、特定の要件を満たすために特殊化されたコンポーネントを理解する必要がある場合、独自のカスタムのテスト手順コンポーネント記述できます。</span><span class="sxs-lookup"><span data-stu-id="c8629-118">If you need to realize specialized components to meet specific requirements, however, you can write your own custom test step components.</span></span> <span data-ttu-id="c8629-119">これらのツールの詳細については、次を参照してください。[テスト用ツール](~/technical-guides/tools-for-testing.md)します。</span><span class="sxs-lookup"><span data-stu-id="c8629-119">For more information about these tools, see [Tools for Testing](~/technical-guides/tools-for-testing.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c8629-120">、Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関する保証をいたしません。</span><span class="sxs-lookup"><span data-stu-id="c8629-120">Use of this tool is not supported by Microsoft, and Microsoft makes no guarantees about the suitability of this program.</span></span> <span data-ttu-id="c8629-121">このプログラムは、ユーザー自身の責任で使用してください。</span><span class="sxs-lookup"><span data-stu-id="c8629-121">Use of this program is entirely at your own risk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8629-122">参照</span><span class="sxs-lookup"><span data-stu-id="c8629-122">See Also</span></span>  
 [<span data-ttu-id="c8629-123">チェックリスト:運用準備のテスト</span><span class="sxs-lookup"><span data-stu-id="c8629-123">Checklist: Testing Operational Readiness</span></span>](../technical-guides/checklist-testing-operational-readiness.md)