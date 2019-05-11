---
title: ルール図形の呼び出しを使用する方法 |Microsoft Docs
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
ms.openlocfilehash: f9cf784eba26f93e6634863d02d36a4bb2e01c38
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333258"
---
# <a name="how-to-use-the-call-rules-shape"></a><span data-ttu-id="0ad38-102">ルールの呼び出し図形を使用する方法</span><span class="sxs-lookup"><span data-stu-id="0ad38-102">How to Use the Call Rules Shape</span></span>
<span data-ttu-id="0ad38-103">オーケストレーション デザイナーで使用することができます、**ルールの呼び出し**図形を呼び出すビジネス ポリシー。</span><span class="sxs-lookup"><span data-stu-id="0ad38-103">In Orchestration Designer, you can use the **Call Rules** shape to call a business policy.</span></span>  
  
### <a name="to-configure-the-call-rules-shape"></a><span data-ttu-id="0ad38-104">ルールの呼び出し図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="0ad38-104">To configure the Call Rules shape</span></span>  
  
1. <span data-ttu-id="0ad38-105">ツールボックスで、 **BizTalk オーケストレーション** タブで、ドラッグ、**ルールの呼び出し**図形をオーケストレーション デザイン画面上の区分線にします。</span><span class="sxs-lookup"><span data-stu-id="0ad38-105">From the Toolbox, in the **BizTalk Orchestrations** tab, drag the **Call Rules** shape onto a connecting line on the Orchestration Design Surface.</span></span>  
  
    <span data-ttu-id="0ad38-106">- または -</span><span class="sxs-lookup"><span data-stu-id="0ad38-106">—Or—</span></span>  
  
    <span data-ttu-id="0ad38-107">区分線または図形を追加する図形のプレース ホルダーを右クリックして をポイント**図形の挿入** をクリックし、コンテキスト メニューで**ルールの呼び出し**します。</span><span class="sxs-lookup"><span data-stu-id="0ad38-107">Right-click the connecting line or the shape placeholder where you want to add the shape, point to **Insert Shape** on the context menu, and then click **Call Rules**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="0ad38-108">BizTalk Server では挿入するアトミックのスコープを持つ必要はありません、**ルールの呼び出し**図形。</span><span class="sxs-lookup"><span data-stu-id="0ad38-108">In BizTalk Server, you do not need to have an atomic scope to insert a **Call Rules** shape.</span></span> <span data-ttu-id="0ad38-109">ドラッグすることができます、**ルールの呼び出し**図形をツールボックスからオーケストレーション デザイン画面にします。</span><span class="sxs-lookup"><span data-stu-id="0ad38-109">You can drag a **Call Rules** shape into the Orchestration Design Surface from the Toolbox.</span></span> <span data-ttu-id="0ad38-110">ただし、BizTalk Server で、**ルールの呼び出し**を挿入しようとする場合、コンテキスト メニューにメニュー項目が無効です、**ルールの呼び出し**アトミックのスコープを持たないオーケストレーション内の図形。</span><span class="sxs-lookup"><span data-stu-id="0ad38-110">However, in BizTalk Server, the **Call Rules** menu item is disabled in the context menu if you try to insert a **Call Rules** shape inside an orchestration that does not have an atomic scope.</span></span> <span data-ttu-id="0ad38-111">これは、使用制限、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]製品です。</span><span class="sxs-lookup"><span data-stu-id="0ad38-111">This is a limitation with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] product.</span></span>  
  
2. <span data-ttu-id="0ad38-112">オーケストレーション デザイナーで、選択、**ルールの呼び出し**図形。</span><span class="sxs-lookup"><span data-stu-id="0ad38-112">In Orchestration Designer, select the **Call Rules** shape.</span></span>  
  
3. <span data-ttu-id="0ad38-113">表示する図形をダブルクリックして、 **CallRules ポリシーの構成** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="0ad38-113">Double-click the shape to display the **CallRules policy configuration** dialog box.</span></span>  
  
4. <span data-ttu-id="0ad38-114">**呼び出すビジネス ポリシーの選択**ドロップダウン リストで、必要なポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="0ad38-114">In the **Select the business policy you wish to call** drop-down list, select the policy you need.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="0ad38-115">ポリシーで使用される型を決定するときに、ポリシーの保存されている最新のバージョンの呼び出し規則の構成になります。</span><span class="sxs-lookup"><span data-stu-id="0ad38-115">Call Rules configuration will look at the latest saved version of a policy when determining the types used in the policy.</span></span> <span data-ttu-id="0ad38-116">実行時に、ポリシーの展開された最新のバージョンが使用します。</span><span class="sxs-lookup"><span data-stu-id="0ad38-116">At run time, the latest deployed version of the policy will be used.</span></span>  
  
5. <span data-ttu-id="0ad38-117">**ポリシー パラメーターの指定**リスト ボックスから変数を選択して、**パラメーター名**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="0ad38-117">In the **Specify policy parameters** list box, select a variable from the **Parameter Name** property.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="0ad38-118">**ルールの呼び出し**図形は基本的に再構築する際、メッセージを使用した場合、**構築**図形、失われたメッセージのコンテキスト プロパティがさらに可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0ad38-118">The **Call Rules** shape is essentially reconstructing the message, as if using a **Construct** shape, which in turn may cause context properties of the message to be lost.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="0ad38-119">BRE ポリシーのパラメーターとしては、メッセージまたは .NET 変数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="0ad38-119">You can specify a message or a .NET variable as a parameter to a BRE policy.</span></span> <span data-ttu-id="0ad38-120">渡す、 **TypedXmlDocument**実際には、パラメーターとしてオーケストレーションで宣言されている対応するメッセージを指定します。</span><span class="sxs-lookup"><span data-stu-id="0ad38-120">To pass a **TypedXmlDocument** fact, specify the corresponding message declared in the orchestration as a parameter.</span></span> <span data-ttu-id="0ad38-121">.NET ファクトを渡すには、パラメーターとしてオーケストレーションで宣言されている .NET 変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="0ad38-121">To pass a .NET fact, specify a .NET variable declared in the orchestration as a parameter.</span></span> <span data-ttu-id="0ad38-122">型の .NET 変数を指定すると、データベース ファクトを渡すため**DataConnection**または**TypedDataTable**ポリシーへのパラメーターとして。</span><span class="sxs-lookup"><span data-stu-id="0ad38-122">To pass a database fact, specify a .NET variable of type **DataConnection** or **TypedDataTable** as a parameter to the policy.</span></span>