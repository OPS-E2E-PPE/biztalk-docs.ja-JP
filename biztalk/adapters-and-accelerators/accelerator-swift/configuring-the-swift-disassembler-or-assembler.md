---
title: SWIFT 逆アセンブラーまたはアセンブラーの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assembler, configuring
- configuring, disassembler
- disassembler, configuring
- configuring, assembler
ms.assetid: 56e421f2-0292-40af-b878-0cba1b034e19
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54efbf924add1b381d41e515c82de4e69ea80203
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378489"
---
# <a name="configuring-the-swift-disassembler-or-assembler"></a><span data-ttu-id="a0dce-102">SWIFT 逆アセンブラーまたはアセンブラーの構成</span><span class="sxs-lookup"><span data-stu-id="a0dce-102">Configuring the SWIFT Disassembler or Assembler</span></span>
<span data-ttu-id="a0dce-103">SWIFT 逆アセンブラーまたは SWIFT アセンブラーをカスタム パイプラインに追加した後、(動的メッセージ型の探索、受信バッチ解除、XML の検証を有効化/無効にするなど、特定のシナリオを対象にする機能を提供するようを構成する必要があります。ビジネス ルール エンジン (BRE) の検証、およびなど)。</span><span class="sxs-lookup"><span data-stu-id="a0dce-103">After you add the SWIFT disassembler or SWIFT assembler to a custom pipeline, you must configure it to provide the functionality you want for the particular scenario (such as enabling/disabling dynamic message type discovery, inbound debatching, XML validation, Business Rule Engine (BRE) validation, and so on).</span></span> <span data-ttu-id="a0dce-104">SWIFT 逆アセンブラーおよびアセンブラーは、コンパイルして、それらを呼び出すカスタム パイプラインを展開する前に、開発時に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0dce-104">You must configure the SWIFT disassembler and assembler during development time before you compile and deploy the custom pipelines that invoke them.</span></span> <span data-ttu-id="a0dce-105">SWIFT 逆アセンブラーまたはアセンブラーを構成するには、パイプライン デザイナーでコンポーネントを選択し、構成プロパティ ウィンドウでプロパティを編集します。</span><span class="sxs-lookup"><span data-stu-id="a0dce-105">To configure the SWIFT disassembler/assembler, select the component in Pipeline Designer and edit the configuration properties in the Properties window.</span></span>  
  
 <span data-ttu-id="a0dce-106">参照してください[SWIFT 逆アセンブラーの構成プロパティ](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md)の詳細と、各構成プロパティとその他の使用法と構成情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="a0dce-106">Refer to [SWIFT Disassembler Configuration Properties](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md) for complete details and descriptions for each configuration property, as well as other usage and configuration information.</span></span>  
  
 <span data-ttu-id="a0dce-107">参照してください[SWIFT アセンブラーの構成プロパティ](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md)の詳細と、エンコードの文字セットの構成プロパティとその他の使用法と構成情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="a0dce-107">Refer to [SWIFT Assembler Configuration Properties](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md) for complete details and descriptions for the Encoding Charset configuration property, as well as other usage and configuration information.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a0dce-108">構成、コンパイル、およびカスタム パイプラインをデプロイした後、再コンパイルし、カスタム パイプラインの再デプロイ構成の変更が必要です。</span><span class="sxs-lookup"><span data-stu-id="a0dce-108">After you configure, compile, and deploy the custom pipelines, changes in configuration will require re-compiling and re-deployment of the custom pipelines.</span></span>  
  
 <span data-ttu-id="a0dce-109">設定することができますを構成する、コンパイル、および SWIFT メッセージを処理するため、カスタム パイプラインをデプロイした後最大受信場所をカスタムの SWIFT 受信パイプラインと送信、カスタムの SWIFT を使用するポートの送信パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="a0dce-109">After you configure, compile, and deploy your custom pipelines for processing SWIFT messages, you can set up receive locations that use your custom SWIFT receive pipeline, and send ports that use your custom SWIFT send pipeline.</span></span> <span data-ttu-id="a0dce-110">受信ポートのパイプラインを展開および構成の詳細については、受信場所、および送信ポートを参照してください[モジュール 4。受信 XML を作成し、フラット ファイル送信ポート](../../adapters-and-accelerators/accelerator-swift/module-4-adding-an-xml-receive-location-and-flat-file-send-port.md)、[第 5 章。受信フラット ファイルを作成して XML 送信ポート](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md)、および BizTalk Server のヘルプ。</span><span class="sxs-lookup"><span data-stu-id="a0dce-110">For more information about deploying pipelines and configuring receive ports, receive locations, and send ports, see [Module 4: Creating XML Receive and Flat File Send Ports](../../adapters-and-accelerators/accelerator-swift/module-4-adding-an-xml-receive-location-and-flat-file-send-port.md), [Module 5: Creating Flat File Receive and XML Send Ports](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md), and BizTalk Server Help.</span></span>  
  
 <span data-ttu-id="a0dce-111">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a0dce-111">This section contains:</span></span>  
  
-   [<span data-ttu-id="a0dce-112">SWIFT 逆アセンブラーの構成</span><span class="sxs-lookup"><span data-stu-id="a0dce-112">Configuring the SWIFT Disassembler</span></span>](../../adapters-and-accelerators/accelerator-swift/configuring-the-swift-disassembler.md)  
  
-   [<span data-ttu-id="a0dce-113">SWIFT アセンブラーの構成</span><span class="sxs-lookup"><span data-stu-id="a0dce-113">Configuring the SWIFT Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/configuring-the-swift-assembler.md)  
  
## <a name="see-also"></a><span data-ttu-id="a0dce-114">参照</span><span class="sxs-lookup"><span data-stu-id="a0dce-114">See Also</span></span>  
 [<span data-ttu-id="a0dce-115">SWIFT 逆アセンブラーおよびアセンブラーの操作</span><span class="sxs-lookup"><span data-stu-id="a0dce-115">Working with the SWIFT Disassembler and Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)