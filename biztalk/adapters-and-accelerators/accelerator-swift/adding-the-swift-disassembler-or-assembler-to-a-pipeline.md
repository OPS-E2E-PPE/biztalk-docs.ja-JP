---
title: SWIFT 逆アセンブラーまたはアセンブラーをパイプラインに追加する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, adding assembler
- assembler, adding to pipelines
- pipelines, adding disassembler
- disassembler, adding to pipelines
ms.assetid: f39eb340-fe58-4c8f-b3f2-f7686a245095
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f48317c21942e0912f88d3e48523e07728c16ad3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968003"
---
# <a name="adding-the-swift-disassembler-or-assembler-to-a-pipeline"></a>SWIFT 逆アセンブラーまたはアセンブラーをパイプラインに追加します。
BizTalk パイプライン デザイナを使用するには Microsoft と[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]カスタム BizTalk を作成する受信パイプラインと送信されます。 SWIFT 逆アセンブラーは、カスタム受信パイプラインの「逆アセンブル」段階を使用できます。 同様に、カスタム送信パイプラインの「アセンブル」段階の SWIFT アセンブラーを使用することができます。 SWIFT 逆アセンブラーまたはアセンブラーをパイプライン デザイナーのツールボックスからを起動するには、は、パイプライン デザイナー キャンバスに、逆アセンブラーまたはアセンブラーを対応するパイプライン ステージにドラッグします。 逆アセンブラーまたはアセンブラーを呼び出す方法について詳しい手順については、「[モジュール 3: パイプライン プロジェクトの追加](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md)でエンド ツー エンド チュートリアル。 パイプライン プロジェクトでの作業やパイプライン デザイナーに関する詳細については、BizTalk Server のヘルプを参照してください。  
  
 仕様では、SWIFT 逆アセンブラーに「逆アセンブル」ステージが必要ですが、*最終的な*呼び出される受信パイプラインのステージ。 すべての後続のステージを使用すると、予期しない動作 (いない後続のステージを呼び出し、このような逆アセンブラーまたはが以前設定され、メッセージ ボックスに、メッセージを発行する前に昇格するコンテキスト プロパティを削除する逆アセンブラーデータベースの場合)。 SWIFT アセンブラーを「アセンブル」段階が必要ですが、同様に、*最初*送信パイプラインのステージ。 前のステージを使用して SWIFT アセンブラーが動的メッセージ型の探索が損なわれる可能性があります。  
  
 SWIFT 逆アセンブラーおよびアセンブラーは、それらを使用するときに、パイプライン デザイナー ツールボックス最初に手動で追加する必要があります。 これを行うための手順の詳細については[モジュール 3: パイプライン プロジェクトの追加](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md)でエンド ツー エンド チュートリアル。 コンポーネントは引き続き手動で追加すると、ツールボックスに表示されます (手動で削除するまで、またはアンインストールする[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)])。  
  
## <a name="see-also"></a>参照  
 [SWIFT 逆アセンブラーおよびアセンブラーの操作](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)