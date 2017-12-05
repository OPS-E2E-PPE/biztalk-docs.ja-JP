---
title: "SWIFT 逆アセンブラーまたはアセンブラーの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assembler, configuring
- configuring, disassembler
- disassembler, configuring
- configuring, assembler
ms.assetid: 56e421f2-0292-40af-b878-0cba1b034e19
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8920a8b74da14eeb8186d153444ced7c54d57724
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="configuring-the-swift-disassembler-or-assembler"></a><span data-ttu-id="ca92d-102">SWIFT 逆アセンブラーまたはアセンブラーを構成します。</span><span class="sxs-lookup"><span data-stu-id="ca92d-102">Configuring the SWIFT Disassembler or Assembler</span></span>
<span data-ttu-id="ca92d-103">カスタム パイプラインに SWIFT 逆アセンブラーまたはアセンブラー SWIFT を追加した後、動的なメッセージの種類の探索、受信バッチ解除処理、XML 検証の有効/無効の場合など、特定のシナリオを対象にする機能を提供することを構成する必要があります。ビジネス ルール エンジン (BRE) の検証、およびなど)。</span><span class="sxs-lookup"><span data-stu-id="ca92d-103">After you add the SWIFT disassembler or SWIFT assembler to a custom pipeline, you must configure it to provide the functionality you want for the particular scenario (such as enabling/disabling dynamic message type discovery, inbound debatching, XML validation, Business Rule Engine (BRE) validation, and so on).</span></span> <span data-ttu-id="ca92d-104">コンパイルおよびそれらを呼び出すカスタム パイプラインを展開する前に、開発時に SWIFT 逆アセンブラーまたはアセンブラーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca92d-104">You must configure the SWIFT disassembler and assembler during development time before you compile and deploy the custom pipelines that invoke them.</span></span> <span data-ttu-id="ca92d-105">SWIFT の逆アセンブラーまたはアセンブラーを構成するのには、パイプライン デザイナーでコンポーネントを選択し、構成プロパティをプロパティ ウィンドウで編集します。</span><span class="sxs-lookup"><span data-stu-id="ca92d-105">To configure the SWIFT disassembler/assembler, select the component in Pipeline Designer and edit the configuration properties in the Properties window.</span></span>  
  
 <span data-ttu-id="ca92d-106">参照してください[SWIFT 逆アセンブラーの構成プロパティ](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md)の全容と、各構成プロパティとその他の使用法と構成情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca92d-106">Refer to [SWIFT Disassembler Configuration Properties](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md) for complete details and descriptions for each configuration property, as well as other usage and configuration information.</span></span>  
  
 <span data-ttu-id="ca92d-107">参照してください[SWIFT アセンブラーの構成プロパティ](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md)完全な詳細とエンコードの文字セットの構成プロパティとその他の使用法と構成情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca92d-107">Refer to [SWIFT Assembler Configuration Properties](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md) for complete details and descriptions for the Encoding Charset configuration property, as well as other usage and configuration information.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ca92d-108">構成、コンパイル、およびカスタム パイプラインを展開した後、再コンパイルと再展開のカスタム パイプラインの構成の変更が必要です。</span><span class="sxs-lookup"><span data-stu-id="ca92d-108">After you configure, compile, and deploy the custom pipelines, changes in configuration will require re-compiling and re-deployment of the custom pipelines.</span></span>  
  
 <span data-ttu-id="ca92d-109">構成、コンパイル、および SWIFT メッセージを処理するため、カスタム パイプラインを展開後は、設定を受信場所を使用する、カスタム SWIFT 受信パイプライン、および、カスタム SWIFT を使用するポートの送信パイプラインに送信します。</span><span class="sxs-lookup"><span data-stu-id="ca92d-109">After you configure, compile, and deploy your custom pipelines for processing SWIFT messages, you can set up receive locations that use your custom SWIFT receive pipeline, and send ports that use your custom SWIFT send pipeline.</span></span> <span data-ttu-id="ca92d-110">受信ポートのパイプラインを展開および構成の詳細については、受信場所、および送信ポートを参照してください[第 4 章: XML の受信を作成して、フラット ファイル送信ポート](../../adapters-and-accelerators/accelerator-swift/module-4-adding-an-xml-receive-location-and-flat-file-send-port.md)、[モジュール 5: フラット ファイル受信を作成し、XML の送信ポート](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md)、および BizTalk Server ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="ca92d-110">For more information about deploying pipelines and configuring receive ports, receive locations, and send ports, see [Module 4: Creating XML Receive and Flat File Send Ports](../../adapters-and-accelerators/accelerator-swift/module-4-adding-an-xml-receive-location-and-flat-file-send-port.md), [Module 5: Creating Flat File Receive and XML Send Ports](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md), and BizTalk Server Help.</span></span>  
  
 <span data-ttu-id="ca92d-111">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ca92d-111">This section contains:</span></span>  
  
-   [<span data-ttu-id="ca92d-112">SWIFT 逆アセンブラーの構成</span><span class="sxs-lookup"><span data-stu-id="ca92d-112">Configuring the SWIFT Disassembler</span></span>](../../adapters-and-accelerators/accelerator-swift/configuring-the-swift-disassembler.md)  
  
-   [<span data-ttu-id="ca92d-113">SWIFT アセンブラーの構成</span><span class="sxs-lookup"><span data-stu-id="ca92d-113">Configuring the SWIFT Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/configuring-the-swift-assembler.md)  
  
## <a name="see-also"></a><span data-ttu-id="ca92d-114">参照</span><span class="sxs-lookup"><span data-stu-id="ca92d-114">See Also</span></span>  
 [<span data-ttu-id="ca92d-115">SWIFT 逆アセンブラーおよびアセンブラーの操作</span><span class="sxs-lookup"><span data-stu-id="ca92d-115">Working with the SWIFT Disassembler and Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)