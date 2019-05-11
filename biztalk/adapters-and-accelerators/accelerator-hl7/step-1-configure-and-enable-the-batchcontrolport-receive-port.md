---
title: 手順 1:構成して有効にする BatchControlPort 受信ポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be248a05-e740-497a-b112-8ba3a57b020b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fdc4260109769fd025b33e6b14d8fd3465d4e0e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289119"
---
# <a name="step-1-configure-and-enable-the-batchcontrolport-receive-port"></a>手順 1:構成して有効にする BatchControlPort 受信ポート
Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) セットアップは、受信ポートを作成、バッチ コントロール ポートを開始するには、バッチ オーケストレーションを使用するメッセージを処理するバッチの停止、および時間。 これらのメッセージには、バッチのアクティベーションには、バッチの終了、タイマー メッセージ バッチにはが含まれます。 この手順では、バッチ コントロール ポートの受信パイプラインを構成し、ポートを有効にします。  
  
### <a name="to-configure-and-enable-batchcontrolport"></a>構成して BatchControlPort を有効にするには  
  
1. 開始**BizTalk Server 管理**します。  
  
2. BizTalk Server 管理コンソールで  **BizTalk Server 管理**、 **BizTalk グループ**、**アプリケーション**、および**BizTalk アプリケーション1**します。 クリックして**受信場所**します。  
  
3. 右クリック**BatchControlLocation**、 をクリックし、**を無効にする**します。  
  
4. 右クリックして**BatchControlLocation**、 をクリックし、**プロパティ**します。  
  
5. 受信場所のプロパティ ダイアログ ボックスでの**受信パイプライン**、 **BTAHL72XPipelines.BTAHL72XReceivePipeline**します。クリックして**OK**します。  
  
6. 右クリックし、BizTalk 管理コンソールで**BatchControlLocation**、 をクリックし、**を有効にする**します。  
  
   続行する[手順 2。バッチ オーケストレーションを有効にする](../../adapters-and-accelerators/accelerator-hl7/step-2-enable-the-batch-orchestration.md)します。