---
title: バッチに関連する昇格させたプロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- promoted properties, batch related properties
- batching, promoted properties
ms.assetid: 00df1d8f-2f3f-4e3f-9983-37dcf3514fd8
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea49f40097df45bac158150cd22d124b43831bcb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378942"
---
# <a name="batch-related-promoted-properties"></a>バッチに関連する昇格させたプロパティ
逆アセンブラーが特別な Microsoft とメッセージをマーク SWIFT 逆アセンブラーがメッセージ ボックス データベースに受信のバッチから送信されたメッセージを発行したとき[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]バッチ メッセージに固有のプロパティを昇格します。 これらのプロパティは、どのバッチがどのような序数の位置から、メッセージの送信元など内にあったに A4SWIFT の部分が保持すると、バッチなどのコンテキスト情報を提供します。  
  
 A4SWIFT は、バッチ メッセージの次の昇格させたプロパティを設定します。  
  
- **A4SWIFT_BatchId**  
  
- **A4SWIFT_IsMessageHeaderValued**  
  
- **A4SWIFT_IsMessageTrailerValued**  
  
- **A4SWIFT_NumberOfParts**  
  
- **A4SWIFT_PosInBatch**  
  
  これらおよびその他の昇格させたプロパティについては、次を参照してください。 [a4swift _ * 昇格プロパティ](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)します。  
  
## <a name="failures-during-batch-processing"></a>バッチ処理中にエラー  
 SWIFT 逆アセンブラーがメッセージのエラー (解析または検証) を検出した、バッチ処理中に場合 (**受信バッチ解除処理**設定**True**)、として、その動作がバッチ処理の構成によって異なります次に示します。  
  
- バッチ処理 (**受信バッチ解除処理**に設定**True**) を有効になっている断片化 (**断片化**に設定**True**)、逆アセンブラーは発行失敗したメッセージをメッセージ ボックス データベースに個別に、昇格させたプロパティに追加され、シリアル化に対応するエラー情報を**ErrorCollection** XML。 逆アセンブラーでは、予期しないデータ (つまり、指定したスキーマのいずれかを使用して、逆アセンブラーを解析できませんデータ) のバッチの最後に検出されると、逆アセンブラーが、バッチの最後のメッセージで予期しないデータが含まれています、解析失敗としてマークを付けます. 逆アセンブラーでは、処理中に致命的なエラーが発生すると、逆アセンブラーは、致命的なエラーとすべてのデータを 1 つのメッセージとして、インターチェンジの終了の原因となったメッセージを発行します。 逆アセンブラーには、致命的なエラーの発生後のメッセージをフラグメントされません。  
  
- バッチ処理 (**受信バッチ解除処理**に設定**True**) を無効になっている断片化 (**断片化**に設定**False**)、逆アセンブラーは発行失敗したメッセージをメッセージ ボックス データベースに個別に、昇格させたプロパティに追加され、シリアル化に対応するエラー情報を**ErrorCollection** XML。 さらに、逆アセンブラーは、ネイティブ形式 (入力の正確なコピー) で、1 つのメッセージとしてメッセージ ボックス データベースにバッチ全体が (1 つまたは複数の失敗したメッセージを含む) を発行します。 逆アセンブラーでマークされます、 **A4SWIFT_Failed**プロパティ セットを昇格**True**を 1 つまたは複数の失敗したメッセージがバッチに含まれているかを示します。 逆アセンブラーもアタッチしますシリアル化**ErrorCollection** XML フラグメント化されていないバッチで、バッチ内の個々 のメッセージで発生したすべてのエラーの連結を表します。 バッチ内の失敗したメッセージからメッセージごとのエラーの詳細を検出するには、(を関連付けることによって A4SWIFT_BatchId 上)、個々 の失敗したメッセージをメッセージ ボックス データベースから取得し、抽出する必要があります、 **ErrorCollection** XML各メッセージに失敗しました。 逆アセンブラーに失敗したバッチ全体に予期しないデータが含まれています (逆アセンブラーを発行するため、逆アセンブラーでは、予期しないデータ (つまり、指定したスキーマのいずれかを使用して、逆アセンブラーを解析できませんデータ) のバッチの最後に検出されると、メッセージ ボックス データベースにもそのまま)、予期しないデータが原因の解析失敗としてマークを付けます。  
  
- 非バッチ シナリオ (**受信バッチ解除処理**に設定**False**)、逆アセンブラー常にメッセージを発行失敗したメッセージ ボックス データベースに期待どおりに、個別にします。  
  
  A4SWIFT のエラーの詳細については、昇格させたプロパティと**ErrorCollection**オブジェクトを参照してください[メッセージ サブスクリプションの失敗の操作](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md)します。  
  
## <a name="see-also"></a>参照  
 [受信バッチの逆アセンブル](../../adapters-and-accelerators/accelerator-swift/disassembling-inbound-batches.md)   
 [SWIFT 逆アセンブラーおよびアセンブラーの操作](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)