---
title: '手順 1: 構成して、受信ポートの有効化、BatchControlPort |Microsoft ドキュメント'
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
ms.openlocfilehash: d50289924062268db078844f2b3d2eaaccda23a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206146"
---
# <a name="step-1-configure-and-enable-the-batchcontrolport-receive-port"></a>手順 1: 構成して、受信ポートの有効化、BatchControlPort
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) セットアップは、受信ポートを作成、バッチ コントロール ポート、開始するには、バッチ オーケストレーションを使用するメッセージを処理するバッチの終了、および時間。 これらのメッセージには、バッチのアクティベーションには、バッチの終了、タイマー メッセージをバッチ処理が含まれます。 このステップでは、バッチ コントロール ポートの受信パイプラインを構成し、ポートを有効にします。  
  
### <a name="to-configure-and-enable-batchcontrolport"></a>構成して BatchControlPort を有効にするには  
  
1.  開始**BizTalk Server 管理**です。  
  
2.  BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、 **BizTalk グループ**、**アプリケーション**、および**BizTalk アプリケーション1**です。 をクリックして**受信場所**です。  
  
3.  右クリック**BatchControlLocation**、クリックして**を無効にする**です。  
  
4.  右クリック**BatchControlLocation**、クリックして**プロパティ**です。  
  
5.  受信場所のプロパティ] ダイアログ ボックスの**受信パイプライン**[ **BTAHL72XPipelines.BTAHL72XReceivePipeline**です。をクリックして**OK**です。  
  
6.  BizTalk 管理コンソールで、右クリック**BatchControlLocation**、クリックして**を有効にする**です。  
  
 進みます[手順 2: バッチ オーケストレーションを有効にする](../../adapters-and-accelerators/accelerator-hl7/step-2-enable-the-batch-orchestration.md)です。