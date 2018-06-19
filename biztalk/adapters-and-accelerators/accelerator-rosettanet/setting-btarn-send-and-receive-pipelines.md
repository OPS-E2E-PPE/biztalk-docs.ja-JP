---
title: BTARN 送信を設定し、受信パイプライン |Microsoft ドキュメント
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
ms.openlocfilehash: a6f5e996b7046e94c90df0269381391a3aed3084
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964512"
---
# <a name="setting-btarn-send-and-receive-pipelines"></a>BTARN 送信を設定し、受信パイプライン
既定では、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]標準を使用して[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]送信パイプライン (Microsoft.Solutions.BTARN.Pipelines.Send) と標準[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]を作成するときに、受信パイプライン (Microsoft.Solutions.BTARN.Pipelines.Receive)パートナー送信ポート。 ただし、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 構成を変更して、既存の BizTalk パイプラインまたは作成したカスタム パイプラインを使用することもできます。 すべての取引先アグリーメント、およびすべてのパートナーとホーム組織は、同じ送信パイプラインと同じ受信パイプラインを使用します。  
  
 最初に、パートナーを作成するときに[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]非同期のいずれかを使用するには、そのパートナーに対して 2 つの送信ポートを作成し、1 つの同期: \<*パートナー名*\>です。非同期の送信ポートと\<*パートナー名*\>です。同期送信ポートです。 これらの送信ポートは、既定で標準の [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 送信パイプラインに設定され、同期送信ポート受信パイプラインは、既定で標準の [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 受信パイプラインに設定されます。  
  
> [!NOTE]
>  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理コンソールで [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] パイプラインを変更すると、BizTalk エクスプローラーで直接変更したプロパティがリセットされる場合があります。  
  
### <a name="to-change-the-send-or-receive-pipeline-that-btarn-uses"></a>BTARN が使用する送信パイプラインまたは受信パイプラインを変更するには  
  
1.  をクリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、順にクリック[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**.  
  
2.  BTARN 管理コンソールを右クリックし、[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]ノードをクリックして**プロパティ**です。  
  
3.  グローバル プロパティ ダイアログ ボックスで、ドロップダウン リストから、別のパイプラインを選択し、をクリックして**OK**です。  
  
4.  **ホスト インスタンス**ノードの下、 [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**ノードが停止してから、ホストを再起動します。  
  
    > [!NOTE]
    >  パイプラインの変更は、BizTalk Server を再起動することにより初めて有効になります。  
  
## <a name="see-also"></a>参照  
 [構成、証明書、データベース、およびセキュリティを管理します。](manage-configuration-certificates-databases-security.md)   
 [BAM の追跡を有効にする](../../adapters-and-accelerators/accelerator-rosettanet/enabling-bam-tracking.md)