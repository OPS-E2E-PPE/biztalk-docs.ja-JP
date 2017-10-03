---
title: "SWIFT 逆アセンブラー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- disassembler
- messages, receive pipelines
- receive pipelines, messages
ms.assetid: 42641550-0c88-4535-b5d5-b90acb30a6d3
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac0024abe862f777e7ee798991d97845ec5098a9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="swift-disassembler"></a>SWIFT 逆アセンブラー
入力方向の受信パイプラインに送信されたすべてのメッセージの処理、 [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] (受信場所で受信した) アプリケーションです。  
  
 BizTalk の受信処理に関連する論理実行段階は受信パイプラインです。 パイプライン コンポーネントは、サービスまたは、各ステージを実装します。 具体的には、逆アセンブラーは、受信パイプラインの逆アセンブル ステージをサービスします。 A4SWIFT は、SWIFT 固有のメッセージにカスタム逆アセンブラー コンポーネントで処理機能を提供します。  
  
 SWIFT の逆アセンブラー、カスタムのフラット ファイル逆アセンブラーは、SWIFT メッセージの受信と、バッチ処理の機能を提供し、次の機能を実行します。  
  
-   動的にメッセージの種類を検出し、ドキュメント スキーマの解決  
  
-   XML に SWIFT のフラット ファイルを解析します。  
  
-   XML (スキーマ) 検証を実行するリーダーを検証する XML を呼び出します  
  
-   BRE の検証を実行するビジネス ルール エンジン (BRE) を呼び出します  
  
-   解析された XML メッセージを公開します、メッセージ ボックス データベースに昇格されたコンテキスト プロパティと XML のシリアル化されたエラー収集  
  
-   処理し、受信バッチを逆アセンブル  
  
 次の図は、逆アセンブラーの迅速なデータ フローです。  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro2.gif "FSA_Intro2")  
  
 SWIFT の逆アセンブラの詳細については、次を参照してください。 [SWIFT 逆アセンブラおよびアセンブラ扱う](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Accelerator for SWIFT のランタイム](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)