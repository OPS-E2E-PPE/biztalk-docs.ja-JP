---
title: SWIFT 逆アセンブラーおよびアセンブラーの機能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disassembler, about disassembler
- assembler, about assembler
- assembler, functionality
- disassembler, functionality
ms.assetid: d4fc092e-586d-4360-921d-151af66b8bc1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f9a01480c5d308ffa882b2457e26548f4b5e43b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992859"
---
# <a name="swift-disassembler-and-assembler-functionality"></a>SWIFT 逆アセンブラーおよびアセンブラーの機能
SWIFT 逆アセンブラーで呼び出されたときに、次のタスクを実行できる、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]受信パイプライン。  
  
- 動的にメッセージの種類を検出し、ドキュメント スキーマを解決します。 これにより、1 つの受信ポートとパイプラインを複数の SWIFT メッセージ型を処理します。  
  
- SWIFT のフラット ファイルを XML に解析します。  
  
- データ型の妥当性、データの形式または長さの適合性チェックなどの XML (スキーマ) 検証を実行するにはリーダーを検証する XML を呼び出します。  
  
- SWIFT ネットワーク ルールに準拠のチェックや、スキーマが実装していないその他の複雑な検証を実行するなど、BRE の検証を実行するビジネス ルール エンジン (BRE) を呼び出します。  
  
- 昇格されたコンテキスト プロパティとシリアル化されたエラーのコレクション (解析または検証中に発生したエラーに関する情報を提供する) XML メッセージ ボックス データベースに解析された XML メッセージを発行します。  
  
  > [!NOTE]
  >  逆アセンブラーでは、解析中に致命的なエラーが発生すると、逆アセンブラーは XML ではなく、ネイティブのフラット ファイル形式でメッセージ ボックス データベースにメッセージを公開します。  
  
- 次のように受信のバッチを処理します。  
  
  -   解析し、バッチのエンベロープ (バッチ ヘッダー、トレーラーのバッチ) を保持します。  
  
  -   解析し、メッセージのエンベロープ (メッセージ ヘッダーは、メッセージのトレーラー) を保持します。  
  
  -   解析し、バッチ内の SWIFT のメッセージを個別に検証  
  
  -   SWIFT メッセージをメッセージ ボックス データベースに個別に発行します。  
  
  -   全体の受信のバッチをメッセージ ボックス データベースに 1 つのメッセージ (入力の正確なコピー) として発行します。  
  
  -   並べ替えや同じバッチの送信元メッセージの関連付けのバッチに関連するコンテキスト プロパティを昇格させる  
  
  SWIFT アセンブラーは、BizTalk 送信パイプラインで呼び出されたときに、次のタスクを実行できます。  
  
- 動的にメッセージの種類を検出し、ドキュメント スキーマを解決します。 これにより、単一の送信ポートとパイプラインを複数の SWIFT メッセージの種類。  
  
- SWIFT のフラット ファイル解析された XML にシリアル化します。  
  
## <a name="see-also"></a>参照  
 [SWIFT 逆アセンブラーおよびアセンブラーの操作](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)