---
title: バックアップ ファイルが破損 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc48197c-944a-4f0a-ba01-8e1d91c88ad3
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fda5acae756fd2c4d0afc0263bc723af3ba77e15
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299634"
---
# <a name="corrupt-backup-files"></a>バックアップ ファイルが壊れています
バックアップ ファイルには、破損している、壊れているか、または不足している可能性がありますになります。 このような場合に、少なくとも 1 つのファイルは復元できません。 エラーがあって、システム上の復元ジョブは、[次へ] の有効な完全バックアップ セットを検索します。 ほとんどの場合、ソース システム上の完全バックアップを強制する必要があります。 このようなセットが存在しない場合、復元ジョブが失敗して、以降の実行ごとは、有効な完全バックアップ セットが到着するまでにも失敗します。 セットが存在する場合、環境を修復に使用されます。  
  
> [!NOTE]  
>  方式により[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]可能であれば、ファイルにバックアップ データを書き込みますを[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データの実際の書き込み中にバックアップが失敗した場合でも正常に完了が報告されます。 このシナリオでは、ディスクに書き込まれているが、コンピューターおよびネットワークの障害にローカルでないまたは中断が発生したときに、主に発生します。 一般的な予防策として、バックアップ ジョブの実行中に、ネットワーク障害が発生する場合強制的に完全バックアップ ネットワーク接続の問題が解決された後です。  
  
## <a name="see-also"></a>参照  
 [ログ配布のトラブルシューティング](../technical-guides/troubleshooting-log-shipping.md)