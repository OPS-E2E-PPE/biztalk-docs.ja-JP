---
title: "SWIFT の逆アセンブラーの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, disassembler
- disassembler, configuring
ms.assetid: f3773781-7412-421c-943c-18cc665da8d9
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7aa71ce6ba1d2a910626446ed45439b8c7132e75
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-the-swift-disassembler"></a><span data-ttu-id="ca121-102">SWIFT の逆アセンブラーを構成します。</span><span class="sxs-lookup"><span data-stu-id="ca121-102">Configuring the SWIFT Disassembler</span></span>
<span data-ttu-id="ca121-103">を呼び出すときは、SWIFT 逆アセンブラー (DASM) は、次のタスクを実行、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]受信パイプライン。</span><span class="sxs-lookup"><span data-stu-id="ca121-103">The SWIFT disassembler (DASM) performs the following tasks when you invoke it in a [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] receive pipeline:</span></span>  
  
-   <span data-ttu-id="ca121-104">動的にメッセージの種類を検出し、ドキュメント スキーマの解決</span><span class="sxs-lookup"><span data-stu-id="ca121-104">Dynamically discovers the message type and resolves the document schema</span></span>  
  
-   <span data-ttu-id="ca121-105">XML に SWIFT のフラット ファイルを解析します。</span><span class="sxs-lookup"><span data-stu-id="ca121-105">Parses SWIFT flat files into XML</span></span>  
  
-   <span data-ttu-id="ca121-106">XML (スキーマ) 検証を実行するリーダーを検証する XML を呼び出します</span><span class="sxs-lookup"><span data-stu-id="ca121-106">Invokes the XML validating reader to perform XML (schema) validation</span></span>  
  
-   <span data-ttu-id="ca121-107">BRE の検証を実行するビジネス ルール エンジン (BRE) を呼び出します</span><span class="sxs-lookup"><span data-stu-id="ca121-107">Invokes the Business Rule Engine (BRE) to perform BRE validation</span></span>  
  
-   <span data-ttu-id="ca121-108">解析された XML メッセージを公開します、メッセージ ボックス データベースに昇格されたコンテキスト プロパティと XML のシリアル化されたエラー収集</span><span class="sxs-lookup"><span data-stu-id="ca121-108">Publishes a parsed XML message to the MessageBox database with promoted context properties and serialized error collection XML</span></span>  
  
-   <span data-ttu-id="ca121-109">受信バッチの処理</span><span class="sxs-lookup"><span data-stu-id="ca121-109">Processes inbound batches</span></span>  
  
 <span data-ttu-id="ca121-110">ユーザーのシナリオの特定の要件を満たすように上記の機能を構成することができ、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="ca121-110">You can configure the functionality listed above to meet the specific requirements for a user scenario and [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] solution.</span></span>  
  
 <span data-ttu-id="ca121-111">BizTalk パイプライン デザイナでは、カスタム受信パイプラインの開発時に SWIFT の逆アセンブラーを構成します。</span><span class="sxs-lookup"><span data-stu-id="ca121-111">BizTalk Pipeline Designer configures the SWIFT disassembler during development time of the custom receive pipeline.</span></span>  
  
 <span data-ttu-id="ca121-112">カスタム受信パイプラインの逆アセンブル ステージに追加された後に SWIFT の逆アセンブラーを構成するには、BizTalk パイプライン デザイナー キャンバスに SWIFT 逆アセンブラー コンポーネントを選択します。</span><span class="sxs-lookup"><span data-stu-id="ca121-112">To configure the SWIFT disassembler after it has been added to the disassemble stage of a custom receive pipeline, select the SWIFT disassembler component on the BizTalk Pipeline Designer canvas.</span></span> <span data-ttu-id="ca121-113">SWIFT の逆アセンブラーが、フォーカスを受け取るし、内のプロパティ ウィンドウを使用してその構成プロパティを設定することができます[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ca121-113">The SWIFT disassembler then receives focus and you can set its configuration properties using the Properties window within [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)].</span></span>  
  
 <span data-ttu-id="ca121-114">利用可能な構成プロパティとその説明と使用方法の詳細のテーブルの場合、次を参照してください。 [SWIFT 逆アセンブラーの構成プロパティ](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="ca121-114">For a table of available configuration properties and their descriptions and usage details, see [SWIFT Disassembler Configuration Properties](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md).</span></span>  
  
 <span data-ttu-id="ca121-115">SWIFT の逆アセンブラーを使用して、さまざまなシナリオと構成プロパティの設定については、次を参照してください。 [SWIFT 逆アセンブラおよびアセンブラ扱う](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)です。</span><span class="sxs-lookup"><span data-stu-id="ca121-115">For information about using the SWIFT disassembler for different scenarios and setting the configuration properties, see [Working with the SWIFT Disassembler and Assembler](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md).</span></span>  
  
 <span data-ttu-id="ca121-116">ときに[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]バイナリ、カスタム パイプラインを静的に構成設定を書き込みますが、カスタム パイプラインをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="ca121-116">When [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] compiles the custom pipeline binary, it statically writes the configuration settings to the custom pipeline.</span></span> <span data-ttu-id="ca121-117">そのため、配置時に構成プロパティを変更または時刻を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="ca121-117">Therefore, you cannot change configuration properties during deployment or run time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ca121-118">構成、コンパイル、およびカスタム パイプラインをデプロイした後、再コンパイルして、カスタム パイプラインを再配置、構成の変更が必要です。</span><span class="sxs-lookup"><span data-stu-id="ca121-118">After you configure, compile, and deploy a custom pipeline, changes in the configuration require recompiling and redeployment of the custom pipeline.</span></span>  
  
 <span data-ttu-id="ca121-119">作成する方法の詳細については、ビルド、およびカスタム パイプラインは、配置を参照してください[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]ヘルプします。</span><span class="sxs-lookup"><span data-stu-id="ca121-119">For information about creating, building, and deploying custom pipelines, see [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Help.</span></span>  
  
 <span data-ttu-id="ca121-120">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ca121-120">This section contains:</span></span>  
  
-   [<span data-ttu-id="ca121-121">SWIFT 逆アセンブラーの構成プロパティ</span><span class="sxs-lookup"><span data-stu-id="ca121-121">SWIFT Disassembler Configuration Properties</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md)