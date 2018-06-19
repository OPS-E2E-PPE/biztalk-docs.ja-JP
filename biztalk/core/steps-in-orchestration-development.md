---
title: オーケストレーションの開発手順 |Microsoft ドキュメント
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
ms.openlocfilehash: 3fd0a19754871a6e736365e622513b193dcbf06a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277394"
---
# <a name="steps-in-orchestration-development"></a><span data-ttu-id="78bc6-102">オーケストレーションの開発手順</span><span class="sxs-lookup"><span data-stu-id="78bc6-102">Steps in Orchestration Development</span></span>
<span data-ttu-id="78bc6-103">オーケストレーションを開発するには、通常、次のような手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="78bc6-103">To develop an orchestration, you typically perform the following basic actions:</span></span>  
  
-   <span data-ttu-id="78bc6-104">目的のビジネス プロセスを表す図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="78bc6-104">Add shapes to represent your business processes.</span></span>  
  
     <span data-ttu-id="78bc6-105">オーケストレーション デザイナーには、各種のアクションやその他の抽象化された概念を表す図形がツールボックスとして用意されています。</span><span class="sxs-lookup"><span data-stu-id="78bc6-105">Orchestration Designer provides you with a toolbox of shapes that can be used to represent different actions or other abstractions.</span></span> <span data-ttu-id="78bc6-106">詳細については、次を参照してください。[オーケストレーション図形](../core/orchestration-shapes.md)です。</span><span class="sxs-lookup"><span data-stu-id="78bc6-106">For more information, see [Orchestration Shapes](../core/orchestration-shapes.md).</span></span>  
  
-   <span data-ttu-id="78bc6-107">メッセージの形式が記述されたスキーマを定義します。</span><span class="sxs-lookup"><span data-stu-id="78bc6-107">Define schemas to describe the format of your messages.</span></span>  
  
     <span data-ttu-id="78bc6-108">スキーマは、BizTalk エディターを使用して定義できます。</span><span class="sxs-lookup"><span data-stu-id="78bc6-108">You can define schemas with BizTalk Editor.</span></span> <span data-ttu-id="78bc6-109">詳細については、次を参照してください。[の XML メッセージ スキーマを作成する方法](../core/how-to-create-schemas-for-xml-messages.md)です。</span><span class="sxs-lookup"><span data-stu-id="78bc6-109">For more information, see [How to Create Schemas for XML Messages](../core/how-to-create-schemas-for-xml-messages.md).</span></span>  
  
-   <span data-ttu-id="78bc6-110">メッセージの送受信に使用するポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="78bc6-110">Define ports through which messages are sent and received.</span></span>  
  
     <span data-ttu-id="78bc6-111">ポートを定義することにより、メッセージの送受信方法と送受信場所を指定できます。</span><span class="sxs-lookup"><span data-stu-id="78bc6-111">You can define ports to specify how and where messages are sent and received.</span></span> <span data-ttu-id="78bc6-112">詳細については、次を参照してください。[オーケストレーションで使用するポート](../core/using-ports-in-orchestrations.md)です。</span><span class="sxs-lookup"><span data-stu-id="78bc6-112">For more information, see [Using Ports in Orchestrations](../core/using-ports-in-orchestrations.md).</span></span>  
  
-   <span data-ttu-id="78bc6-113">バインド**送信**と**受信**図形をポートです。</span><span class="sxs-lookup"><span data-stu-id="78bc6-113">Bind **Send** and **Receive** shapes to ports.</span></span>  
  
     <span data-ttu-id="78bc6-114">接続することができます、**送信**と**受信**図形をポートおよびそれらを使用するポート操作を指定します。</span><span class="sxs-lookup"><span data-stu-id="78bc6-114">You can connect your **Send** and **Receive** shapes to ports and specify the port operations that they use.</span></span> <span data-ttu-id="78bc6-115">詳細については、次を参照してください。[送信図形を構成する方法](../core/how-to-configure-the-send-shape.md)です。</span><span class="sxs-lookup"><span data-stu-id="78bc6-115">For more information, see [How to Configure the Send Shape](../core/how-to-configure-the-send-shape.md).</span></span> <span data-ttu-id="78bc6-116">参照してください[受信図形を構成する方法](../core/how-to-configure-the-receive-shape.md)です。</span><span class="sxs-lookup"><span data-stu-id="78bc6-116">Also see [How to Configure the Receive Shape](../core/how-to-configure-the-receive-shape.md).</span></span>  
  
-   <span data-ttu-id="78bc6-117">メッセージへのデータの割り当てや、メッセージ間の変換を行います。</span><span class="sxs-lookup"><span data-stu-id="78bc6-117">Assign or transform data between messages.</span></span>  
  
     <span data-ttu-id="78bc6-118">使用することができます、**メッセージの構築**図形のメッセージの値を割り当てるか、メッセージの変換。</span><span class="sxs-lookup"><span data-stu-id="78bc6-118">You can use the **Construct Message** shape to assign message values or do message transformations.</span></span> <span data-ttu-id="78bc6-119">詳細については、次を参照してください。[メッセージの構築](../core/constructing-messages.md)です。</span><span class="sxs-lookup"><span data-stu-id="78bc6-119">For more information, see [Constructing Messages](../core/constructing-messages.md).</span></span>  
  
-   <span data-ttu-id="78bc6-120">オーケストレーションで使用するために、作成する必要のあるカスタム コンポーネント、または参照として追加する必要のあるカスタム コンポーネントを明確にしておきます。</span><span class="sxs-lookup"><span data-stu-id="78bc6-120">Identify any custom components that you might want to write or add as reference to work within your orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="78bc6-121">場合、**ローカル コピー**参照アセンブリのプロパティに設定されて**True**オーケストレーションでは、参照の初期の追加が行われた後に、外部アセンブリに加えられた変更を取得できませんBizTalk プロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="78bc6-121">If the **Copy Local** property of the referenced assembly is set to **True**, Orchestration will not be able to pick up any changes made to the external assembly after the initial add reference takes place in BizTalk project.</span></span>  
  
-   <span data-ttu-id="78bc6-122">実行中のオーケストレーションでデータを管理するための変数を定義し、割り当てます。</span><span class="sxs-lookup"><span data-stu-id="78bc6-122">Define and assign orchestration variables to manage data in your running orchestration.</span></span>  
  
     <span data-ttu-id="78bc6-123">オーケストレーションの変数を宣言するには、[オーケストレーションの種類] ウィンドウの [変数] フォルダーを使用します。また、各種図形において変数が使われた式を編集するには、BizTalk 式エディターを使用します。</span><span class="sxs-lookup"><span data-stu-id="78bc6-123">You can use the Variables folder in the Orchestration View window to declare your orchestration variables, and BizTalk Expression Editor to edit expressions that assign and use the variables in various shapes.</span></span> <span data-ttu-id="78bc6-124">詳細については、次を参照してください。 [XLANG s データ型](../core/xlang-s-data-types.md)です。</span><span class="sxs-lookup"><span data-stu-id="78bc6-124">For more information, see [XLANG-s Data Types](../core/xlang-s-data-types.md).</span></span>  
  
-   <span data-ttu-id="78bc6-125">オーケストレーションをビルドして、正常に動作するかテストします。</span><span class="sxs-lookup"><span data-stu-id="78bc6-125">Build your orchestration to test it for completeness.</span></span>  
  
     <span data-ttu-id="78bc6-126">オーケストレーションをビルドするには、そのオーケストレーションがホストされているプロジェクトまたはソリューションをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="78bc6-126">You build your orchestration when you compile the project or solution that contains it.</span></span> <span data-ttu-id="78bc6-127">詳細については、次を参照してください。[オーケストレーションのビルド方法](../core/how-to-build-orchestrations.md)です。</span><span class="sxs-lookup"><span data-stu-id="78bc6-127">For more information, see [How to Build Orchestrations](../core/how-to-build-orchestrations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78bc6-128">参照</span><span class="sxs-lookup"><span data-stu-id="78bc6-128">See Also</span></span>  
 <span data-ttu-id="78bc6-129">[ビルドとオーケストレーションの実行](../core/building-and-running-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="78bc6-129">[Building and Running Orchestrations](../core/building-and-running-orchestrations.md) </span></span>  
 <span data-ttu-id="78bc6-130">[オーケストレーションの管理](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="78bc6-130">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 [<span data-ttu-id="78bc6-131">オーケストレーション デザイナーを使用してオーケストレーションの作成</span><span class="sxs-lookup"><span data-stu-id="78bc6-131">Creating Orchestrations Using Orchestration Designer</span></span>](../core/creating-orchestrations-using-orchestration-designer.md)