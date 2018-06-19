---
title: BizTalk Server と SQL Server の Always Encrypted の列への接続 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/20/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fcc20a2b-daf9-4b7f-ae61-cb408e4bd04c
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d5e117bd91176589e998fc01eb2c613ac0da2bbc
ms.sourcegitcommit: f65e8ed2b8c18cded26b9d60868fb6a56bcc1205
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
ms.locfileid: "25497753"
---
# <a name="connect-to-sql-server-always-encrypted-columns-with-biztalk-server"></a>BizTalk Server と SQL Server の Always Encrypted の列への接続します。
WCF-SQL アダプターで Always Encrypted が有効に[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]を暗号化された列を照会します。  

**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 、WCF-SQL アダプターの暗号化された列を照会できます[!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)]です。 `ColumnEncryptionSetting`プロパティのバインドは有効にするにまたは Always Encrypted データベースから列の暗号化/暗号化解除の値を取得するための機能を無効にするのに使用します。

このトピックを有効またはこの機能を無効にする方法を示します[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。

> [!TIP] 
> [Always Encrypted (データベース エンジン)](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine)を理解し、詳細については、優れたリソース[!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)]機能します。

## <a name="prerequisites"></a>前提条件
インストール[Feature Pack 2](https://aka.ms/bts2016fp2)上、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。

## <a name="enable-always-encrypted"></a>Always Encrypted を有効にします。

1. **BizTalk Server 管理コンソール**コンソールで、WCF SQL ポートを右クリックしを選択して**プロパティ**です。
2. 移動して、**バインド**タブです。
3. **Always Encrypted**、有効化または無効にする、`ColumnEncryptionSettings`プロパティ。

* **有効になっている**: ポート クエリ、および Always Encrypted データベースから暗号化されたデータを取得
* **無効になっている**: ポートは、Always Encrypted データベースをクエリできますが、返されるデータはハッシュされています

    ![Always Encrypted を有効にします。](../core/media/enable-always-encrypted.png)

4. 選択**適用**と**OK**して変更を保存します。

## <a name="see-also"></a>参照
[Always Encrypted (Database Engine) (Always Encrypted (データベース エンジン))](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine)  
[この機能パックを構成します。](../core/configure-the-feature-pack.md)