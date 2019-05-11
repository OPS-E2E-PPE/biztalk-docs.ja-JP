---
title: ディザスター リカバリーの SQL Server の準備 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 44b77fe8-393d-4781-b0b0-5b7f6e50a67b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 036f5ab2510744ad0f1dc30e36e6135ed5ac0d1c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398528"
---
# <a name="preparing-the-disaster-recovery-sql-servers"></a>ディザスター リカバリーの SQL Server の準備
セットを作成する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース ディザスター リカバリー サイトのインスタンス。 ディザスター リカバリーを確実に[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース インスタンスが同じレベルの運用環境としてのパフォーマンスを提供できます[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース インスタンス、ディザスター リカバリー[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]類似したデータベースのインスタンスを構成する必要がありますハードウェアとを実行している物理コンピューターの台数[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。 このシナリオでは、各運用に対してログ配布が構成される BizTalk Server で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース インスタンスに対応するを適用する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ディザスター リカバリー サイトでのデータベース インスタンス。  
  
 キーの BizTalk Server ログ配布の要件は、データベース ファイルが格納される実稼働サイトでドライブ文字が、ディザスター リカバリー サイトのデータベース ファイルの復元先でドライブ文字と一致しています。 したがって、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース ファイル グループにある G:\data で実稼働環境で、(DR) を移行先サーバーで G:\data ディレクトリが必要、または復元は失敗します。  
  
 BizTalk Server のログ配布はサポートしていません、 **RESTORE WITH MOVE** [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コマンド。 このため、推奨、ディザスター リカバリー サイトにあるデータベース インスタンスの名前に実稼働環境でデータベースのインスタンスの名前が一致する (既定では、インスタンス名は、ファイル パスの一部)。 実行している災害復旧のコンピューターに対応するドライブ文字には、単にディレクトリを作成することも[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ように、**復元**操作で使用するために、同じディレクトリ構造内のファイルを作成できます実稼働します。  
  
 作成[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ディザスター リカバリー サイトのすべての必須セキュリティ ログイン、ディザスター リカバリー サイトへのフェールオーバーが必要なことができるように、実稼働サイトに対応するセキュリティ ログインは、送信先システムに存在します。  
  
 ディザスター リカバリーのインストール 1 回[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスが完了すると、ディザスター リカバリー サイトへの切り替えが失敗したことをクリーン システムを復元できるように、master および msdb データベースの完全バックアップを実行します。