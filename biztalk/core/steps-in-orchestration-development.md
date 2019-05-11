---
title: オーケストレーションの開発手順 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- designing, orchestrations
- orchestrations, designing
- orchestrations, creating
- creating, orchestrations
- Copy Local property
ms.assetid: 556b1e6c-63a6-4805-a0a5-e555f198fe4e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 062cff21e067f9e7139c849cf0dd73af5eed1748
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244173"
---
# <a name="steps-in-orchestration-development"></a><span data-ttu-id="cf8d1-102">オーケストレーションの開発手順</span><span class="sxs-lookup"><span data-stu-id="cf8d1-102">Steps in Orchestration Development</span></span>
<span data-ttu-id="cf8d1-103">オーケストレーションを開発するには、通常、次の基本的な操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="cf8d1-103">To develop an orchestration, you typically perform the following basic actions:</span></span>  
  
-   <span data-ttu-id="cf8d1-104">ビジネス プロセスを表す図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="cf8d1-104">Add shapes to represent your business processes.</span></span>  
  
     <span data-ttu-id="cf8d1-105">オーケストレーション デザイナーは、さまざまなアクションまたは他の抽象化を表すために使用できる図形のツールボックスを提供します。</span><span class="sxs-lookup"><span data-stu-id="cf8d1-105">Orchestration Designer provides you with a toolbox of shapes that can be used to represent different actions or other abstractions.</span></span> <span data-ttu-id="cf8d1-106">詳細については、次を参照してください。[オーケストレーション図形](../core/orchestration-shapes.md)します。</span><span class="sxs-lookup"><span data-stu-id="cf8d1-106">For more information, see [Orchestration Shapes](../core/orchestration-shapes.md).</span></span>  
  
-   <span data-ttu-id="cf8d1-107">メッセージの形式を記述するスキーマを定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8d1-107">Define schemas to describe the format of your messages.</span></span>  
  
     <span data-ttu-id="cf8d1-108">BizTalk エディターでスキーマを定義できます。</span><span class="sxs-lookup"><span data-stu-id="cf8d1-108">You can define schemas with BizTalk Editor.</span></span> <span data-ttu-id="cf8d1-109">詳細については、次を参照してください。[の XML メッセージ スキーマを作成する方法](../core/how-to-create-schemas-for-xml-messages.md)します。</span><span class="sxs-lookup"><span data-stu-id="cf8d1-109">For more information, see [How to Create Schemas for XML Messages](../core/how-to-create-schemas-for-xml-messages.md).</span></span>  
  
-   <span data-ttu-id="cf8d1-110">使用されるメッセージの送信し、受信ポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="cf8d1-110">Define ports through which messages are sent and received.</span></span>  
  
     <span data-ttu-id="cf8d1-111">メッセージの送信し、受信方法と場所を指定するポートを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="cf8d1-111">You can define ports to specify how and where messages are sent and received.</span></span> <span data-ttu-id="cf8d1-112">詳細については、次を参照してください。[オーケストレーションで使用するポート](../core/using-ports-in-orchestrations.md)します。</span><span class="sxs-lookup"><span data-stu-id="cf8d1-112">For more information, see [Using Ports in Orchestrations](../core/using-ports-in-orchestrations.md).</span></span>  
  
-   <span data-ttu-id="cf8d1-113">バインド**送信**と**受信**図形をポート。</span><span class="sxs-lookup"><span data-stu-id="cf8d1-113">Bind **Send** and **Receive** shapes to ports.</span></span>  
  
     <span data-ttu-id="cf8d1-114">接続することができます、**送信**と**受信**図形をポートと、それらを使用するポート操作を指定します。</span><span class="sxs-lookup"><span data-stu-id="cf8d1-114">You can connect your **Send** and **Receive** shapes to ports and specify the port operations that they use.</span></span> <span data-ttu-id="cf8d1-115">詳細については、次を参照してください。[送信図形を構成する方法](../core/how-to-configure-the-send-shape.md)します。</span><span class="sxs-lookup"><span data-stu-id="cf8d1-115">For more information, see [How to Configure the Send Shape](../core/how-to-configure-the-send-shape.md).</span></span> <span data-ttu-id="cf8d1-116">参照してください[受信図形を構成する方法](../core/how-to-configure-the-receive-shape.md)します。</span><span class="sxs-lookup"><span data-stu-id="cf8d1-116">Also see [How to Configure the Receive Shape](../core/how-to-configure-the-receive-shape.md).</span></span>  
  
-   <span data-ttu-id="cf8d1-117">割り当てまたはメッセージの間でデータを変換します。</span><span class="sxs-lookup"><span data-stu-id="cf8d1-117">Assign or transform data between messages.</span></span>  
  
     <span data-ttu-id="cf8d1-118">使用することができます、**メッセージの構築**図形のメッセージの値を割り当てるか、メッセージの変換。</span><span class="sxs-lookup"><span data-stu-id="cf8d1-118">You can use the **Construct Message** shape to assign message values or do message transformations.</span></span> <span data-ttu-id="cf8d1-119">詳細については、次を参照してください。[メッセージの構築](../core/constructing-messages.md)します。</span><span class="sxs-lookup"><span data-stu-id="cf8d1-119">For more information, see [Constructing Messages](../core/constructing-messages.md).</span></span>  
  
-   <span data-ttu-id="cf8d1-120">書き込みまたはオーケストレーション内で作業する参照として追加したい場合がありますすべてのカスタム コンポーネントを特定します。</span><span class="sxs-lookup"><span data-stu-id="cf8d1-120">Identify any custom components that you might want to write or add as reference to work within your orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf8d1-121">場合、**ローカル コピー**参照アセンブリのプロパティに設定されて**True**オーケストレーション追加された参照が行われた後に、外部のアセンブリに加えられた変更を取得できませんBizTalk プロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="cf8d1-121">If the **Copy Local** property of the referenced assembly is set to **True**, Orchestration will not be able to pick up any changes made to the external assembly after the initial add reference takes place in BizTalk project.</span></span>  
  
-   <span data-ttu-id="cf8d1-122">定義し、実行中のオーケストレーション内のデータを管理するオーケストレーション変数を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="cf8d1-122">Define and assign orchestration variables to manage data in your running orchestration.</span></span>  
  
     <span data-ttu-id="cf8d1-123">オーケストレーションの種類 ウィンドウで、変数 フォルダーを使用するには、オーケストレーションの変数を割り当てるし、さまざまな図形で、変数を使用する式を編集するのに BizTalk 式エディタを宣言します。</span><span class="sxs-lookup"><span data-stu-id="cf8d1-123">You can use the Variables folder in the Orchestration View window to declare your orchestration variables, and BizTalk Expression Editor to edit expressions that assign and use the variables in various shapes.</span></span> <span data-ttu-id="cf8d1-124">詳細については、次を参照してください。 [xlang-s データ型](../core/xlang-s-data-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="cf8d1-124">For more information, see [XLANG-s Data Types](../core/xlang-s-data-types.md).</span></span>  
  
-   <span data-ttu-id="cf8d1-125">完全を期すのためにテストするオーケストレーションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="cf8d1-125">Build your orchestration to test it for completeness.</span></span>  
  
     <span data-ttu-id="cf8d1-126">プロジェクトまたはそれを含んでいるソリューションをコンパイルするときに、オーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="cf8d1-126">You build your orchestration when you compile the project or solution that contains it.</span></span> <span data-ttu-id="cf8d1-127">詳細については、次を参照してください。[オーケストレーションのビルド方法](../core/how-to-build-orchestrations.md)します。</span><span class="sxs-lookup"><span data-stu-id="cf8d1-127">For more information, see [How to Build Orchestrations](../core/how-to-build-orchestrations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf8d1-128">参照</span><span class="sxs-lookup"><span data-stu-id="cf8d1-128">See Also</span></span>  
 <span data-ttu-id="cf8d1-129">[ビルドとオーケストレーションの実行](../core/building-and-running-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="cf8d1-129">[Building and Running Orchestrations](../core/building-and-running-orchestrations.md) </span></span>  
 <span data-ttu-id="cf8d1-130">[オーケストレーションの管理](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="cf8d1-130">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 [<span data-ttu-id="cf8d1-131">オーケストレーション デザイナーでのオーケストレーションの作成</span><span class="sxs-lookup"><span data-stu-id="cf8d1-131">Creating Orchestrations Using Orchestration Designer</span></span>](../core/creating-orchestrations-using-orchestration-designer.md)