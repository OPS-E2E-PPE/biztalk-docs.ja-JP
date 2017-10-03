---
title: "展開先の環境をクリーンアップ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8585853b-e625-48c3-a241-81ebf1be0e1e
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4023492bf79223b3ba6b1db5cedebadf88feb9c4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="cleaning-the-destination-environment"></a>展開先の環境のクリーンアップ
復元ジョブには、解決できないエラーが発生すると、空の環境からそれを開始するために、送信先の環境をクリーンアップします。 ストアド プロシージャを実行している**sp_LogShippingClean** 、変換先の master データベースにある[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスは「クリーンアップ」送信先の環境。 この手順では、すべてのデータベースを削除し、指定されたソースの最後に復元されたデータ セットを削除します。  
  
 この手順を実行する前に無効にする、 **BTS ログの配布 - データベースの復元**ジョブ (get 履歴のバックアップ ジョブは実行し続けます)。 無効化の詳細については、 **BTS ログの配布 - データベースの復元**ジョブを参照してください[BizTalk Server のバックアップ ジョブでデータベースを復元する方法](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)です。 後に、 **sp_LogShippingClean**プロシージャが実行されて、次回、復元ジョブの実行時に、最新の完全バックアップ セット以降、有効なログのバックアップ セットが検出されます。 このセットが既に復元されている場合、復元ジョブをクリア、**リストア**設定および後続のすべての列を設定し、セットを復元する処理を実行し、します。  
  
> [!NOTE]  
>  環境が消去された後に設定、最新の完全バックアップ ジョブを検索するため強制的に完全バックアップ元システムでこの手順を実行した後は、復元ジョブを実行する前にします。  
  
> [!NOTE]  
>  **Sp_LogShippingClean**さまざまなサーバーの設定が適用されているという観点から、相互に同期を保つために、指定したソース システムのデータベースの復元は、すべてのサーバー上の手順を繰り返す必要があります。  
  
 実行する、 **sp_LogShippingClean**プロシージャ、すべての master データベースに接続[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]、障害回復の一部であるインスタンスがサイトし、では、次のコマンドを実行、**新しいクエリ**オプションで使用できる[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ごとの Management Studio[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス。  
  
```  
sp_LogShippingClean 'SourceID'  
```  
  
 ここで**SourceID**運用環境で構成されている識別子に対応する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス。  
  
## <a name="see-also"></a>参照  
 [ログ配布のトラブルシューティング](../technical-guides/troubleshooting-log-shipping.md)