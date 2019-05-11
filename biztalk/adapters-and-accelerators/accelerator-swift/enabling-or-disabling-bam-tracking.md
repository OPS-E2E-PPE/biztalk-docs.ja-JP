---
title: 有効化または BAM の追跡を無効にする |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Message Repair and New Submission, BAM tracking
- BAM tracking
ms.assetid: 07896fab-88a0-4759-8547-16edcd1eebc0
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f44f8d6add5eed56182a68b881e4019e2ca214a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377980"
---
# <a name="enabling-or-disabling-bam-tracking"></a>有効化または BAM の追跡を無効にします。
有効または BAM Message Repair and 新しい転送プロセスでは、トランザクションを持つプロセスの中であっても、任意の時点では、追跡を無効にすることができます。 ただし、トランザクションは、プロセス中に BAM の追跡を無効にした場合、BAM データできない可能性がありますそれらのトランザクションを完了します。 このような場合、履歴テーブルには引き続きすべてのインスタンスの正確なデータが含まれます。  
  
 有効化または BAM A4SWIFT コンポーネント構成プロセスの一部として追跡を無効にする方法については、次を参照してください。 [A4SWIFT プロパティの設定](../../adapters-and-accelerators/accelerator-swift/setting-a4swift-properties.md)します。  
  
### <a name="to-enable-or-disable-bam-tracking"></a>有効にするか、BAM 追跡を無効にするには  
  
1.  プロファイルの Web クライアントで右クリック**BizTalk Accelerator for SWIFT**コンソール ツリーをクリックで**プロパティ**します。  
  
2.  グローバル プロパティ ダイアログ ボックスで、BAM の選択を解除して追跡を無効にする**BAM の追跡を有効にする**、または BAM を選択して追跡を有効にします。  
  
3.  **[OK]** をクリックします。  
  
4.  BizTalk Server 管理コンソールで  **BizTalk Server 管理**、 **BizTalk グループ**、し**プラットフォームの設定**します。 クリックして**インスタンスをホスト**します。  
  
5.  詳細ペインで、ホスト インスタンスを右クリックし、**再起動**します。  
  
## <a name="see-also"></a>参照  
 [A4SWIFT プロパティの設定](../../adapters-and-accelerators/accelerator-swift/setting-a4swift-properties.md)