---
title: 有効化または BAM の追跡を無効化 |Microsoft ドキュメント
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
ms.openlocfilehash: c1132c41e9a017e42139d988d1588f79d7d3afaa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207394"
---
# <a name="enabling-or-disabling-bam-tracking"></a>有効にするか、BAM 追跡を無効にします。
有効にするにまたは BAM Message Repair and 新しい転送プロセスでは、トランザクションを持つプロセスの中であっても、任意の時点では、追跡を無効にすることができます。 ただし、トランザクションは、プロセス中に BAM の追跡を無効にする場合、BAM データできない可能性がありますこれらのトランザクションの完了します。 このような場合、履歴テーブルにはまだすべてのインスタンスの正確なデータが含まれます。  
  
 有効化または BAM A4SWIFT コンポーネント構成プロセスの一部として追跡を無効にする方法については、次を参照してください。 [A4SWIFT のプロパティの設定](../../adapters-and-accelerators/accelerator-swift/setting-a4swift-properties.md)です。  
  
### <a name="to-enable-or-disable-bam-tracking"></a>有効にするにまたは BAM の追跡を無効にするには  
  
1.  プロファイル Web クライアントを右クリックして**BizTalk Accelerator 用 SWIFT**をクリックしてコンソール ツリーで、**プロパティ**です。  
  
2.  グローバル プロパティ ダイアログ ボックスで、BAM の選択を解除して追跡を無効にする**BAM の追跡を有効にする**、または BAM を選択して追跡を有効にします。  
  
3.  **[OK]** をクリックします。  
  
4.  BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、 **BizTalk グループ**、し**プラットフォームの設定**です。 をクリックして**のホスト インスタンスの**します。  
  
5.  詳細ウィンドウで、ホスト インスタンスを右クリックし、をクリックして**再起動**です。  
  
## <a name="see-also"></a>参照  
 [A4SWIFT のプロパティの設定](../../adapters-and-accelerators/accelerator-swift/setting-a4swift-properties.md)