---
title: "Windows 認証を使用して Oracle E-business Suite への接続 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0937dfd9-4a94-4d65-a42c-3c5019eefde2
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed71a893ef029e6524b7e71f68626c32f207f91e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="connect-to-oracle-e-business-suite-using-windows-authentication"></a>Windows 認証を使用して Oracle E-business Suite への接続します。
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite への接続を確立するために Windows 認証を使用するアダプターのクライアントを有効にします。 Windows 認証を使用するには、アダプター クライアント ユーザー名の「/」を指定して、パスワードを空白のままにします。 Windows 認証を使用して Oracle E-business Suite への接続に関する詳細については、次を参照してください。 [Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)です。  

## <a name="what-you-need-to-know"></a>おく必要があります。  
 Windows 認証を使用するのには、次の操作を行う必要があります。  
  
-   場合、 **ClientCredentialType**プロパティに設定されている**データベース**、指定「/」のままにして、ユーザー名の Oracle E-business Suite への接続に空白のパスワード。  
  
-   場合、 **ClientCredentialType**プロパティに設定されている**EBusiness**、接続する Oracle E-business Suite 資格情報を指定します。 また、指定する必要がありますの「/」、 **OracleUserName**バインディング プロパティ、およびのままにして、 **OraclePassword**プロパティは空白をバインドします。  

## <a name="enable-windows-authentication"></a>Windows 認証を有効にします。  
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
  
5.  Oracle E-business Suite 成果物は、アプリのスキーマで使用できます。 Oracle E-business Suite の成果物にアクセスする Windows 認証を使用してログインを新しく作成したユーザーを有効にするには、アプリケーション スキーマに、ユーザーのスキーマを変更してください。 次の SQL コマンドを追加するには、ユーザーがログオンしたときに、アプリにユーザーの既定のスキーマを変更するログオン スクリプトを作成します。  
  
    ```  
    alter session set current_schema=APPS;  
    ```  
  
6.  アプリのスキーマにユーザーのスキーマを変更する場合でもまだいないことができますを参照しを使用してメタデータを生成中に Oracle E-business Suite の成果物を表示する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。 これは、新しく作成したユーザーがアプリケーション スキーマのアクセス許可を持たないためです。 新しく作成されたユーザーのアプリ スキーマの権限を指定することを確認してください。  
  
## <a name="see-also"></a>参照  
[Oracle クライアント E-business Suite アダプターを構成します。](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-oracle-client-for-the-e-business-suite-adapter.md)   
[Oracle E-business Suite 接続 URI を作成します。](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)  
 [Oracle E-business Suite への接続を作成します。](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md)