---
title: "RNIF メッセージの処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RosettaNet Implementation Framework (RNIF)
- RosettaNet, about RosettaNet
- RNIF
- RNIF, non-repudiation
- RNIF, BizTalk Accelerator for RosettaNet
- non-repudiation
- RNIF, about RNIF
- BizTalk Accelerator for RosettaNet, RNIF
- RosettaNet
ms.assetid: 994f15bc-765c-4220-8ab1-176919e9e821
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34ff8794c6dcc94571607207b4c13e9dd2bf54cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="rnif-message-processing"></a>RNIF メッセージの処理
RosettaNet 組織は、RNIF (RosettaNet Implementation Framework) 仕様でメッセージ交換を定義しています。 RNIF は、統合システムがメッセージを転送する方法を定義します。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]完全に新機能に追加する機能、RNIF 仕様を実装する[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]ネイティブ ボックスを提供します。  
  
 RNIF 通信は複雑です。 RNIF 処理を実行するパブリック プロセスには、さまざまな検証チェックと複雑なワークフロー ロジックが含まれます。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]この機能をネイティブに提供します。 そのため、RNIF ロジックを最初から開発したり保守することなく、RosettaNet 準拠システムを使用できます。  
  
## <a name="btarn-support-for-rnif"></a>BTARN の RNIF のサポート  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] では、RNIF の両方のバージョン、RNIF 1.1 と RNIF 2.0 (V02.00.01) をサポートしています。 RNIF 2.0 には、RNIF 1.1 でサポートされる機能に加え、暗号化、添付ファイル、および同期トランザクションを含む重要な機能が追加されています。 RNIF 2.0 には RNIF 1.1 との下位互換性はありません。  
  
> [!NOTE]
>  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] は、RosettaNet Ready RNIF 2.0 に準拠しています。  
  
 この 2 つのバージョンでは RosettaNet メッセージの定義方法が異なります。 異なるメッセージ コンテナの詳細については、次を参照してください。 [RNIF 規格](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md)です。  
  
 統合システムは、HTTP/HTTPS および SMTP; 経由で RNIF 転送を実行します。ただし、 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] HTTP、HTTPS のみを実装します。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]RNIF 1.1 での添付ファイルと同期トランザクションができませんでした。  
  
### <a name="non-repudiation"></a>否認不可  
 RNIF 規格には、否認不可の要件が盛り込まれています。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] によって送受信されるワイヤ形式のメッセージを送受信したことを法的に証明できるように、このメッセージを否認不可データベースに格納します。 このため、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] では、着信メッセージ用に [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Archive データベースの MessageStorageIn テーブルが、送信メッセージ用に同データベースの MessageStorageOut テーブルが使用されます。  
  
 プロセス構成プロファイルで、Service Content と受信確認に対して個別に否認不可要件を設定します。 一方または両方を設定した場合、**発信元とコンテンツの否認**と**否認不可のために必要な**オプション`True`、し[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]次のデータを格納します。  
  
|data|目次|  
|----------|--------------|  
|RecordID|格納されたメッセージ専用の一意の ID|  
|MessageCategory|要求 (0)、応答 (1)、またはシグナル (2)|  
|DestinationParty|送信先パーティの名前|  
|SourceParty|送信元パーティの名前|  
|PIPCode|PIP3A4 など|  
|PIPVersion|V02.00 など|  
|MessageContent|バイナリ形式のメッセージ|  
|MessageTrackingID|メッセージのメッセージ追跡 ID|  
|PIPInstanceID|プロセスの PIP インスタンス ID|  
  
## <a name="see-also"></a>参照  
 [BizTalk Server に BizTalk Accelerator for RosettaNet の追加](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md)   
 [PIP の実装](../../adapters-and-accelerators/accelerator-rosettanet/pip-implementation.md)