---
title: Windows 認証を使用して Oracle データベースへの接続 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73b42a1b-1105-4278-bf8a-62cf0cffb08f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c984a62275c58f50b0c360a5f46040a6022b459
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007755"
---
# <a name="connect-to-the-oracle-database-using-windows-authentication"></a>Windows 認証を使用して Oracle データベースへの接続します。
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]により、クライアントは、Oracle データベースとの接続を確立するために Windows 認証を使用するアダプター。 Windows 認証を使用するアダプターのクライアントを指定する必要があります「/」は、ユーザー名とパスワードが空白のままにします。 Windows 認証を使用して Oracle データベースへの接続に関する詳細については、次を参照してください。 [Consume Adapter Service を使用して Visual Studio での Oracle データベースへの接続](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio-using-the-consume-adapter-service.md)します。  
  
 Oracle データベースへの接続に Windows 認証を使用するアダプターのクライアントを有効にするには、Oracle データベースを実行するコンピューターで、次のタスクを行う必要があります。  
  
1. 確認します、`sqlnet.ora`クライアントと、サーバーに、使用可能なファイル`ORACLE_BASE\ORACLE_HOME\network\admin\sqlnet.ora`、次のエントリがあります。  
  
   ```  
   SQLNET.AUTHENTICATION_SERVICES= (NTS)  
   ```  
  
2. SYSDBA として Oracle データベースに接続します。  
  
3. Oracle データベースで外部ユーザーとして Windows ユーザーを作成します。 ユーザー名が大文字である必要がありますに注意してください。  
  
   ```  
   CREATE USER “OPS$<DOMAIN_NAME>\<USER_NAME\>” IDENTIFIED EXTERNALLY;  
   ```  
  
4. ユーザーに特権を付与します。  
  
   ```  
   GRANT CONNECT,RESOURCE TO “OPS$<DOMAIN_NAME>\<USER_NAME\>”;  
   ```  
  
5. 新しく作成したユーザーの Oracle のデータベース成果物へのアクセスに Windows 認証を使用してログインを有効にするには、SCOTT スキーマにユーザーのスキーマを変更できます。 次の SQL コマンドを追加するには、ユーザーがログオンしたときに、SCOTT にユーザーの既定のスキーマを変更するログオン スクリプトを作成します。  
  
   ```  
   alter session set current_schema=SCOTT;  
   ```  
  
6. SCOTT スキーマに、ユーザーのスキーマを変更する場合でも引き続きいないできなく参照とを使用してメタデータを生成中に Oracle データベースのアイテムを表示する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。 これは、新しく作成したユーザーに SCOTT スキーマに対するアクセス許可があるないためにです。 新しく作成したユーザーに SCOTT スキーマに対する権限を提供することを確認します。  
  
## <a name="see-also"></a>参照  
 [Oracle データベース アダプターの Oracle クライアントを構成します。](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md)   
[Oracle データベースへの接続の作成](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)