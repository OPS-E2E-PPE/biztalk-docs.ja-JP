---
title: SWIFT 逆アセンブラーの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, disassembler
- disassembler, configuring
ms.assetid: f3773781-7412-421c-943c-18cc665da8d9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ad88310f5bbf600edd576bc0bc17c64fe3ecbea
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001467"
---
# <a name="configuring-the-swift-disassembler"></a>SWIFT 逆アセンブラーを構成します。
SWIFT 逆アセンブラー (逆アセンブラー) は microsoft を呼び出すと、次のタスクを実行[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]受信パイプライン。  
  
- 動的にメッセージの種類を検出し、ドキュメント スキーマの解決  
  
- XML に SWIFT のフラット ファイルを解析します。  
  
- XML (スキーマ) 検証を実行するにはリーダーを検証する XML を呼び出します  
  
- BRE の検証を実行するビジネス ルール エンジン (BRE) を呼び出します  
  
- 昇格されたコンテキスト プロパティと XML のシリアル化されたエラー コレクションを付けて MessageBox データベースに解析された XML メッセージを発行します。  
  
- 受信バッチの処理  
  
  ユーザーのシナリオの特定の要件を満たすために上記の機能を構成することができますと[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ソリューション。  
  
  BizTalk パイプライン デザイナでは、カスタム受信パイプラインの開発時に、SWIFT 逆アセンブラーを構成します。  
  
  カスタム受信パイプラインの逆アセンブル ステージに追加した後で SWIFT 逆アセンブラーを構成するには、BizTalk パイプライン デザイナー キャンバスに SWIFT 逆アセンブラー コンポーネントを選択します。 SWIFT 逆アセンブラーは、フォーカスを受け取るし、Microsoft 内で [プロパティ] ウィンドウを使用してその構成プロパティを設定する[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]します。  
  
  使用可能な構成プロパティとその説明および使用方法の詳細のテーブルの場合、次を参照してください。 [SWIFT 逆アセンブラーの構成プロパティ](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md)します。  
  
  SWIFT 逆アセンブラーを使用して、さまざまなシナリオと構成プロパティの設定については、次を参照してください。 [SWIFT 逆アセンブラーとアセンブラー](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)します。  
  
  ときに[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]バイナリ、カスタム パイプラインに静的に構成設定を書き込むカスタム パイプラインをコンパイルします。 そのため、デプロイ時に構成プロパティを変更したり、時間を実行したりすることはできません。  
  
> [!NOTE]
>  構成、コンパイル、およびカスタム パイプラインをデプロイ後に再コンパイルし、カスタム パイプラインの再展開構成の変更が必要です。  
  
 作成、構築、およびカスタム パイプラインを展開する方法については、BizTalk Server のヘルプを参照してください。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [SWIFT 逆アセンブラーの構成プロパティ](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md)