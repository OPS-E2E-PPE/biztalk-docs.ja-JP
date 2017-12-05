---
title: "Windows 認証を使用して Oracle データベースへの接続 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 73b42a1b-1105-4278-bf8a-62cf0cffb08f
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 840435ce334863a4b76e6ac7da0d8dd64e7d4937
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="connect-to-the-oracle-database-using-windows-authentication"></a>Windows 認証を使用して Oracle データベースへの接続します。
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle データベースとの接続を確立するために Windows 認証を使用するアダプターのクライアントを有効にします。 Windows 認証を使用するアダプターのクライアントを指定する必要があります「/」は、ユーザー名とパスワードの空白のままにします。 Windows 認証を使用して Oracle データベースへの接続に関する詳細については、次を参照してください。[アダプター サービスの使用を使用して Visual Studio での Oracle データベースへの接続](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio-using-the-consume-adapter-service.md)です。  
  
 アダプター クライアントを Windows 認証を使用して Oracle データベースへの接続を有効にするには、Oracle データベースを実行しているコンピューターで、次のタスクを行う必要があります。  
  
1.  確認して、`sqlnet.ora`両方のクライアントとサーバーで使用可能なファイルを`ORACLE_BASE\ORACLE_HOME\network\admin\sqlnet.ora`、次のエントリがあります。  
  
    ```  
    SQLNET.AUTHENTICATION_SERVICES= (NTS)  
    ```  
  
2.  SYSDBA として Oracle データベースに接続します。  
  
3.  Oracle データベース内の外部のユーザーとして Windows ユーザーを作成します。 ユーザー名が大文字である必要がありますに注意してください。  
  
    ```  
    CREATE USER “OPS$<DOMAIN_NAME>\<USER_NAME\>” IDENTIFIED EXTERNALLY;  
    ```  
  
4.  ユーザーに特権を付与します。  
  
    ```  
    GRANT CONNECT,RESOURCE TO “OPS$<DOMAIN_NAME>\<USER_NAME\>”;  
    ```  
  
5.  Oracle データベース アイテムにアクセスする Windows 認証を使用してログインを新しく作成したユーザーを有効にするには、SCOTT スキーマに、ユーザーのスキーマを変更できます。 次の SQL コマンドを追加するには、ユーザーがログオンしたときに、SCOTT にユーザーの既定のスキーマを変更するログオン スクリプトを作成します。  
  
    ```  
    alter session set current_schema=SCOTT;  
    ```  
  
6.  SCOTT スキーマにユーザーのスキーマを変更する場合でもまだないことができますを参照しを使用してメタデータを生成中に Oracle データベース アイテムを表示する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。 これは、新しく作成したユーザーに SCOTT スキーマに対するアクセス許可があるないためです。 新しく作成されたユーザーに SCOTT スキーマの権限を提供することを確認してください。  
  
## <a name="see-also"></a>参照  
 [Oracle データベース アダプターの Oracle クライアントを構成します。](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md)   
[Oracle データベースへの接続の作成](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)