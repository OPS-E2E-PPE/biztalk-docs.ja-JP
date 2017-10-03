---
title: "BRE Database1 への接続の暗号化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63edd2bb-97f1-4b8b-8cdc-f4792909ca86
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0dd585c596f7635417a4e22cbccda04593e7c598
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="encrypting-the-connection-to-the-bre-database"></a>BRE データベースへの接続の暗号化
企業のセキュリティ ポリシーに基づいて、次の項目についての暗号化を検討してください。  
  
-   ログオン処理時に送信される資格情報。  
  
-   ビジネス ルール エンジン (BRE) ポリシーを実行するクライアント コンピューターとルール エンジン データベースの間のネットワーク上で送信されるデータ。  
  
 このトピックでは、[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] または [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] でホストされる BRE データベースへの接続を暗号化する方法について説明します。  
  
## <a name="to-encrypt-the-connection-to-the-bre-database-hosted-on-sql-server-2008-sp1-or-sql-server-2008-r2"></a>SQL Server 2008 SP1 または SQL Server 2008 R2 でホストされる BRE データベースへの接続を暗号化するには  
 既定では、クライアント アプリケーションによる [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] への接続の際のログオン処理時に送信される資格情報が暗号化されます。 サーバーの起動時に証明書がサーバーに提供されない場合、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] ではログオン パケットの暗号化に使用する自己署名入りの証明書が生成されます。  
  
 間にネットワーク経由で送信されるデータの暗号化を有効にする[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]とクライアントのインスタンスの[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]、設定する必要があります、**強制的に暗号化**をサーバーでオプション**を[はい]**設定または、 **Force Protocol Encryption**オプションを**はい**クライアントにします。  
  
 ときに、**強制的に暗号化**オプションに設定されて**はい**サーバー側で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]すべての通信の暗号化に SSL を使用して*すべてのクライアントとデータベース サーバー*. つまり、サーバーへのすべての着信接続が暗号化されます。 サーバーでこのオプションを有効にするには、SQL Server 構成マネージャーを使用してサーバーに証明書をインストールすることをお勧めします。 サーバーに証明書がインストールされていない場合、インスタンスが起動されると、サーバーによって自己署名入りの証明書が自動生成されます。  
  
 この自己署名入りの証明書は、信頼されている証明機関から発行された証明書の代わりに使用することができますが、この証明書では ID 偽装の脅威に対する保護は一切提供されません。 実稼働環境やインターネットに接続しているサーバーでは、自己署名入りの証明書を使用した SSL 接続は使用しないことをお勧めします。 このオプションが設定されている場合、暗号化をサポートできないクライアントによるアクセスはすべて拒否されます。 SQL Server は、設定後に再起動する必要があります、**強制的に暗号化**オプション。 このオプションは、SQL Server 構成マネージャー ([!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] のネットワーク構成) を使用して設定できます。  
  
 ときに、 **Force Protocol Encryption**クライアント側で設定されている[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]すべての通信の暗号化に SSL を使用して*そのクライアントとすべてのサーバー間*です。 つまり、クライアントからのすべての発信接続が暗号化されます。 クライアント側でこのオプションを有効にするには、する必要があります証明書をインストール、サーバーの場合、 **Trust Server Certificate**にクライアントでオプションが設定されている**いいえ**です。 場合、 **Trust Server Certificate**にクライアントでオプションが設定されている**はい**クライアントは、サーバー証明書を検証できません自己署名証明書の使用を許可します。 このオプションは、SQL Server 構成マネージャー (SQL Native Client の構成) を使用して設定できます。  
  
 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]暗号化を有効にすることもできます、*特定のクライアントからサーバーへの接続*を設定して、**データ Encrypt/use Encryption**フラグを**はい**で、接続文字列です。 ただし、BRE 自動的に生成、接続文字列は、encryption オプションを設定しなくても**はい**です。 したがって、クライアント コンピューターからルール エンジン データベース サーバーへの特定の接続を暗号化することはできません。 代わりに、設定する必要があります、 **Force Protocol Encryption**前の段落で説明したように、クライアントでオプションです。