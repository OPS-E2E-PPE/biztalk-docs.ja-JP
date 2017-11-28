---
title: "SWIFT アセンブラーの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assembler, configuring
- configuring, assembler
ms.assetid: 76944226-e29b-4a7f-a4ab-3c3d5f13ec51
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76e1309012abbaac27e2e0ae6ec9b35f37d88884
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-the-swift-assembler"></a><span data-ttu-id="7f3b8-102">SWIFT アセンブラーを構成します。</span><span class="sxs-lookup"><span data-stu-id="7f3b8-102">Configuring the SWIFT Assembler</span></span>
<span data-ttu-id="7f3b8-103">を呼び出すときは、SWIFT アセンブラーは、次のタスクを実行、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]送信パイプライン。</span><span class="sxs-lookup"><span data-stu-id="7f3b8-103">The SWIFT assembler performs the following tasks when you invoke it in a [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] send pipeline:</span></span>  
  
-   <span data-ttu-id="7f3b8-104">動的にメッセージの種類を検出し、ドキュメント スキーマの解決</span><span class="sxs-lookup"><span data-stu-id="7f3b8-104">Dynamically discovers the message type and resolves the document schema</span></span>  
  
-   <span data-ttu-id="7f3b8-105">SWIFT のフラット ファイル解析された XML にシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="7f3b8-105">Serializes parsed XML into SWIFT flat files</span></span>  
  
 <span data-ttu-id="7f3b8-106">エンコード文字セット (たとえば、ASCII または Unicode エンコードを使用する場合など) のシリアル化された出力をエンコードするために使用されるを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="7f3b8-106">You can configure the encoding character set used for encoding the serialized output (for example, to use ASCII or Unicode encoding).</span></span>  
  
 <span data-ttu-id="7f3b8-107">SWIFT アセンブラーを使用するカスタム送信パイプラインの開発時に SWIFT アセンブラーを構成します。</span><span class="sxs-lookup"><span data-stu-id="7f3b8-107">You configure the SWIFT assembler during development time of the custom send pipeline that uses the SWIFT assembler.</span></span>  
  
 <span data-ttu-id="7f3b8-108">BizTalk パイプライン デザイナでは、カスタム送信パイプラインの開発時に SWIFT アセンブラーを構成します。</span><span class="sxs-lookup"><span data-stu-id="7f3b8-108">BizTalk Pipeline Designer configures the SWIFT assembler during development time of the custom send pipeline.</span></span>  
  
 <span data-ttu-id="7f3b8-109">カスタム送信パイプラインのアセンブル ステージに追加された後に SWIFT アセンブラーを構成するには、パイプライン デザイナー キャンバスに SWIFT アセンブラー コンポーネントを選択します。</span><span class="sxs-lookup"><span data-stu-id="7f3b8-109">To configure the SWIFT assembler after it has been added to the assemble stage of a custom send pipeline, select the SWIFT assembler component on the Pipeline Designer canvas.</span></span> <span data-ttu-id="7f3b8-110">SWIFT アセンブラーし、フォーカスを受け取るし、内のプロパティ ウィンドウを使用してその構成プロパティを設定することができます[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="7f3b8-110">The SWIFT assembler then receives focus, and you can set its configuration properties using the Properties window within [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)].</span></span>  
  
 <span data-ttu-id="7f3b8-111">利用可能な構成プロパティとその説明と使用方法の詳細のテーブルの場合、次を参照してください。 [SWIFT アセンブラーの構成プロパティ](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="7f3b8-111">For a table of available configuration properties and their descriptions and usage details, see [SWIFT Assembler Configuration Properties](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md).</span></span>  
  
 <span data-ttu-id="7f3b8-112">SWIFT アセンブラーを使用して、さまざまなシナリオと構成プロパティの設定については、次を参照してください。 [SWIFT 逆アセンブラおよびアセンブラ扱う](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)です。</span><span class="sxs-lookup"><span data-stu-id="7f3b8-112">For information about using the SWIFT assembler for different scenarios and setting the configuration properties, see [Working with the SWIFT Disassembler and Assembler](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md).</span></span>  
  
 <span data-ttu-id="7f3b8-113">カスタム パイプラインのバイナリのコンパイル時に静的に構成設定をカスタム パイプラインに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="7f3b8-113">When the custom pipeline binary is compiled, it statically writes the configuration settings to the custom pipeline.</span></span> <span data-ttu-id="7f3b8-114">そのため、配置時に構成プロパティを変更または時刻を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="7f3b8-114">Therefore, you cannot change configuration properties during deployment or run time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7f3b8-115">構成、コンパイル、およびカスタム パイプラインをデプロイした後、再コンパイルして、カスタム パイプラインを再配置、構成の変更が必要です。</span><span class="sxs-lookup"><span data-stu-id="7f3b8-115">After you configure, compile, and deploy a custom pipeline, changes in the configuration require recompiling and redeployment of the custom pipeline.</span></span>  
  
 <span data-ttu-id="7f3b8-116">作成する方法の詳細については、ビルド、およびカスタム パイプラインは、配置を参照してください[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]ヘルプします。</span><span class="sxs-lookup"><span data-stu-id="7f3b8-116">For information about creating, building, and deploying custom pipelines, see [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Help.</span></span>  
  
 <span data-ttu-id="7f3b8-117">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7f3b8-117">This section contains:</span></span>  
  
-   [<span data-ttu-id="7f3b8-118">SWIFT アセンブラーの構成プロパティ</span><span class="sxs-lookup"><span data-stu-id="7f3b8-118">SWIFT Assembler Configuration Properties</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md)