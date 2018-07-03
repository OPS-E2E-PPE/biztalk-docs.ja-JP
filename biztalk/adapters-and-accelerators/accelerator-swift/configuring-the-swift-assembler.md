---
title: SWIFT アセンブラーの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assembler, configuring
- configuring, assembler
ms.assetid: 76944226-e29b-4a7f-a4ab-3c3d5f13ec51
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50c58ad000e465949229400128ce4c47da40806e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993667"
---
# <a name="configuring-the-swift-assembler"></a><span data-ttu-id="6c1b7-102">SWIFT アセンブラーの構成</span><span class="sxs-lookup"><span data-stu-id="6c1b7-102">Configuring the SWIFT Assembler</span></span>
<span data-ttu-id="6c1b7-103">Microsoft で起動するときに、SWIFT アセンブラーが、次のタスクを実行します[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]送信パイプライン。</span><span class="sxs-lookup"><span data-stu-id="6c1b7-103">The SWIFT assembler performs the following tasks when you invoke it in a Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] send pipeline:</span></span>  
  
- <span data-ttu-id="6c1b7-104">動的にメッセージの種類を検出し、ドキュメント スキーマの解決</span><span class="sxs-lookup"><span data-stu-id="6c1b7-104">Dynamically discovers the message type and resolves the document schema</span></span>  
  
- <span data-ttu-id="6c1b7-105">SWIFT のフラット ファイル解析された XML にシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="6c1b7-105">Serializes parsed XML into SWIFT flat files</span></span>  
  
  <span data-ttu-id="6c1b7-106">エンコードの文字 (たとえば、ASCII または Unicode エンコーディングを使用する場合など) のシリアル化された出力をエンコードするために使用される設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="6c1b7-106">You can configure the encoding character set used for encoding the serialized output (for example, to use ASCII or Unicode encoding).</span></span>  
  
  <span data-ttu-id="6c1b7-107">SWIFT アセンブラーを使用するカスタム送信パイプラインの開発時に、SWIFT アセンブラーを構成します。</span><span class="sxs-lookup"><span data-stu-id="6c1b7-107">You configure the SWIFT assembler during development time of the custom send pipeline that uses the SWIFT assembler.</span></span>  
  
  <span data-ttu-id="6c1b7-108">BizTalk パイプライン デザイナでは、カスタム送信パイプラインの開発時に、SWIFT アセンブラーを構成します。</span><span class="sxs-lookup"><span data-stu-id="6c1b7-108">BizTalk Pipeline Designer configures the SWIFT assembler during development time of the custom send pipeline.</span></span>  
  
  <span data-ttu-id="6c1b7-109">カスタム送信パイプラインのアセンブル ステージに追加した後で、SWIFT アセンブラーを構成するには、パイプライン デザイナー キャンバスに SWIFT アセンブラー コンポーネントを選択します。</span><span class="sxs-lookup"><span data-stu-id="6c1b7-109">To configure the SWIFT assembler after it has been added to the assemble stage of a custom send pipeline, select the SWIFT assembler component on the Pipeline Designer canvas.</span></span> <span data-ttu-id="6c1b7-110">SWIFT アセンブラーし、フォーカスを受け取るし、Microsoft 内で [プロパティ] ウィンドウを使用してその構成プロパティを設定する[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="6c1b7-110">The SWIFT assembler then receives focus, and you can set its configuration properties using the Properties window within Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)].</span></span>  
  
  <span data-ttu-id="6c1b7-111">使用可能な構成プロパティとその説明および使用方法の詳細のテーブルの場合、次を参照してください。 [SWIFT アセンブラーの構成プロパティ](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="6c1b7-111">For a table of available configuration properties and their descriptions and usage details, see [SWIFT Assembler Configuration Properties](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md).</span></span>  
  
  <span data-ttu-id="6c1b7-112">SWIFT アセンブラーを使用して、さまざまなシナリオと構成プロパティの設定については、次を参照してください。 [SWIFT 逆アセンブラーとアセンブラー](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)します。</span><span class="sxs-lookup"><span data-stu-id="6c1b7-112">For information about using the SWIFT assembler for different scenarios and setting the configuration properties, see [Working with the SWIFT Disassembler and Assembler](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md).</span></span>  
  
  <span data-ttu-id="6c1b7-113">カスタム パイプラインのバイナリがコンパイルされると、静的に構成設定をカスタム パイプラインに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="6c1b7-113">When the custom pipeline binary is compiled, it statically writes the configuration settings to the custom pipeline.</span></span> <span data-ttu-id="6c1b7-114">そのため、デプロイ時に構成プロパティを変更したり、時間を実行したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="6c1b7-114">Therefore, you cannot change configuration properties during deployment or run time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6c1b7-115">構成、コンパイル、およびカスタム パイプラインをデプロイ後に再コンパイルし、カスタム パイプラインの再展開構成の変更が必要です。</span><span class="sxs-lookup"><span data-stu-id="6c1b7-115">After you configure, compile, and deploy a custom pipeline, changes in the configuration require recompiling and redeployment of the custom pipeline.</span></span>  
  
 <span data-ttu-id="6c1b7-116">作成、構築、およびカスタム パイプラインを展開する方法については、BizTalk Server のヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c1b7-116">For information about creating, building, and deploying custom pipelines, see BizTalk Server Help.</span></span>  
  
 <span data-ttu-id="6c1b7-117">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6c1b7-117">This section contains:</span></span>  
  
-   [<span data-ttu-id="6c1b7-118">SWIFT アセンブラーの構成プロパティ</span><span class="sxs-lookup"><span data-stu-id="6c1b7-118">SWIFT Assembler Configuration Properties</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md)