---
title: SWIFT 逆アセンブラーまたはアセンブラーをパイプラインに追加する |Microsoft ドキュメント
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
ms.openlocfilehash: 0648e6c51d83a95fb24b36d872e06e157480c5fb
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005251"
---
# <a name="adding-the-swift-disassembler-or-assembler-to-a-pipeline"></a>SWIFT 逆アセンブラーまたはアセンブラーをパイプラインに追加します。
BizTalk パイプライン デザイナを使用する[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]カスタム BizTalk を作成する受信および送信パイプラインです。 「逆アセンブル」カスタム受信パイプラインのステージの SWIFT の逆アセンブラーを使用することができます。 同様に、カスタム送信パイプラインで"をアセンブル"ステージの SWIFT アセンブラーを使用することができます。 呼び出すには、SWIFT 逆アセンブラーまたはアセンブラー パイプライン デザイナーのツールボックスは、パイプライン デザイナー キャンバスに逆アセンブラーまたはアセンブラー対応するパイプラインのステージにドラッグします。 逆アセンブラーまたはアセンブラーの呼び出しについての詳しい手順については、「[第 3 章: パイプライン プロジェクトを追加する](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md)、エンド ツー エンド チュートリアル」でします。 詳細については、パイプライン デザイナーまたはパイプライン プロジェクトでの作業では、BizTalk Server ヘルプを参照してください。  
  
 仕様では、SWIFT の逆アセンブラーである「逆アセンブル」ステージが必要ですが、*最終*呼び出される受信パイプラインのステージ。 すべての後続のステージを使用すると、予期しない動作 (後続のステージを呼び出していない、このような逆アセンブラーや逆アセンブラーが以前設定と、メッセージ ボックスに、メッセージを発行する前に昇格されたコンテキスト プロパティを削除します。データベースの場合)。 SWIFT アセンブラー"をアセンブル"ステージをするが必要ですが、同様に、*最初*送信パイプラインのステージ。 前のステージを使用すると、SWIFT アセンブラーによって動的なメッセージの種類の探索が損なわれる可能性があります。  
  
 それらを使用するパイプライン デザイナー ツールボックス最初の時刻に SWIFT 逆アセンブラおよびアセンブラを手動で追加する必要があります。 これを行うための手順の詳細については[第 3 章: パイプライン プロジェクトを追加する](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md)エンド ツー エンド チュートリアル」でします。 手動で追加すると、ツールボックスに表示するには、コンポーネントが続行されます (手動で削除するまで、またはアンインストールする[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)])。  
  
## <a name="see-also"></a>参照  
 [SWIFT 逆アセンブラーおよびアセンブラーの操作](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)