---
title: "SWIFT 逆アセンブラーおよびアセンブラー機能 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- disassembler, about disassembler
- assembler, about assembler
- assembler, functionality
- disassembler, functionality
ms.assetid: d4fc092e-586d-4360-921d-151af66b8bc1
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0109979fbb9bf61fc0e1be833061b2a15b470690
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="swift-disassembler-and-assembler-functionality"></a>SWIFT 逆アセンブラーおよびアセンブラー機能
SWIFT の逆アセンブラーで呼び出されたときに、次のタスクを実行できる、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]受信パイプライン。  
  
-   動的にメッセージの種類を検出し、ドキュメント スキーマを解決します。 これにより、単一の受信ポートとパイプラインを複数の SWIFT メッセージ型を処理します。  
  
-   XML に SWIFT のフラット ファイルを解析します。  
  
-   データ型の有効性、データ形式または長さの準拠の確認などの XML (スキーマ) 検証を実行するリーダーを検証する XML を呼び出します。  
  
-   SWIFT ネットワーク ルールへの準拠の確認や、スキーマが実装されていないその他の複雑な検証を実行するなど、BRE の検証を実行するビジネス ルール エンジン (BRE) を呼び出します。  
  
-   メッセージ ボックス データベースに昇格されたコンテキスト プロパティとシリアル化されたエラーのコレクション (解析または検証中に発生したエラーに関する情報を提供する) を XML に解析された XML メッセージを発行します。  
  
    > [!NOTE]
    >  逆アセンブラーでは、解析中に致命的なエラーが発生すると、逆アセンブラーは XML ではなく、ネイティブのフラット ファイル形式でメッセージ ボックス データベースにメッセージを公開します。  
  
-   次のように受信のバッチを処理します。  
  
    -   解析し、バッチのエンベロープ (バッチ ヘッダー、トレーラーのバッチ) を保持します。  
  
    -   解析し、メッセージのエンベロープ (メッセージ ヘッダー、メッセージ トレーラー) を保持します。  
  
    -   解析し、個別に SWIFT メッセージのバッチでの検証  
  
    -   個別に SWIFT メッセージをメッセージ ボックス データベースに発行します。  
  
    -   全体の受信のバッチをメッセージ ボックス データベースに 1 つのメッセージ (入力の正確なコピー) として公開します。  
  
    -   並べ替えや同じバッチから送信されたメッセージの関連付けのバッチに関連するコンテキスト プロパティを昇格させる  
  
 SWIFT のアセンブラーは、BizTalk 送信パイプラインで呼び出されたときに、次のタスクを実行できます。  
  
-   動的にメッセージの種類を検出し、ドキュメント スキーマを解決します。 これにより、単一の送信ポートとパイプラインを複数 SWIFT メッセージの種類。  
  
-   SWIFT のフラット ファイル解析された XML にシリアル化します。  
  
## <a name="see-also"></a>参照  
 [SWIFT 逆アセンブラおよびアセンブラの操作](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)