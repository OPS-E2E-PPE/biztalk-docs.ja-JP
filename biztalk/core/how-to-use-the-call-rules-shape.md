---
title: ルール図形の呼び出しを使用する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Call Rules shape [Orchestration Designer], how to
- Call Rules shape [Orchestration Designer], configuring
- Call Rules shape [Orchestration Designer], policies
- policies, Call Rules shape [Orchestration Designer]
ms.assetid: e4bc8a2c-de7e-4e3a-81b8-12bcebb17d27
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c85badfaf22ff4fb6aebd9ed19c757faaa1f303c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006443"
---
# <a name="how-to-use-the-call-rules-shape"></a><span data-ttu-id="1a524-102">ルールの呼び出し図形の使用方法</span><span class="sxs-lookup"><span data-stu-id="1a524-102">How to Use the Call Rules Shape</span></span>
<span data-ttu-id="1a524-103">オーケストレーション デザイナーで使用することができます、**ルールの呼び出し**図形をビジネス ポリシーを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1a524-103">In Orchestration Designer, you can use the **Call Rules** shape to call a business policy.</span></span>  
  
### <a name="to-configure-the-call-rules-shape"></a><span data-ttu-id="1a524-104">ルールの呼び出し図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="1a524-104">To configure the Call Rules shape</span></span>  
  
1.  <span data-ttu-id="1a524-105">ツールボックス からの**BizTalk オーケストレーション** タブで、ドラッグ、**ルールの呼び出し**図形をオーケストレーション デザイン画面上の区分線にします。</span><span class="sxs-lookup"><span data-stu-id="1a524-105">From the Toolbox, in the **BizTalk Orchestrations** tab, drag the **Call Rules** shape onto a connecting line on the Orchestration Design Surface.</span></span>  
  
     <span data-ttu-id="1a524-106">- または -</span><span class="sxs-lookup"><span data-stu-id="1a524-106">—Or—</span></span>  
  
     <span data-ttu-id="1a524-107">区分線または図形を追加する図形のプレース ホルダーを右クリックするポイント**図形の挿入**をクリックしてコンテキスト メニューで、**ルールの呼び出し**です。</span><span class="sxs-lookup"><span data-stu-id="1a524-107">Right-click the connecting line or the shape placeholder where you want to add the shape, point to **Insert Shape** on the context menu, and then click **Call Rules**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1a524-108">BizTalk Server ではアトミックのスコープを挿入する必要はありません、**ルールの呼び出し**図形です。</span><span class="sxs-lookup"><span data-stu-id="1a524-108">In BizTalk Server, you do not need to have an atomic scope to insert a **Call Rules** shape.</span></span> <span data-ttu-id="1a524-109">ドラッグすることができます、**ルールの呼び出し**図形をツールボックスからオーケストレーション デザイン画面にします。</span><span class="sxs-lookup"><span data-stu-id="1a524-109">You can drag a **Call Rules** shape into the Orchestration Design Surface from the Toolbox.</span></span> <span data-ttu-id="1a524-110">ただし、BizTalk Server では、**ルールの呼び出し**を挿入しようとする場合、コンテキスト メニューにメニュー項目が無効な**ルールの呼び出し**アトミックのスコープを持たないオーケストレーション内の図形です。</span><span class="sxs-lookup"><span data-stu-id="1a524-110">However, in BizTalk Server, the **Call Rules** menu item is disabled in the context menu if you try to insert a **Call Rules** shape inside an orchestration that does not have an atomic scope.</span></span> <span data-ttu-id="1a524-111">これは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 製品における制限事項です。</span><span class="sxs-lookup"><span data-stu-id="1a524-111">This is a limitation with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] product.</span></span>  
  
2.  <span data-ttu-id="1a524-112">オーケストレーション デザイナーで、選択、**ルールの呼び出し**図形です。</span><span class="sxs-lookup"><span data-stu-id="1a524-112">In Orchestration Designer, select the **Call Rules** shape.</span></span>  
  
3.  <span data-ttu-id="1a524-113">表示する図形をダブルクリックして、 **CallRules ポリシーの構成** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="1a524-113">Double-click the shape to display the **CallRules policy configuration** dialog box.</span></span>  
  
4.  <span data-ttu-id="1a524-114">**呼び出すビジネス ポリシーの選択**ドロップダウン リストで、必要なポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="1a524-114">In the **Select the business policy you wish to call** drop-down list, select the policy you need.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1a524-115">ルールの呼び出しの構成は、ポリシーで使用される種類を決定する際、保存されている最新バージョンのポリシーを参照します。</span><span class="sxs-lookup"><span data-stu-id="1a524-115">Call Rules configuration will look at the latest saved version of a policy when determining the types used in the policy.</span></span> <span data-ttu-id="1a524-116">実行時に、展開されている最新バージョンのポリシーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="1a524-116">At run time, the latest deployed version of the policy will be used.</span></span>  
  
5.  <span data-ttu-id="1a524-117">**ポリシー パラメーターの指定**ボックスの一覧から変数を選択して、**パラメーター名**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="1a524-117">In the **Specify policy parameters** list box, select a variable from the **Parameter Name** property.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1a524-118">**ルールの呼び出し**図形は基本的に再構築する際、メッセージを使用する場合に、**構築**図形、さらに、失われるメッセージのコンテキスト プロパティを引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1a524-118">The **Call Rules** shape is essentially reconstructing the message, as if using a **Construct** shape, which in turn may cause context properties of the message to be lost.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1a524-119">BRE ポリシーへのパラメーターとしてメッセージまたは .NET 変数を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="1a524-119">You can specify a message or a .NET variable as a parameter to a BRE policy.</span></span> <span data-ttu-id="1a524-120">渡す、 **TypedXmlDocument**実際には、パラメーターとしてオーケストレーションで宣言されている対応するメッセージを指定します。</span><span class="sxs-lookup"><span data-stu-id="1a524-120">To pass a **TypedXmlDocument** fact, specify the corresponding message declared in the orchestration as a parameter.</span></span> <span data-ttu-id="1a524-121">.NET ファクトを渡すには、オーケストレーション内でパラメーターとして宣言済みの .NET 変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="1a524-121">To pass a .NET fact, specify a .NET variable declared in the orchestration as a parameter.</span></span> <span data-ttu-id="1a524-122">データベース ファクトを渡すは、型の .NET 変数を指定します。 **DataConnection**または**TypedDataTable**ポリシーへのパラメーターとして。</span><span class="sxs-lookup"><span data-stu-id="1a524-122">To pass a database fact, specify a .NET variable of type **DataConnection** or **TypedDataTable** as a parameter to the policy.</span></span>