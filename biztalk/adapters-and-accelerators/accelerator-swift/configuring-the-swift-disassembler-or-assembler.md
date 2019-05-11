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
# <a name="configuring-the-swift-disassembler-or-assembler"></a>SWIFT 逆アセンブラーまたはアセンブラーの構成
SWIFT 逆アセンブラーまたは SWIFT アセンブラーをカスタム パイプラインに追加した後、(動的メッセージ型の探索、受信バッチ解除、XML の検証を有効化/無効にするなど、特定のシナリオを対象にする機能を提供するようを構成する必要があります。ビジネス ルール エンジン (BRE) の検証、およびなど)。 SWIFT 逆アセンブラーおよびアセンブラーは、コンパイルして、それらを呼び出すカスタム パイプラインを展開する前に、開発時に構成する必要があります。 SWIFT 逆アセンブラーまたはアセンブラーを構成するには、パイプライン デザイナーでコンポーネントを選択し、構成プロパティ ウィンドウでプロパティを編集します。  
  
 参照してください[SWIFT 逆アセンブラーの構成プロパティ](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md)の詳細と、各構成プロパティとその他の使用法と構成情報について説明します。  
  
 参照してください[SWIFT アセンブラーの構成プロパティ](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md)の詳細と、エンコードの文字セットの構成プロパティとその他の使用法と構成情報について説明します。  
  
> [!NOTE]
>  構成、コンパイル、およびカスタム パイプラインをデプロイした後、再コンパイルし、カスタム パイプラインの再デプロイ構成の変更が必要です。  
  
 設定することができますを構成する、コンパイル、および SWIFT メッセージを処理するため、カスタム パイプラインをデプロイした後最大受信場所をカスタムの SWIFT 受信パイプラインと送信、カスタムの SWIFT を使用するポートの送信パイプラインを使用します。 受信ポートのパイプラインを展開および構成の詳細については、受信場所、および送信ポートを参照してください[モジュール 4。受信 XML を作成し、フラット ファイル送信ポート](../../adapters-and-accelerators/accelerator-swift/module-4-adding-an-xml-receive-location-and-flat-file-send-port.md)、[第 5 章。受信フラット ファイルを作成して XML 送信ポート](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md)、および BizTalk Server のヘルプ。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [SWIFT 逆アセンブラーの構成](../../adapters-and-accelerators/accelerator-swift/configuring-the-swift-disassembler.md)  
  
-   [SWIFT アセンブラーの構成](../../adapters-and-accelerators/accelerator-swift/configuring-the-swift-assembler.md)  
  
## <a name="see-also"></a>参照  
 [SWIFT 逆アセンブラーおよびアセンブラーの操作](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)