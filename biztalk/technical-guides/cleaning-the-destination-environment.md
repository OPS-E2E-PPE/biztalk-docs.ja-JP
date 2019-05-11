---
title: 移行先の環境のクリーニング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8585853b-e625-48c3-a241-81ebf1be0e1e
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd24df50cd4c29dacbd9f8830f6851abdb8ed354
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397060"
---
# <a name="cleaning-the-destination-environment"></a>移行先の環境のクリーニング
復元ジョブには、解決できないエラー条件が発生すると、空の環境から起動できるように、移行先の環境をクリーニングします。 ストアド プロシージャを実行している**sp_LogShippingClean** 、変換先の master データベースにある[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスが「クリーン」送信先の環境。 この手順では、すべてのデータベースを削除し、指定されたソースの最後に復元されたデータ セットを削除します。  
  
 この手順を実行する前に無効にする、 **BTS ログの配布 - データベースの復元**ジョブ (get のバックアップ履歴 ジョブは実行し続けます)。 無効化の詳細については、 **BTS ログの配布 - データベースの復元**ジョブを参照してください[Backup BizTalk Server ジョブでデータベースを復元する方法](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)します。 後に、 **sp_LogShippingClean**プロシージャが実行されて、次回、復元ジョブの実行時に有効な後続のログのバックアップ セットの設定、最新の完全バックアップが検出されます。 このセットが既に復元されている場合、復元ジョブをクリア、**リストア**設定および後続のすべての列を設定し、セットの復元を続行します。  
  
> [!NOTE]  
>  設定、環境がクリーニングした後、最新の完全バックアップ ジョブを検索するため、この手順を実行した後、復元ジョブを実行する前に、ソース システム上完全バックアップを強制します。  
  
> [!NOTE]  
>  **Sp_LogShippingClean**別のサーバーでは、適用されているセットという観点からの同期を保つために、指定したソース システムのデータベースの復元はすべてのサーバー上での手順を繰り返す必要があります。  
  
 実行する、 **sp_LogShippingClean**プロシージャでは、すべてのマスター データベースに接続[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスのディザスター リカバリーの一部であるサイトし、では、次のコマンドを実行、**新しいクエリ**オプションで使用できる[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]各 Management Studio[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス。  
  
```  
sp_LogShippingClean 'SourceID'  
```  
  
 場所**SourceID** 、運用環境で構成されている識別子に対応する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス。  
  
## <a name="see-also"></a>参照  
 [ログ配布のトラブルシューティング](../technical-guides/troubleshooting-log-shipping.md)