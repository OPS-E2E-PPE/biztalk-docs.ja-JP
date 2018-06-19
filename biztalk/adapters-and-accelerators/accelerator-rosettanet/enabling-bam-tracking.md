---
title: BAM 追跡の有効化 |Microsoft ドキュメント
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
ms.openlocfilehash: 90fae70edf7f748de3790aeaa9e13e3381c44c48
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210058"
---
# <a name="enabling-bam-tracking"></a>BAM 追跡を有効にします。
[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] では、BizTalk アクティビティ監視 (BAM) を使用した拡張追跡機能をサポートしています。 BTARN 構成のグローバル プロパティの一部として追跡を有効にします。 追跡を有効にすると、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] はすべてのアグリーメントに対するメッセージを追跡します。 既定では追跡が有効になっています。  
  
 追跡の詳細については、次を参照してください。[追跡強化](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md)です。  
  
### <a name="to-enable-or-disable-bam-tracking"></a>BAM の追跡を有効または無効にするには  
  
1.  をクリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、順にクリック[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**.  
  
2.  右クリックし、[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]ノードをクリックしてスコープ ペイン**プロパティ**です。  
  
3.  **グローバル プロパティ**ダイアログ ボックスで、 **BAM の追跡を有効にする**の追跡を有効または無効にするには、このオプションをオフにします。  
  
> [!IMPORTANT]
>  有効フラグを変更して追跡を有効または無効にした場合は、常に、パブリック処理と HTTP アダプターが実行されているすべてのサービスを再開する必要があります。 この再開には、ホスト サービスと分離ホスト サービスが含まれます。  
  
## <a name="see-also"></a>参照  
 [構成、証明書、データベース、およびセキュリティを管理します。](manage-configuration-certificates-databases-security.md)   
 [拡張追跡](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md)   
 [BTARN 構成の管理](../../adapters-and-accelerators/accelerator-rosettanet/administering-the-btarn-configuration.md)