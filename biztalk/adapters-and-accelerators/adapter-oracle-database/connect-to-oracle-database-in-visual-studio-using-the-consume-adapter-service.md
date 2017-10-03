---
title: "アダプター サービスを使用して Visual Studio での Oracle データベースへの接続 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- connecting, to the Oracle database
- connection, to the Oracle database
ms.assetid: db2789d0-2d61-472b-ad0c-4ef0707e9c64
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b9ecd6867776b8adf918f901369f526bc0479bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-oracle-database-in-visual-studio-using-the-consume-adapter-service"></a>アダプター サービスを使用して Visual Studio での Oracle データベースへの接続します。
アダプター サービスのアドインがインストールされている WCF LOB Adapter SDK をインストールするときにします。 アダプター サービスの追加のコンピューターにインストールされているすべての WCF カスタム バインドを読み込みます。 WCF ベースを使用して Oracle データベースへの接続に[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]BizTalk プロジェクトで使用する必要があります、 **oracleDBBinding**です。  
  
 このトピックでは、アダプター サービスの追加で使用する方法について説明します。  
  
## <a name="connecting-to-an-oracle-database-using-the-consume-adapter-service-add-in"></a>Oracle に接続するデータベースを使用して、アダプターを使用する追加のサービスの  
 使用して Oracle データベースへの接続には、次の手順を実行、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。  
  
1.  使用して接続する、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] BizTalk ソリューションで。  
  
    1.  ソリューション エクスプ ローラーでプロジェクトを右クリックし、**追加**、クリックして**生成した項目の追加**です。  
  
    2.  **生成した項目の追加** ダイアログ ボックスで、次の操作します。  
  
        |プロパティ|目的|  
        |--------------|----------------|  
        |**カテゴリ**|をクリックして**アダプター サービスの使用**です。|  
        |**[テンプレート]**|をクリックして**アダプター サービスの使用**です。|  
  
    3.  **[追加]**をクリックします。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] が表示されます。  
  
2.  **バインディングを選択**ドロップダウン リスト、選択**oracleDBBinding**  をクリック**構成**です。  
  
3.  **アダプターの構成** ダイアログ ボックスをクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**ユーザー名と、Oracle データベースへの接続にパスワードを指定します。  
  
    1.  Oracle データベースの資格情報を使用して接続するには、内のデータベース資格情報を入力、**ユーザー名**と**パスワード**テキスト ボックス。 ユーザー名と Oracle データベースへの接続にパスワードを指定するときに、次の考慮事項に従うことを確認します。  
  
        -   **ユーザー名**です。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]が Oracle データベースでの接続を開くときに、ユーザー名を入力する値の大文字小文字を保持します。 Oracle データベースでユーザー名は大文字小文字を区別します。 Oracle ユーザー名を指定することを確認する必要があります、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースで想定されている場合。 通常、これは SCOTT/TIGER 資格情報にユーザー名は大文字である必要があります:"SCOTT"です。  
  
        -   **パスワード**です。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]が Oracle データベースでの接続を開くときにパスワードを入力する値の大文字小文字を保持します。 リリース 10 g、前の Oracle システム上のパスワードは大文字小文字が区別されません。  
  
    2.  Windows 認証を使用して接続するには、入力 **/** で、**ユーザー名**テキスト ボックスと参加解除、**パスワード**ボックスは空白です。  
  
4.  クリックして、 **URI プロパティ**タブをクリックし、接続パラメーターの値を指定します。 詳細については、接続 URI の[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[Oracle Database 接続 URI を作成](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)です。  
  
5.  クリックして、**バインド プロパティ**タブをクリックし、対象となる操作で、必要な場合、バインド プロパティの値を指定します。 たとえば、POLLINGSTMT 操作の対象とする場合は、設定する必要あります、 **PollingStatement**プロパティをバインドします。 バインドのプロパティの詳細については、次を参照してください。 [Oracle データベース アダプターのバインドのプロパティについてお読み](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)です。  
  
6.  **[OK]**をクリックします。  
  
7.  **[接続]**をクリックします。 接続が確立されると、接続状態は表示**接続**です。  
  
     次の図に示しています、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]接続が確立された後にすぐにします。  
  
     ![アダプター サービスの使用 ダイアログ ボックスの接続](../../adapters-and-accelerators/adapter-oracle-database/media/b5bdb08c-4326-408b-8c2a-aedae64925c8.gif "b5bdb08c-4326-408b-8c2a-aedae64925c8")  
  
## <a name="see-also"></a>参照  
 [アダプター サービス参照の追加を使用して Visual Studio での Oracle データベースへの接続します。](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-db-in-visual-studio-using-the-add-adapter-service.md)   
 [Windows 認証を使用して Oracle データベースへの接続します。](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)