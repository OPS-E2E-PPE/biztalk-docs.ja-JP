---
title: BTARN 送信の設定および受信パイプライン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send pipelines, modifying
- modifying, send pipelines
- receive pipelines, modifying
- modifying, receive pipelines
ms.assetid: 00960de0-3763-40aa-9e4b-1fedc7f1eea6
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c195747a5c5501a3ac9ef57602f5bbdd5e0c0bfc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281830"
---
# <a name="setting-btarn-send-and-receive-pipelines"></a>BTARN 送信の設定および受信パイプライン
既定では、Microsoft によって[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]標準を使用して[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]送信パイプライン (Microsoft.Solutions.BTARN.Pipelines.Send) と標準[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]パートナーを作成するときに、パイプライン (Microsoft.Solutions.BTARN.Pipelines.Receive) を受信送信ポート。 ただし、変更、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]既存の BizTalk パイプラインまたは作成したカスタム パイプラインを使用するよう構成します。 すべての取引先アグリーメント、およびすべてのパートナーとホーム組織は、使用して、同じ送信パイプラインと、同じ受信パイプライン。  
  
 最初に、パートナーを作成するときに[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]非同期のいずれかを使用するには、そのパートナーに対して 2 つの送信ポートを作成します。 もう 1 つの同期: \<*パートナー名*\>します。非同期の送信ポートと\<*パートナー名*\>します。同期送信ポートです。 標準にこれらの送信ポートは、既定[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]送信パイプライン、および同期送信ポートの受信パイプライン既定値は、標準[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]受信パイプライン。  
  
> [!NOTE]
>  変更、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]でパイプライン、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理コンソールは、BizTalk エクスプ ローラーで直接変更したプロパティをリセット可能性があります。  
  
### <a name="to-change-the-send-or-receive-pipeline-that-btarn-uses"></a>BTARN を使用するパイプラインの受信を送信を変更するには  
  
1. クリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、順にクリックします[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**.  
  
2. BTARN 管理コンソールで、右クリックし、[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]ノード、およびクリック**プロパティ**します。  
  
3. グローバル プロパティ ダイアログ ボックスで、ドロップダウン リストから別のパイプラインを選択し、 **OK**します。  
  
4. **ホスト インスタンス**ノードの下、 [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**ノードが停止して、ホストを再起動します。  
  
   > [!NOTE]
   >  BizTalk Server を再起動する場合と、パイプラインの変更が反映のみ。  
  
## <a name="see-also"></a>参照  
 [構成、証明書、データベース、およびセキュリティを管理します。](manage-configuration-certificates-databases-security.md)   
 [BAM の追跡を有効にする](../../adapters-and-accelerators/accelerator-rosettanet/enabling-bam-tracking.md)