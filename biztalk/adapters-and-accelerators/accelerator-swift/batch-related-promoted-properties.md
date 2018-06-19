---
title: バッチに関連する昇格させたプロパティ |Microsoft ドキュメント
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
ms.openlocfilehash: 20fa421c6536d1d5182a11872206783392c65f69
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210546"
---
# <a name="batch-related-promoted-properties"></a>バッチに関連する昇格させたプロパティ
逆アセンブラーが特殊なメッセージをマーク SWIFT の逆アセンブラーを発行すると、メッセージ ボックス データベースに受信のバッチから発信されたメッセージ、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]バッチ メッセージに固有のプロパティを昇格します。 これらのプロパティは、メッセージをどのような序数の位置から開始するバッチなど内にあったに A4SWIFT の部分が保持されると、バッチなどのコンテキスト情報を提供します。  
  
 A4SWIFT は、バッチ メッセージの次の昇格させたプロパティを設定します。  
  
-   **A4SWIFT_BatchId**  
  
-   **A4SWIFT_IsMessageHeaderValued**  
  
-   **A4SWIFT_IsMessageTrailerValued**  
  
-   **A4SWIFT_NumberOfParts**  
  
-   **A4SWIFT_PosInBatch**  
  
 これらおよびその他の昇格させたプロパティについては、次を参照してください。 [A4SWIFT_ * 昇格されたプロパティ](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)です。  
  
## <a name="failures-during-batch-processing"></a>バッチ処理中にエラー  
 バッチ処理中に SWIFT の逆アセンブラーがメッセージのエラー (解析または検証) を検出した場合 (**受信バッチ解除処理**'éý' **True**)、として、その動作がバッチ処理の構成によって異なります次に示します。  
  
-   バッチ処理の (**受信バッチ解除処理**に設定**True**) 断片化が有効になっていると (**断片化**に設定**True**) では、逆アセンブラー、MessageBox データベースに失敗したメッセージに個別に、公開されたメッセージの昇格させたプロパティに追加され、シリアル化に対応するエラー情報**元**XML です。 逆アセンブラーには、(つまり、指定したスキーマのいずれかを使用して、逆アセンブラーを解析できませんデータ) のバッチの終了時に予期しないデータが検出されると、逆アセンブラー、バッチの最後のメッセージで予期しないデータが含まれています、解析失敗としてマーク. 逆アセンブラーでは、処理中に致命的なエラーが発生すると、逆アセンブラーは、致命的なエラーとすべてのデータを単一のメッセージとして、インターチェンジの終了の原因となったメッセージを公開します。 逆アセンブラーは致命的なエラーの後にメッセージをフラグメント化されません。  
  
-   バッチ処理の (**受信バッチ解除処理**に設定**True**) 断片化が無効になっていると (**断片化**'éý' **False**) では、逆アセンブラー、MessageBox データベースに失敗したメッセージに個別に、公開されたメッセージの昇格させたプロパティに追加され、シリアル化に対応するエラー情報**元**XML です。 さらに、逆アセンブラーは、ネイティブ形式 (入力の正確なコピー) で、1 つのメッセージとしてメッセージ ボックス データベースにバッチ全体が (1 つまたは複数の失敗したメッセージを含む) を公開します。 逆アセンブラーをマークして、 **A4SWIFT_Failed**プロパティ セットを昇格**True**を 1 つまたは複数の失敗したメッセージが、バッチに含まれていることを示します。 逆アセンブラーがアタッチもシリアル化**元**を断片化されていないバッチをバッチ内の個々 のメッセージで発生したすべてのエラーの連結を表す XML。 バッチ内の失敗したメッセージからメッセージごとのエラーの詳細を探索するには、(を関連付けることによって A4SWIFT_BatchId で)、メッセージ ボックス データベースから個々 の失敗したメッセージを取得し、抽出する必要があります、**元**XML各メッセージに失敗しました。 逆アセンブラーに失敗したバッチ全体に予期しないデータが含まれています (逆アセンブラーを公開するため、逆アセンブラーでは、(つまり、指定したスキーマのいずれかを使用して、逆アセンブラーを解析できませんデータ) のバッチの終了時に予期しないデータが検出されると、メッセージ ボックス データベースにもそのまま)、予期しないデータのための解析失敗としてマークを付けます。  
  
-   バッチ以外のシナリオ (**受信バッチ解除処理**'éý' **False**)、逆アセンブラー常にメッセージの公開失敗したメッセージ ボックス データベースに期待どおりに、個別にします。  
  
 昇格させたプロパティ A4SWIFT のエラーの詳細については、**元**オブジェクトを参照してください[メッセージ サブスクリプションの失敗の操作](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md)です。  
  
## <a name="see-also"></a>参照  
 [受信バッチを逆アセンブル](../../adapters-and-accelerators/accelerator-swift/disassembling-inbound-batches.md)   
 [SWIFT 逆アセンブラおよびアセンブラの操作](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)