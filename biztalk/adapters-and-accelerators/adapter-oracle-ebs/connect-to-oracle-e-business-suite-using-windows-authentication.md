---
title: Windows 認証を使用して Oracle E-business Suite への接続 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0937dfd9-4a94-4d65-a42c-3c5019eefde2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9563f754fd096efb4ab39192f1a8a21a7e6b2207
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009107"
---
# <a name="connect-to-oracle-e-business-suite-using-windows-authentication"></a>Windows 認証を使用して Oracle E-business Suite への接続します。
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]により、クライアントは、Oracle E-business Suite との接続を確立するために Windows 認証を使用するアダプター。 Windows 認証を使用するには、アダプター クライアントはユーザー名の「/」を指定し、パスワードを空白のままにする必要があります。 Windows 認証を使用して Oracle E-business Suite への接続に関する詳細については、[Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)を参照してください。  

## <a name="what-you-need-to-know"></a>知る必要があります。  
 Windows 認証を使用するには、次の操作を行う必要があります。  
  
-   場合、 **ClientCredentialType**プロパティに設定されて**データベース**、指定「/」Oracle E-business Suite への接続を空白のパスワードのユーザー名とままにしてください。  
  
-   場合、 **ClientCredentialType**プロパティに設定されて**EBusiness**、接続する Oracle E-business Suite の資格情報を指定します。 また、指定する必要がありますの「/」、 **OracleUserName**バインドのプロパティと参加解除、 **OraclePassword**プロパティは空白をバインドします。  

## <a name="enable-windows-authentication"></a>Windows 認証を有効にします。  
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
  
5. APPS スキーマ Oracle E-business Suite の成果物を利用できます。 ログイン Oracle E-business Suite の成果物へのアクセスに Windows 認証を使用して、新しく作成したユーザーを有効にするには、APPS スキーマにユーザーのスキーマを変更する必要があります。 次の SQL コマンドを追加するには、ユーザーがログオンしたときに、アプリにユーザーの既定のスキーマを変更するログオン スクリプトを作成します。  
  
   ```  
   alter session set current_schema=APPS;  
   ```  
  
6. APPS スキーマに、ユーザーのスキーマを変更する場合でも引き続きいないできなく参照とを使用してメタデータを生成中に Oracle E-business Suite の成果物を表示する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 これは、新しく作成したユーザーにアプリ スキーマのアクセス許可があるないためにです。 新しく作成されたユーザーに対してアプリ スキーマに対する権限を指定したことを確認します。  
  
## <a name="see-also"></a>参照  
[Oracle E-business Suite アダプターのクライアントを構成します。](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-oracle-client-for-the-e-business-suite-adapter.md)   
[Oracle E-business Suite 接続 URI の作成します。](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)  
 [Oracle E-business Suite への接続を作成します。](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md)