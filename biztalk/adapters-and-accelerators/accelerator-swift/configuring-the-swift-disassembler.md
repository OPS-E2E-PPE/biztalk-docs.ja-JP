---
title: SWIFT 逆アセンブラーの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, disassembler
- disassembler, configuring
ms.assetid: f3773781-7412-421c-943c-18cc665da8d9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ad88310f5bbf600edd576bc0bc17c64fe3ecbea
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001467"
---
# <a name="configuring-the-swift-disassembler"></a><span data-ttu-id="4458e-102">SWIFT 逆アセンブラーを構成します。</span><span class="sxs-lookup"><span data-stu-id="4458e-102">Configuring the SWIFT Disassembler</span></span>
<span data-ttu-id="4458e-103">SWIFT 逆アセンブラー (逆アセンブラー) は microsoft を呼び出すと、次のタスクを実行[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]受信パイプライン。</span><span class="sxs-lookup"><span data-stu-id="4458e-103">The SWIFT disassembler (DASM) performs the following tasks when you invoke it in a Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] receive pipeline:</span></span>  
  
- <span data-ttu-id="4458e-104">動的にメッセージの種類を検出し、ドキュメント スキーマの解決</span><span class="sxs-lookup"><span data-stu-id="4458e-104">Dynamically discovers the message type and resolves the document schema</span></span>  
  
- <span data-ttu-id="4458e-105">XML に SWIFT のフラット ファイルを解析します。</span><span class="sxs-lookup"><span data-stu-id="4458e-105">Parses SWIFT flat files into XML</span></span>  
  
- <span data-ttu-id="4458e-106">XML (スキーマ) 検証を実行するにはリーダーを検証する XML を呼び出します</span><span class="sxs-lookup"><span data-stu-id="4458e-106">Invokes the XML validating reader to perform XML (schema) validation</span></span>  
  
- <span data-ttu-id="4458e-107">BRE の検証を実行するビジネス ルール エンジン (BRE) を呼び出します</span><span class="sxs-lookup"><span data-stu-id="4458e-107">Invokes the Business Rule Engine (BRE) to perform BRE validation</span></span>  
  
- <span data-ttu-id="4458e-108">昇格されたコンテキスト プロパティと XML のシリアル化されたエラー コレクションを付けて MessageBox データベースに解析された XML メッセージを発行します。</span><span class="sxs-lookup"><span data-stu-id="4458e-108">Publishes a parsed XML message to the MessageBox database with promoted context properties and serialized error collection XML</span></span>  
  
- <span data-ttu-id="4458e-109">受信バッチの処理</span><span class="sxs-lookup"><span data-stu-id="4458e-109">Processes inbound batches</span></span>  
  
  <span data-ttu-id="4458e-110">ユーザーのシナリオの特定の要件を満たすために上記の機能を構成することができますと[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ソリューション。</span><span class="sxs-lookup"><span data-stu-id="4458e-110">You can configure the functionality listed above to meet the specific requirements for a user scenario and [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] solution.</span></span>  
  
  <span data-ttu-id="4458e-111">BizTalk パイプライン デザイナでは、カスタム受信パイプラインの開発時に、SWIFT 逆アセンブラーを構成します。</span><span class="sxs-lookup"><span data-stu-id="4458e-111">BizTalk Pipeline Designer configures the SWIFT disassembler during development time of the custom receive pipeline.</span></span>  
  
  <span data-ttu-id="4458e-112">カスタム受信パイプラインの逆アセンブル ステージに追加した後で SWIFT 逆アセンブラーを構成するには、BizTalk パイプライン デザイナー キャンバスに SWIFT 逆アセンブラー コンポーネントを選択します。</span><span class="sxs-lookup"><span data-stu-id="4458e-112">To configure the SWIFT disassembler after it has been added to the disassemble stage of a custom receive pipeline, select the SWIFT disassembler component on the BizTalk Pipeline Designer canvas.</span></span> <span data-ttu-id="4458e-113">SWIFT 逆アセンブラーは、フォーカスを受け取るし、Microsoft 内で [プロパティ] ウィンドウを使用してその構成プロパティを設定する[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="4458e-113">The SWIFT disassembler then receives focus and you can set its configuration properties using the Properties window within Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)].</span></span>  
  
  <span data-ttu-id="4458e-114">使用可能な構成プロパティとその説明および使用方法の詳細のテーブルの場合、次を参照してください。 [SWIFT 逆アセンブラーの構成プロパティ](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="4458e-114">For a table of available configuration properties and their descriptions and usage details, see [SWIFT Disassembler Configuration Properties](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md).</span></span>  
  
  <span data-ttu-id="4458e-115">SWIFT 逆アセンブラーを使用して、さまざまなシナリオと構成プロパティの設定については、次を参照してください。 [SWIFT 逆アセンブラーとアセンブラー](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)します。</span><span class="sxs-lookup"><span data-stu-id="4458e-115">For information about using the SWIFT disassembler for different scenarios and setting the configuration properties, see [Working with the SWIFT Disassembler and Assembler](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md).</span></span>  
  
  <span data-ttu-id="4458e-116">ときに[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]バイナリ、カスタム パイプラインに静的に構成設定を書き込むカスタム パイプラインをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="4458e-116">When [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] compiles the custom pipeline binary, it statically writes the configuration settings to the custom pipeline.</span></span> <span data-ttu-id="4458e-117">そのため、デプロイ時に構成プロパティを変更したり、時間を実行したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4458e-117">Therefore, you cannot change configuration properties during deployment or run time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4458e-118">構成、コンパイル、およびカスタム パイプラインをデプロイ後に再コンパイルし、カスタム パイプラインの再展開構成の変更が必要です。</span><span class="sxs-lookup"><span data-stu-id="4458e-118">After you configure, compile, and deploy a custom pipeline, changes in the configuration require recompiling and redeployment of the custom pipeline.</span></span>  
  
 <span data-ttu-id="4458e-119">作成、構築、およびカスタム パイプラインを展開する方法については、BizTalk Server のヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4458e-119">For information about creating, building, and deploying custom pipelines, see BizTalk Server Help.</span></span>  
  
 <span data-ttu-id="4458e-120">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4458e-120">This section contains:</span></span>  
  
-   [<span data-ttu-id="4458e-121">SWIFT 逆アセンブラーの構成プロパティ</span><span class="sxs-lookup"><span data-stu-id="4458e-121">SWIFT Disassembler Configuration Properties</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md)