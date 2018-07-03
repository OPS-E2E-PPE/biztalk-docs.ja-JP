---
title: 破損したバックアップ ファイル |Microsoft Docs
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
ms.openlocfilehash: 5947b527dea1206255daf52f128569fd7a4f659c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987915"
---
# <a name="corrupt-backup-files"></a>バックアップ ファイルが壊れています
バックアップ ファイルは、破損している、壊れているか、または不明になる可能性があります。 このような場合は、少なくとも 1 つのファイルを復元できません。 エラーを検出しました。 システム上の復元ジョブは、[次へ] の有効な完全バックアップ セットを検索します。 ほとんどの場合、ソース システムの完全バックアップを強制する必要があります。 そのようなセットが存在しない場合は、復元ジョブは失敗し、有効な完全バックアップ セットが到着するまでにもそれぞれ後続の実行が失敗しました。 セットが存在する場合、環境を修復に使用されます。  
  
> [!NOTE]
>  方法により[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ことは、ファイルにバックアップ データを書き込みますを[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データの実際の書き込み中にバックアップが失敗した場合でも正常に完了が報告されます。 このシナリオは、主に、ディスクに書き込まれる、ローカル コンピューターとネットワークの障害にまたは中断が発生した場合に発生します。 一般的な念のため、バックアップ ジョブの実行中に、ネットワーク障害が発生した場合完全バックアップを強制、ネットワーク接続の問題が解決された後です。  
  
## <a name="see-also"></a>参照  
 [ログ配布のトラブルシューティング](../technical-guides/troubleshooting-log-shipping.md)