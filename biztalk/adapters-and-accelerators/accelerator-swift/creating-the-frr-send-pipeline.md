---
title: 送信パイプラインの作成、FRR |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FRR, creating send pipelines
- creating, send pipelines
- send pipelines, creating
ms.assetid: c6cd2047-ea53-425f-80cc-b02a1deb5292
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 971fde4a2f0f743574e60911dcb091a325efd079
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378342"
---
# <a name="creating-the-frr-send-pipeline"></a>FRR 送信パイプラインを作成します。
FIN Response Reconciliation を実行するには、SWIFT アセンブラーに加え、SWIFTAsmFrrMQSeriesHelper パイプライン コンポーネントを含む送信パイプラインを作成する必要があります。  

 **まとめ**  

 次の段階では、送信パイプラインを作成します。  

|ステージ|コンポーネント|  
|-----------|---------------|  
|アセンブル ステージ|SWIFT アセンブラー|  
|エンコード ステージ|SWIFT Frr MQSeries の送信コンポーネント|  

### <a name="to-create-a-custom-send-pipeline-for-frr"></a>FRR 用カスタム送信パイプラインを作成するには  

1. ソリューション エクスプ ローラーの Visual Studio で、パイプライン プロジェクトを右クリックして**追加**、 をクリックし、**新しい項目の**します。  

2. 新しい項目の追加 ダイアログ ボックスで、**送信パイプライン**テンプレート ペインから。  

3. **名前**など、受信パイプラインの名前を入力ボックスに、 **FRRSendPipeline.btp**します。 **[追加]** をクリックします。  

4. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、 をクリックして**ビュー**し**ツールボックス**します。  

5. BizTalk パイプライン コンポーネントのツールボックスからドラッグ**SWIFT アセンブラー**を**ここにドロップ**下のボックス、**アセンブル**で図形をステージ**BizTalk パイプラインデザイナー**します。  

6. BizTalk パイプライン コンポーネントのツールボックスからドラッグ**SWIFT Frr MQSeries の送信コンポーネント**を**ここにドロップ**下のボックス、**エンコード**で図形をステージ**BizTalk パイプライン デザイナ**します。  

7. BizTalk エクスプ ローラーで、パイプライン プロジェクトを右クリックして**Undeploy**、順にクリックします**はい**します。  

   > [!NOTE]
   >  展開解除して、パイプライン プロジェクトを再デプロイし後、は、送信ポートをリセットか、以前に配置されたプロジェクトでパイプラインを使用する受信場所必要があります。  

8. ソリューション エクスプ ローラーで、パイプライン プロジェクトを右クリックし をクリックし、**ビルド**します。  

9. ビルドが成功した後、パイプライン プロジェクトを右クリックし、**デプロイ**します。
