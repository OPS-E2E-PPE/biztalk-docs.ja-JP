---
title: "障害復旧 SQL サーバーを準備する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 44b77fe8-393d-4781-b0b0-5b7f6e50a67b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47bd787fe5fa33a30f01bc37fd4988ab26db99d1
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="preparing-the-disaster-recovery-sql-servers"></a>障害復旧 SQL サーバーを準備します。
セットを作成します.[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース障害復旧サイトのインスタンス。 災害復旧を確実に[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース インスタンスが同じレベルの運用環境のパフォーマンスを提供できます[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース インスタンス、災害復旧[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]類似したデータベースのインスタンスを構成する必要がありますハードウェアとを実行している物理コンピューターの台数[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。 このシナリオでは、BizTalk Server の各実稼働用に構成されるログ配布で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]、対応するのには適用先のデータベース インスタンス[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース インスタンスの災害復旧サイトにします。  
  
 キーの BizTalk Server のログ配布の要件は、実稼働サイト データベース ファイルの格納場所にドライブ文字が、障害復旧サイトのデータベース ファイルの復元先でドライブ文字と一致しています。 その場合、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース ファイル グループにある G:\data 実稼働環境で、必要がある G:\data ディレクトリ (DR) を移行先サーバーで、または、復元は失敗します。  
  
 BizTalk Server のログ配布はサポートしていません、 **RESTORE WITH MOVE** [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コマンド。 このため、ことをお勧め、災害復旧サイトのデータベース インスタンス名が実稼働環境でデータベース インスタンスの名前に一致する (既定では、インスタンス名は、ファイル パスの一部)。 実行している災害復旧のコンピューターに対応するドライブ文字には、単にディレクトリを作成することもできます[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]できるように、**復元**操作で使用されるように、同じディレクトリ構造内のファイルを作成できます実稼働します。  
  
 作成[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]障害復旧サイトの障害復旧サイトへのフェールオーバーが必要なことすべてために必要なセキュリティ ログインできるように、実稼働サイトに対応するセキュリティ ログインが送信先システムに存在します。  
  
 災害復旧の 1 回インストール[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスが完了すると、master および msdb データベースの完全バックアップを実行して、障害復旧サイトへの切り替えが失敗した場合に、システムのクリーンを復元できるようにします。