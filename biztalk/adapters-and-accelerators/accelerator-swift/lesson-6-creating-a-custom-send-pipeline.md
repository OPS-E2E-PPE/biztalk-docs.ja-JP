---
title: 'レッスン 6: 作成、カスタム送信パイプライン |Microsoft Docs'
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
ms.openlocfilehash: 12afba9368554dc85cf57658f674a088db7580d2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973723"
---
# <a name="lesson-6-creating-a-custom-send-pipeline"></a>レッスン 6: カスタム送信パイプラインを作成します。
このレッスンでは、BizTalk パイプライン デザイナを使用して、カスタム送信パイプラインを作成します。 送信パイプラインは、前に、メッセージで実行するパイプライン[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]が宛先にメッセージを送信します。  
  
 SWIFT アセンブラー (ASM) コンポーネントを使用するカスタム パイプラインを構成します。 ASM は、XML 形式のメッセージを取得に変換したり、SWIFT のフラット ファイルにコンテンツをシリアル化します。 この変換はで作成した MT103 スキーマに基づいて[レッスン 3: カスタム受信パイプラインを追加する](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md)します。  
  
### <a name="to-create-a-custom-send-pipeline"></a>カスタム送信パイプラインを作成するには  
  
1. ソリューション エクスプ ローラーで右クリックし、 **SWIFTPipelines**プロジェクトをポイントして、**追加**、 をクリックし、**新しい項目の**。  
  
2. 追加する新しい項目の SWIFTPipelines ダイアログ ボックスであることを確認**パイプライン ファイル**がカテゴリ ウィンドウで選択され、**送信パイプライン**テンプレート ペインから。  
  
3. **名前**ボックスに「 **MT103SendPipeline.btp**します。  
  
4. クリックして**追加**に BizTalk パイプライン デザイナで、空のパイプラインを開きます。  
  
   > [!NOTE]
   >  BizTalk パイプライン デザイナーで空のパイプラインが表示されます。 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] ソリューション エクスプ ローラーに SWIFTPipelines プロジェクトの下の新しいパイプラインを追加します。  
  
   続行する[レッスン 7: SWIFT アセンブラーをカスタムに追加する送信パイプライン](../../adapters-and-accelerators/accelerator-swift/lesson-7-adding-the-swift-assembler-to-a-custom-send-pipeline.md)します。