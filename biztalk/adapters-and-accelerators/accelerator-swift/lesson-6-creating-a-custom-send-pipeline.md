---
title: 'レッスン 6: カスタムを作成する送信パイプライン |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- custom pipelines
- send pipelines, custom pipelines
ms.assetid: 73a3a546-1e43-4b93-87d3-9bfb32685a57
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a82801b0084f2d1b82a2c25cfc0fa2a9f8f1376c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210162"
---
# <a name="lesson-6-creating-a-custom-send-pipeline"></a>レッスン 6: カスタムの送信パイプラインを作成します。
このレッスンでは、BizTalk パイプライン デザイナを使用して、カスタム送信パイプラインを作成します。 送信パイプラインは前に、のメッセージで実行するパイプライン[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]が宛先にメッセージを送信します。  
  
 SWIFT アセンブラー (ASM) コンポーネントを使用するカスタム パイプラインを構成します。 ASM は XML 形式のメッセージを受け取る変換や、SWIFT のフラット ファイルにコンテンツをシリアル化してください。 この変換はで作成した MT103 スキーマに基づいて[レッスン 3: カスタム受信パイプラインを追加する](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md)です。  
  
### <a name="to-create-a-custom-send-pipeline"></a>カスタム送信パイプラインを作成するには  
  
1.  ソリューション エクスプ ローラーで右クリックし、 **SWIFTPipelines**プロジェクトをポイントし、**追加**、順にクリック**新しい項目の**します。  
  
2.  追加新しい項目の SWIFTPipelines ダイアログ ボックスであることを確認**パイプライン ファイル**が選択されてカテゴリ ウィンドウで、**送信パイプライン**テンプレート ペインからです。  
  
3.  **名前**ボックスに、入力**MT103SendPipeline.btp**です。  
  
4.  をクリックして**追加**BizTalk パイプライン デザイナーで空白のパイプラインを開きます。  
  
    > [!NOTE]
    >  BizTalk パイプライン デザイナーで空のパイプラインが表示されます。 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーに SWIFTPipelines プロジェクトの下で、新しいパイプラインを追加します。  
  
 進みます[レッスン 7: カスタムに SWIFT アセンブラーを追加する送信パイプライン](../../adapters-and-accelerators/accelerator-swift/lesson-7-adding-the-swift-assembler-to-a-custom-send-pipeline.md)です。