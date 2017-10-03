---
title: "SWIFT の逆アセンブラーの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, disassembler
- disassembler, configuring
ms.assetid: f3773781-7412-421c-943c-18cc665da8d9
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7aa71ce6ba1d2a910626446ed45439b8c7132e75
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-the-swift-disassembler"></a>SWIFT の逆アセンブラーを構成します。
を呼び出すときは、SWIFT 逆アセンブラー (DASM) は、次のタスクを実行、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]受信パイプライン。  
  
-   動的にメッセージの種類を検出し、ドキュメント スキーマの解決  
  
-   XML に SWIFT のフラット ファイルを解析します。  
  
-   XML (スキーマ) 検証を実行するリーダーを検証する XML を呼び出します  
  
-   BRE の検証を実行するビジネス ルール エンジン (BRE) を呼び出します  
  
-   解析された XML メッセージを公開します、メッセージ ボックス データベースに昇格されたコンテキスト プロパティと XML のシリアル化されたエラー収集  
  
-   受信バッチの処理  
  
 ユーザーのシナリオの特定の要件を満たすように上記の機能を構成することができ、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ソリューションです。  
  
 BizTalk パイプライン デザイナでは、カスタム受信パイプラインの開発時に SWIFT の逆アセンブラーを構成します。  
  
 カスタム受信パイプラインの逆アセンブル ステージに追加された後に SWIFT の逆アセンブラーを構成するには、BizTalk パイプライン デザイナー キャンバスに SWIFT 逆アセンブラー コンポーネントを選択します。 SWIFT の逆アセンブラーが、フォーカスを受け取るし、内のプロパティ ウィンドウを使用してその構成プロパティを設定することができます[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]です。  
  
 利用可能な構成プロパティとその説明と使用方法の詳細のテーブルの場合、次を参照してください。 [SWIFT 逆アセンブラーの構成プロパティ](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md)です。  
  
 SWIFT の逆アセンブラーを使用して、さまざまなシナリオと構成プロパティの設定については、次を参照してください。 [SWIFT 逆アセンブラおよびアセンブラ扱う](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)です。  
  
 ときに[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]バイナリ、カスタム パイプラインを静的に構成設定を書き込みますが、カスタム パイプラインをコンパイルします。 そのため、配置時に構成プロパティを変更または時刻を実行することはできません。  
  
> [!NOTE]
>  構成、コンパイル、およびカスタム パイプラインをデプロイした後、再コンパイルして、カスタム パイプラインを再配置、構成の変更が必要です。  
  
 作成する方法の詳細については、ビルド、およびカスタム パイプラインは、配置を参照してください[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]ヘルプします。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [SWIFT 逆アセンブラーの構成プロパティ](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md)