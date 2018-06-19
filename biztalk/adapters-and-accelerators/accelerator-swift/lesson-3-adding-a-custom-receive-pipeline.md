---
title: 'レッスン 3: カスタム受信パイプラインを追加する |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, creating custom pipelines
- custom pipelines
ms.assetid: 1917b8e2-4f1c-4c20-abe4-ea18a406eeeb
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76abee50cce743dde6c62ea078f5ef9dada0c998
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210010"
---
# <a name="lesson-3-adding-a-custom-receive-pipeline"></a>レッスン 3: カスタム受信パイプラインを追加します。
このレッスンでは、BizTalk パイプライン デザイナを使用してカスタム受信パイプラインを作成します。 カスタム受信パイプラインは、アダプターがその前に、メッセージを受信した後のメッセージが実行されるパイプライン[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]メッセージ ボックス データベースに公開します。  
  
 SWIFT 逆アセンブラー (DASM) コンポーネントを使用してカスタム パイプラインを構成します。 SWIFT の逆アセンブラーでは SWIFT 形式のフラット ファイル、変換、または解析、XML ベースの表現に SWIFT メッセージの内容を[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を使用できます。  
  
 前の手順で追加した MT103 ランタイム スキーマ ([レッスン 2: プロジェクト参照を追加する](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-project-references.md)) 変換に使用される形式です。  
  
### <a name="to-create-a-new-custom-receive-pipeline"></a>新しいカスタム受信パイプラインを作成するには  
  
1.  ソリューション エクスプ ローラーで右クリックし、 **SWIFTPipelines**プロジェクトをポイントし、**追加**、順にクリック**新しい項目の**します。  
  
2.  追加新しい項目の SWIFTPipelines ダイアログ ボックスで、**パイプライン ファイル**カテゴリ ウィンドウで、選択**受信パイプライン**テンプレート ペインからです。  
  
3.  **名前**ボックスに、入力**MT103ReceivePipeline.btp**です。  
  
4.  をクリックして**追加**BizTalk パイプライン デザイナーで空白のパイプラインを開きます。  
  
 BizTalk パイプライン デザイナーで空のパイプラインが表示されます。 Visual Studio はまた、SWIFTPipelines プロジェクトの下で、ソリューション エクスプ ローラーに新しいパイプラインを追加します。  
  
 進みます[レッスン 4: SWIFT アセンブラーおよび逆アセンブラーをツールボックスに追加する](../../adapters-and-accelerators/accelerator-swift/lesson-4-adding-the-swift-assembler-and-disassembler-to-the-toolbox.md)です。