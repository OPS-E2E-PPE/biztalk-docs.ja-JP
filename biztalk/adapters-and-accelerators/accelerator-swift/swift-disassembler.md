---
title: SWIFT 逆アセンブラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disassembler
- messages, receive pipelines
- receive pipelines, messages
ms.assetid: 42641550-0c88-4535-b5d5-b90acb30a6d3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8baec8f140c0f7f0d3220b17c879a4868247bf6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376980"
---
# <a name="swift-disassembler"></a>SWIFT 逆アセンブラー
パイプラインは、受信処理に送信されたすべてのメッセージ、[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]アプリケーション (受信場所で受信済み)。  
  
 で、BizTalk の受信処理に関連する論理実行段階では、パイプラインが表示されます。 パイプライン コンポーネントは、サービスまたは各ステージを実装します。 具体的には、逆アセンブラーは、受信パイプラインの逆アセンブル ステージをサービスします。 A4SWIFT は、SWIFT 固有のメッセージにカスタム逆アセンブラー コンポーネントで処理機能を提供します。  
  
 SWIFT 逆アセンブラー、独自のフラット ファイル逆アセンブラーは、SWIFT メッセージの受信と、バッチ処理するための機能を提供し、次の関数を実行します。  
  
- 動的にメッセージの種類を検出し、ドキュメント スキーマの解決  
  
- XML に SWIFT のフラット ファイルを解析します。  
  
- XML (スキーマ) 検証を実行するにはリーダーを検証する XML を呼び出します  
  
- BRE の検証を実行するビジネス ルール エンジン (BRE) を呼び出します  
  
- 昇格されたコンテキスト プロパティと XML のシリアル化されたエラー コレクションを付けて MessageBox データベースに解析された XML メッセージを発行します。  
  
- 処理し、受信バッチを逆アセンブル  
  
  次の図に、SWIFT 逆アセンブラーのデータ フローです。  
  
  ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro2.gif "FSA_Intro2")  
  
  SWIFT 逆アセンブラーの詳細については、次を参照してください。 [SWIFT 逆アセンブラーとアセンブラー](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Accelerator for SWIFT ランタイム](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)