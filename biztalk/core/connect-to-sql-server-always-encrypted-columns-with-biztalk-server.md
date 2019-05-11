---
title: BizTalk Server と SQL Server の Always Encrypted の列への接続 |Microsoft Docs
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
ms.openlocfilehash: a6d280bfc0ad199199c2963447c738e83e48c0d6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354929"
---
# <a name="connect-to-sql-server-always-encrypted-columns-with-biztalk-server"></a>BizTalk Server と SQL Server の Always Encrypted の列への接続します。
WCF-SQL アダプターで Always Encrypted を有効に[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]暗号化された列を照会します。  

**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 、WCF-SQL アダプターは、暗号化された列をクエリできます[!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)]します。 `ColumnEncryptionSetting`を有効にするか、Always Encrypted データベースから暗号化/復号化の列の値を取得するための機能を無効にするために使用がプロパティをバインドします。

このトピックでは、有効またはこの機能を無効にする方法を示します[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]します。

> [!TIP]
> [Always Encrypted (データベース エンジン)](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine)有用なリソースを理解し、この詳細については、[!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)]機能します。

## <a name="prerequisites"></a>前提条件
インストール[Feature Pack 2](https://aka.ms/bts2016fp2)上、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]します。

## <a name="enable-always-encrypted"></a>Always Encrypted を有効にします。

1. **BizTalk Server 管理**コンソールで、WCF SQL ポートを右クリックし、選択**プロパティ**します。
2. 移動して、**バインド**タブ。
3. **Always Encrypted**、有効化または無効にする、`ColumnEncryptionSettings`プロパティ。

* **有効になっている**:ポートのクエリ、および Always Encrypted データベースから暗号化されたデータを取得します
* **無効になっている**:ポートは、Always Encrypted データベースをクエリできますが、返されるデータのハッシュ

    ![Always Encrypted を有効にします。](../core/media/enable-always-encrypted.png)

4. 選択**適用**、および**OK**変更を保存します。

## <a name="see-also"></a>関連項目
[Always Encrypted (データベース エンジン)](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine)  
[Feature Pack を構成します。](../core/configure-the-feature-pack.md)