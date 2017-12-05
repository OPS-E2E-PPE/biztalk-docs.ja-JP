---
title: "レッスン 5: カスタム受信パイプラインに SWIFT の逆アセンブラーを追加する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive pipelines, adding disassembler
- custom pipelines
- disassembler, custom pipelines
- disassembler, adding to pipelines
ms.assetid: 96e26d97-bfab-448f-b7b6-3bc2ec3ccebf
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0616c4adddc6e2d096624d02b968a21012ccd93b
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="lesson-5-adding-the-swift-disassembler-to-a-custom-receive-pipeline"></a>レッスン 5: カスタム受信パイプラインに SWIFT の逆アセンブラーを追加します。
このレッスンでは、パイプラインにカスタムの SWIFT 逆アセンブラー (DASM) を追加します。 逆アセンブラー パイプライン コンポーネントは、バッチ内のメッセージを個々 のドキュメントに分割するパイプライン コンポーネントです。  
  
 逆アセンブラー パイプライン コンポーネントで提供される[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Server は。  
  
-   フラット ファイル逆アセンブラー  
  
-   BizTalk Framework 逆アセンブラー  
  
-   XML 逆アセンブラー  
  
 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]追加 SWIFT 逆アセンブラーを追加します。  
  
### <a name="to-add-the-swift-custom-disassembler-to-your-pipeline"></a>SWIFT カスタム逆アセンブラーをパイプラインに追加するには  
  
1.  [表示] メニューからクリックして**ツールボックス**です。  
  
2.  **BizTalk パイプライン コンポーネントのツールボックス**、 をクリックして**SWIFT 逆アセンブラー**ドラッグして、**ここにドロップ**下のボックス、**逆アセンブル**で図形をステージ**BizTalk パイプライン デザイナ**です。 ままにして、 **SWIFT 逆アセンブラー**で選択された図形、 **BizTalk パイプライン デザイナ**です。  
  
3.  **プロパティ**ペインで、 **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema**の**SWIFT ヘッダー スキーマ**プロパティです。  
  
    > [!NOTE]
    >  混同しないでください**SWIFT ヘッダー スキーマ**とメッセージ ヘッダーのスキーマです。 設定する必要があります**SWIFT ヘッダー スキーマ**手順 3 でします。  
  
4.  **プロパティ** ウィンドウで、いることを確認、 **BRE 検証**プロパティに設定されている**True**です。  
  
    > [!NOTE]
    >  このチュートリアルで後ほど説明については、ビジネス ルール エンジン (BRE) の次に示します。  
  
5.  **プロパティ** ウィンドウで、いることを確認、 **XML 検証**プロパティに設定されている**True**です。  
  
6.  **プロパティ** ウィンドウで、いることを確認、**受信バッチ解除処理**プロパティに設定されている**False**です。  
  
7.  **ファイル**メニューの **すべて保存**して変更を保存します。  
  
 進みます[レッスン 6: カスタムを作成する送信パイプライン](../../adapters-and-accelerators/accelerator-swift/lesson-6-creating-a-custom-send-pipeline.md)です。