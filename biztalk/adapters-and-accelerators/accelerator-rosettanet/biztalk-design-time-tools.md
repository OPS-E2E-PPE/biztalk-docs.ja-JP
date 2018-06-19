---
title: BizTalk のデザイン時ツール |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Adapter Framework
- schemas, tools
- BizTalk Orchestration Designer
- schemas, BTARN schemas
- BizTalk Editor
- BizTalk Mapper
- tools, schemas
- BTARN, schemas
- BizTalk Pipeline Designer
ms.assetid: a981e167-f178-4fef-be0e-02fa15feffc2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f259167112ab87da5af14ca73f735ae38d8789e
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006633"
---
# <a name="biztalk-design-time-tools"></a>BizTalk のデザイン時ツール
作業する開発者[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] BizTalk Server に組み込まれたデザイン時ツールのセットを使用できます。 これらのツールが組み込ま[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]です。 詳細については[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ツールを参照してください[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Server のヘルプします。  
  
## <a name="biztalk-editor"></a>BizTalk エディター  
 BizTalk エディターを使用して管理する[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]RosettaNet Partner Interface Process (Pip) に基づく XSD スキーマです。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]ソリューション開発の次のスキーマがインストールされます。  
  
-   0A1_FailureNotificationPropertySchema.xsd  
  
-   0A1_MS_V02_00_FailureNotification.xsd  
  
-   0A1_V1_FailureNotificationMessageGuideline.xsd  
  
-   0C1_MS_R01_02_AsynchronousTestNotification.xsd  
  
-   0C2_MS_R01_02_AsynchronousTestConfirmation.xsd  
  
-   0C2_MS_R01_02_AsynchronousTestRequest.xsd  
  
-   0C3_MS_R01_02_SynchronousTestNotification.xsd  
  
-   0C4_MS_R01_02_SynchronousTestQuery.xsd  
  
-   0C4_MS_R01_02_SynchronousTestResponse.xsd  
  
-   2A12_MS_V01_03_ProductMasterNotification.xsd  
  
-   3A2PriceAndAvailabilityQueryMessageGuideline_v1_3.xsd  
  
-   3A2PriceAndAvailabilityResponseMessageGuideline_v1_3.xsd  
  
-   3A4_MS_V02_02_PurchaseOrderConfirmation.xsd  
  
-   3A4_MS_V02_02_PurchaseOrderRequest.xsd  
  
 これらのスキーマは、「 \<*ドライブ*\>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<バージョン\>Accelerator for rosettanet \sdk\schemas です。  
  
 複数のスキーマを追加するには、RosettaNet の Web サイトから Pip をダウンロードして[http://go.microsoft.com/fwlink/?linkid=33859](http://go.microsoft.com/fwlink/?linkid=33859)です。 詳細については、次を参照してください。[新しい Partner Interface Process の組み込み](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md)です。  
  
## <a name="biztalk-mapper"></a>BizTalk マッパー  
 BizTalk マッパーを使用して、データ変換を定義するマップの作成やカスタマイズを行います。 また、インバウンドおよびアウトバウンドの両方の RosettaNet メッセージの種類に対する変換をマップします。  
  
## <a name="biztalk-orchestration-designer"></a>BizTalk オーケストレーション デザイナ  
 BizTalk オーケストレーション デザイナを使用して、ビジネス プロセスの設計および実装を行います。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK で提供されているプライベート プロセスをカスタマイズできます。 詳細については、次を参照してください[プライベート プロセス &#91;。RN3 &#93;](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)と[プライベート プロセス &#91; のカスタマイズRN3 &#93;](../../adapters-and-accelerators/accelerator-rosettanet/customizing-private-processes.md). パブリック プロセスはカスタマイズできません。パブリック プロセスをカスタマイズすると、RosettaNet 準拠ではなくなります。  
  
## <a name="biztalk-pipeline-designer"></a>BizTalk パイプライン デザイナ  
 BizTalk パイプライン デザイナを使用して、メッセージ処理手順を定義して関連付けるパイプラインを作成および構成します。 パイプラインは、メッセージ処理をステージに分割し、作業の各カテゴリを実行する順序を決定します。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK には、受信用および送信用の 2 つの RNIF (RosettaNet Implementation Framework) パイプラインが含まれています。 詳細については、次を参照してください。 [RNIF パイプライン](../../adapters-and-accelerators/accelerator-rosettanet/rnif-pipelines.md)です。  
  
## <a name="biztalk-adapter-framework"></a>BizTalk アダプタ フレームワーク  
 BizTalk アダプタ フレームワークとエンドポイント アダプタを使用して、パートナーおよびアプリケーションを統合します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server および BTARN のツールおよび機能](../../adapters-and-accelerators/accelerator-rosettanet/tools-and-features-of-biztalk-server-and-btarn.md)   
 [管理およびランタイム ツール](../../adapters-and-accelerators/accelerator-rosettanet/administration-and-run-time-tools.md)   
 [分析ツール](../../adapters-and-accelerators/accelerator-rosettanet/analysis-tools1.md)   
 [新しい Partner Interface Process の組み込み](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md)