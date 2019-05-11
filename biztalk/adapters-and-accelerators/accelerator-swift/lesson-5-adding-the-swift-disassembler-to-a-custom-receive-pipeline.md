---
title: 'レッスン 5: SWIFT 逆アセンブラーをカスタム受信パイプラインに追加する |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive pipelines, adding disassembler
- custom pipelines
- disassembler, custom pipelines
- disassembler, adding to pipelines
ms.assetid: 96e26d97-bfab-448f-b7b6-3bc2ec3ccebf
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f37d8ff6369a030bf284584f19192f651cb08a2
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530287"
---
# <a name="lesson-5-adding-the-swift-disassembler-to-a-custom-receive-pipeline"></a>レッスン 5: SWIFT 逆アセンブラーをカスタム受信パイプラインに追加します。
このレッスンでは、パイプラインにカスタムの SWIFT 逆アセンブラー (逆アセンブラー) を追加します。 逆アセンブラー パイプライン コンポーネントは、バッチ内のメッセージを個々 のドキュメントに分割するパイプライン コンポーネントです。  
  
 MicrosoftBizTalk サーバーで提供される、逆アセンブラー パイプライン コンポーネントは次のとおりです。  
  
- フラット ファイル逆アセンブラー  
  
- BizTalk Framework 逆アセンブラー  
  
- XML 逆アセンブラー  
  
  Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]追加 SWIFT 逆アセンブラーを追加します。  
  
### <a name="to-add-the-swift-custom-disassembler-to-your-pipeline"></a>SWIFT カスタム逆アセンブラーをパイプラインに追加するには  
  
1. [表示] メニューからクリックして**ツールボックス**します。  
  
2. **BizTalk パイプライン コンポーネントのツールボックス**、 をクリックして**SWIFT 逆アセンブラー**ドラッグして、**ここにドロップ**下のボックス、**逆アセンブル**で図形をステージ**BizTalk パイプライン デザイナ**します。 ままに、 **SWIFT 逆アセンブラー**で選択されている図形、 **BizTalk パイプライン デザイナ**します。  
  
3. **プロパティ**ペインで、 **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema**の**SWIFT ヘッダー スキーマ**プロパティ。  
  
   > [!NOTE]
   >  混同しないでください**SWIFT ヘッダー スキーマ**とメッセージ ヘッダーのスキーマ。 設定する必要があります**SWIFT ヘッダー スキーマ**手順 3. でします。  
  
4. **プロパティ**ウィンドウで、いることを確認、 **BRE 検証**プロパティに設定されて**True**します。  
  
   > [!NOTE]
   >  ビジネス ルール エンジン (BRE) の詳細については、このチュートリアルの後半に従います。  
  
5. **プロパティ**ウィンドウで、いることを確認、 **XML 検証**プロパティに設定されて**True**します。  
  
6. **プロパティ**ウィンドウで、いることを確認、**分割処理受信**プロパティに設定されて**False**します。  
  
7. **ファイル**メニューの **すべて保存**変更を保存します。  
  
   続行する[レッスン 6。送信パイプラインの作成、カスタム](../../adapters-and-accelerators/accelerator-swift/lesson-6-creating-a-custom-send-pipeline.md)します。