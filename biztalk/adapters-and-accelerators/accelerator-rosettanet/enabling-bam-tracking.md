---
title: BAM の追跡を有効にする |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM tracking, enabling
- BAM tracking, disabling
ms.assetid: 3fee3315-fba7-4eea-89f3-6a061b450bb8
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3098fa81b9fa88c884eb556a31481ac1ac57c51
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283766"
---
# <a name="enabling-bam-tracking"></a>BAM 追跡を有効にします。
[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] では、BizTalk アクティビティ監視 (BAM) を使用した拡張追跡機能をサポートしています。 BTARN 構成のグローバル プロパティの一部として追跡を有効にします。 追跡を有効にすると、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] はすべてのアグリーメントに対するメッセージを追跡します。 既定では追跡が有効になっています。  
  
 追跡の詳細については、次を参照してください。[拡張追跡](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md)します。  
  
### <a name="to-enable-or-disable-bam-tracking"></a>BAM の追跡を有効または無効にするには  
  
1. クリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、順にクリックします[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**.  
  
2. 右クリックし、[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]スコープ ウィンドウで、およびクリック ノード**プロパティ**します。  
  
3. **グローバル プロパティ**ダイアログ ボックスで、 **BAM の追跡を有効にする**追跡を有効または無効にするには、このオプションをオフにします。  
  
> [!IMPORTANT]
>  有効フラグを変更して追跡を有効または無効にした場合は、常に、パブリック処理と HTTP アダプターが実行されているすべてのサービスを再開する必要があります。 この再開には、ホスト サービスと分離ホスト サービスが含まれます。  
  
## <a name="see-also"></a>参照  
 [構成、証明書、データベース、およびセキュリティを管理します。](manage-configuration-certificates-databases-security.md)   
 [拡張追跡](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md)   
 [BTARN 構成の管理](../../adapters-and-accelerators/accelerator-rosettanet/administering-the-btarn-configuration.md)