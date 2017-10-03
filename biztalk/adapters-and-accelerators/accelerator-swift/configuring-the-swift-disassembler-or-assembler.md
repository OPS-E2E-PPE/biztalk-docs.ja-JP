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
ms.openlocfilehash: 220c115edac37b8f7268719eefb2095fa7594243
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-the-swift-disassembler-or-assembler"></a>SWIFT 逆アセンブラーまたはアセンブラーを構成します。
カスタム パイプラインに SWIFT 逆アセンブラーまたはアセンブラー SWIFT を追加した後、動的なメッセージの種類の探索、受信バッチ解除処理、XML 検証の有効/無効の場合など、特定のシナリオを対象にする機能を提供することを構成する必要があります。ビジネス ルール エンジン (BRE) の検証、およびなど)。 コンパイルおよびそれらを呼び出すカスタム パイプラインを展開する前に、開発時に SWIFT 逆アセンブラーまたはアセンブラーを構成する必要があります。 SWIFT の逆アセンブラーまたはアセンブラーを構成するのには、パイプライン デザイナーでコンポーネントを選択し、構成プロパティをプロパティ ウィンドウで編集します。  
  
 参照してください[SWIFT 逆アセンブラーの構成プロパティ](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md)の全容と、各構成プロパティとその他の使用法と構成情報について説明します。  
  
 参照してください[SWIFT アセンブラーの構成プロパティ](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md)完全な詳細とエンコードの文字セットの構成プロパティとその他の使用法と構成情報について説明します。  
  
> [!NOTE]
>  構成、コンパイル、およびカスタム パイプラインを展開した後、再コンパイルと再展開のカスタム パイプラインの構成の変更が必要です。  
  
 構成、コンパイル、および SWIFT メッセージを処理するため、カスタム パイプラインを展開後は、設定を受信場所を使用する、カスタム SWIFT 受信パイプライン、および、カスタム SWIFT を使用するポートの送信パイプラインに送信します。 受信ポートのパイプラインを展開および構成の詳細については、受信場所、および送信ポートを参照してください[第 4 章: XML の受信を作成して、フラット ファイル送信ポート](../../adapters-and-accelerators/accelerator-swift/module-4-adding-an-xml-receive-location-and-flat-file-send-port.md)、[モジュール 5: フラット ファイル受信を作成し、XML の送信ポート](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md)、および[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]ヘルプします。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [SWIFT の逆アセンブラーを構成します。](../../adapters-and-accelerators/accelerator-swift/configuring-the-swift-disassembler.md)  
  
-   [SWIFT アセンブラーを構成します。](../../adapters-and-accelerators/accelerator-swift/configuring-the-swift-assembler.md)  
  
## <a name="see-also"></a>参照  
 [SWIFT 逆アセンブラおよびアセンブラの操作](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)