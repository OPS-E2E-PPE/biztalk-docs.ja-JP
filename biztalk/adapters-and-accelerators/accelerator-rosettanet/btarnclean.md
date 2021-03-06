---
title: BtarnClean |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BtarnClean utility
- assemblies, undeploying
- BTARN, deleting artifacts
- orchestrations, unenlisting
- ports, stopping
- orchestrations, stopping
- ports, deleting
- BTARN, BtarnClean utility
ms.assetid: fbecbb88-9b18-4b4b-a286-0bfa783f2320
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01c4524fd5ce633851b64fc07ea2891a389b4ef5
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752858"
---
# <a name="btarnclean"></a>BtarnClean
BtarnClean ユーティリティを使用して Microsoft® をクリーンアップする[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]アイテムをコンピューターから。 以下の処理が実行されます。  
  
- すべての [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] オーケストレーションを停止し、登録を解除する  
  
- 関連するすべてのポートを停止し、削除する  
  
- すべての Microsoft の展開解除します。Solutions.BTARN します。\*アセンブリ  
  
## <a name="location-in-sdk"></a>SDK でのパス  
 \<*ドライブ*\>\Program Files (x86) \ Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk  
  
## <a name="running-btarnclean"></a>BtarnClean の実行  
  
#### <a name="to-run-btarnclean"></a>BtarnClean を実行するには  
  
1.  コマンド プロンプトを開きます。  
  
2.  移動\<*ドライブ*\>\ Program Files (x86) \Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\\します。  
  
3.  コマンド プロンプトで「 **BtarnClean**、し、ENTER キーを押します。  
  
     コマンドの実行を確認するプロンプトが表示されます。  
  
## <a name="remarks"></a>コメント  
 他のアイテムに依存する BizTalk アイテムのあるコンピューターで BtarnClean ユーティリティを実行しようとすると、そのアイテムは削除できないというメッセージが表示されます。 該当するアイテムはそのままで、引き続きその他のアイテムが削除されます。 依存関係を削除した後で、ユーティリティを再度実行できます。  
  
 複数コンピュータ展開の一部であるコンピュータで BtarnClean ユーティリティを実行した場合、アイテムを削除すると、同じ展開のその他のサーバーにも影響が及びます。  
  
 開発者によって作成された複数のプロセスが存在する場合に BtarnClean ユーティリティを実行すると、使用中のプロセスは削除されません。  
  
 ユーザーのアイテムが主要な受信場所を使用する場合、BtarnClean ユーティリティではその受信場所は削除されません。 その場合は、受信ポートを削除する必要があります。  
  
 このユーティリティを実行した後で [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] の構成を解除する場合は、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] フォルダーから Configuration.exe /u を実行します。  
  
## <a name="see-also"></a>参照  
 [ユーティリティ](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)
