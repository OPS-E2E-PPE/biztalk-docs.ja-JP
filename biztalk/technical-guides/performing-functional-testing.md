---
title: 機能テストを実行して |Microsoft ドキュメント
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
ms.openlocfilehash: f17c2701d6aa90393b8839bafc933bea2fba5746
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302322"
---
# <a name="performing-functional-testing"></a><span data-ttu-id="a171d-102">機能テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="a171d-102">Performing Functional Testing</span></span>
<span data-ttu-id="a171d-103">テストを使用する機能を特定の BizTalk アプリケーションのコンテキストで、特定のエンド ツー エンド シナリオまたは特定のユース ケースをテストします。</span><span class="sxs-lookup"><span data-stu-id="a171d-103">You use functional testing to test a specific end-to-end scenario or a given use case in the context of a particular BizTalk application.</span></span> <span data-ttu-id="a171d-104">機能テストには、エラーのパスを含む特定のシナリオのすべての可能なパスを取り扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a171d-104">A functional test should cover all the possible paths through a given scenario, including the failure paths.</span></span> <span data-ttu-id="a171d-105">エラー パスを評価して、アプリケーションが適切に処理エラー条件のことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a171d-105">Failure paths should be evaluated to ensure that the application deals with failure conditions appropriately.</span></span>  
  
 <span data-ttu-id="a171d-106">(オーケストレーション、カスタム パイプライン コンポーネントのカスタム アセンブリなど) のすべての成果物を呼び出す必要があります、およびこれらのオブジェクトのすべてのコード分岐をもテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a171d-106">All the artifacts (such as orchestrations, custom pipeline components, and custom assemblies) should be invoked, and all the code branches through these objects should be tested as well.</span></span> <span data-ttu-id="a171d-107">メッセージがシステムを通じて正しくフローすることを確認するメッセージのすべての可能な組み合わせを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a171d-107">All the possible combinations of messages should be exercised to ensure that messages flow through the system correctly.</span></span> <span data-ttu-id="a171d-108">無効なメッセージは、アプリケーションがエラーが発生した場合、予想される方法で動作することを確認し、オーケストレーションおよびカスタム コンポーネントのすべての例外ブロックに含まれるコードをテストするもテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a171d-108">Invalid messages should be tested as well to make sure that the application reacts in the expected way in case of error and to test the code contained in all the exception blocks of orchestrations and custom components.</span></span>  
  
## <a name="automating-functional-testing"></a><span data-ttu-id="a171d-109">機能テストの自動化</span><span class="sxs-lookup"><span data-stu-id="a171d-109">Automating Functional Testing</span></span>  
 <span data-ttu-id="a171d-110">高速繰り返せることから、ようにヒューマン エラーを回避することができるようにするように、機能テストを自動化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a171d-110">You should automate functional testing so that it is fast, so that it can be repeated, and so that it will avoid human errors.</span></span> <span data-ttu-id="a171d-111">**BizUnit**宣言型テスト フレームワークを開発者がデザイン急速にテスト_ケースを有効にするよう設計されています。</span><span class="sxs-lookup"><span data-stu-id="a171d-111">**BizUnit** is a declarative test framework designed to enable developers to rapidly design test cases.</span></span> <span data-ttu-id="a171d-112">実際には、BizUnit XML テスト_ケースと呼ばれる XML 構成ファイルでは、テストを実行する方法を定義するだけです。</span><span class="sxs-lookup"><span data-stu-id="a171d-112">In fact, an XML configuration file called BizUnit XML test case is enough to define how a test should be performed.</span></span> <span data-ttu-id="a171d-113">テストを実行する独自のカスタム ドライバーを作成することも簡単に活用詳細**Visual Studio 単体テスト**または**NUnit**ホストし、テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="a171d-113">To run tests you can create your own custom driver or more easily leverage **Visual Studio Unit Testing** or **NUnit** to host and run your tests.</span></span>  
  
 <span data-ttu-id="a171d-114">BizUnit XML のすべてのテスト_ケースには、3 つのフェーズが含まれています: **TestSetup**、 **TestExecution**、および**TestCleanup**です。</span><span class="sxs-lookup"><span data-stu-id="a171d-114">Every BizUnit XML test case contains three phases: **TestSetup**, **TestExecution**, and **TestCleanup**.</span></span> <span data-ttu-id="a171d-115">これらの各フェーズにより、0 個以上のテスト ステップが含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a171d-115">Each of these phases can contain zero or more test steps.</span></span> <span data-ttu-id="a171d-116">各手順では、作業の単位を表し、特定のタスクを実行するように .NET クラスとして実装します。</span><span class="sxs-lookup"><span data-stu-id="a171d-116">Each step represents a unit of work and is implemented as a .NET class designed to perform a certain task.</span></span> <span data-ttu-id="a171d-117">このフレームワークは、コンポーネントの機能豊富なセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="a171d-117">This framework provides a rich set of components.</span></span> <span data-ttu-id="a171d-118">ただしを特定の要件を満たすために特別なコンポーネントを実現する必要がある場合は、独自のカスタムのテスト ステップ コンポーネントを記述することができます。</span><span class="sxs-lookup"><span data-stu-id="a171d-118">If you need to realize specialized components to meet specific requirements, however, you can write your own custom test step components.</span></span> <span data-ttu-id="a171d-119">これらのツールの詳細については、次を参照してください。[テスト用ツール](~/technical-guides/tools-for-testing.md)です。</span><span class="sxs-lookup"><span data-stu-id="a171d-119">For more information about these tools, see [Tools for Testing](~/technical-guides/tools-for-testing.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a171d-120">、Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関して保証を行いません。</span><span class="sxs-lookup"><span data-stu-id="a171d-120">Use of this tool is not supported by Microsoft, and Microsoft makes no guarantees about the suitability of this program.</span></span> <span data-ttu-id="a171d-121">このプログラムは、ユーザー自身の責任で使用してください。</span><span class="sxs-lookup"><span data-stu-id="a171d-121">Use of this program is entirely at your own risk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a171d-122">参照</span><span class="sxs-lookup"><span data-stu-id="a171d-122">See Also</span></span>  
 [<span data-ttu-id="a171d-123">チェックリスト: テスト運用の準備</span><span class="sxs-lookup"><span data-stu-id="a171d-123">Checklist: Testing Operational Readiness</span></span>](../technical-guides/checklist-testing-operational-readiness.md)