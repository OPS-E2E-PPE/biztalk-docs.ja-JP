---
title: 'レッスン 3: カスタム受信パイプラインを追加する |Microsoft Docs'
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
ms.openlocfilehash: a5238dac95df214a25c130369b134bc155212516
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993747"
---
# <a name="lesson-3-adding-a-custom-receive-pipeline"></a>レッスン 3: カスタム受信パイプラインを追加します。
このレッスンでは、BizTalk パイプライン デザイナを使用してカスタム受信パイプラインを作成します。 カスタム受信パイプラインは、アダプターが前に、メッセージを受信した後に、メッセージで実行されるパイプライン[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]メッセージ ボックス データベースに公開します。  
  
 SWIFT 逆アセンブラー (逆アセンブラー) コンポーネントを使用するカスタム パイプラインを構成します。 SWIFT 逆アセンブラーでは、SWIFT 形式のフラット ファイルと変換、または解析、SWIFT、XML ベースの表現では、メッセージの内容を[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]消費することができます。  
  
 前の手順で追加した MT103 ランタイム スキーマ ([レッスン 2: プロジェクト参照を追加する](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-project-references.md)) は、変換に使用する形式です。  
  
### <a name="to-create-a-new-custom-receive-pipeline"></a>新しいカスタム受信パイプラインを作成するには  
  
1. ソリューション エクスプ ローラーで右クリックし、 **SWIFTPipelines**プロジェクトをポイントして、**追加**、 をクリックし、**新しい項目の**。  
  
2. 追加する新しい項目の SWIFTPipelines ダイアログ ボックスで、**パイプライン ファイル**カテゴリ ウィンドウで選択し**受信パイプライン**テンプレート ペインから。  
  
3. **名前**ボックスに「 **MT103ReceivePipeline.btp**します。  
  
4. クリックして**追加**に BizTalk パイプライン デザイナで、空のパイプラインを開きます。  
  
   BizTalk パイプライン デザイナーで空のパイプラインが表示されます。 Visual Studio ではソリューション エクスプ ローラーに新しいパイプラインも SWIFTPipelines プロジェクトの下に追加します。  
  
   続行する[レッスン 4: SWIFT アセンブラーと逆アセンブラーをツールボックスに追加する](../../adapters-and-accelerators/accelerator-swift/lesson-4-adding-the-swift-assembler-and-disassembler-to-the-toolbox.md)します。