---
title: アダプター サービス参照の追加を使用して Visual Studio での Oracle データベースへの接続 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93e56c1f-adee-4976-bc39-bb9b8102145e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12c815fbfe2b723a0dd4e4646fd7b69a7e30b01f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215066"
---
# <a name="connect-to-the-oracle-database-in-visual-studio-using-the-add-adapter-service-reference"></a>アダプター サービス参照の追加を使用して Visual Studio での Oracle データベースへの接続します。
使用して Oracle データベースへの接続に、 [!INCLUDE[adapteroracle_short_md](../../includes/adapteroracle-short-md.md)] .NET プログラミング ソリューションで使用する必要があります、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]です。 このトピックでは、使用する方法の説明、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
## <a name="connect-using-the-add-adapter-service-reference-plug-in"></a>アダプター サービス参照の追加プラグインを使用して接続します。  
使用して Oracle データベースへの接続には、次の手順を完了、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。   

  
1.  使用して接続する、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]プログラミング ソリューションで。  
  
    1.  Visual Studio を使用して、プロジェクトを作成します。  
  
    2.  ソリューション エクスプ ローラーでプロジェクトを右クリックし、をクリックして**アダプター サービス参照の追加**です。 アダプター サービス参照の追加プラグインを開きます。  
  
2.  **バインディングを選択**ドロップダウン リスト、選択**oracleDBBinding**  をクリック**構成**です。  
  
3.  **アダプターの構成** ダイアログ ボックスをクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**ユーザー名と、Oracle データベースへの接続にパスワードを指定します。  
  
    1.  Oracle データベースの資格情報を使用して接続するには、内のデータベース資格情報を入力、**ユーザー名**と**パスワード**テキスト ボックス。 ユーザー名と Oracle データベースへの接続にパスワードを指定するときに、次の考慮事項に従うことを確認します。  
  
        -   **ユーザー名**です。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]が Oracle データベースでの接続を開くときに、ユーザー名を入力する値の大文字小文字を保持します。 Oracle データベースでユーザー名は大文字小文字を区別します。 Oracle ユーザー名を指定することを確認する必要があります、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースで想定されている場合。 通常、これは SCOTT/TIGER 資格情報にユーザー名は大文字である必要があります:"SCOTT"です。  
  
        -   **パスワード**です。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]が Oracle データベースでの接続を開くときにパスワードを入力する値の大文字小文字を保持します。 リリース 10 g、前の Oracle システム上のパスワードは大文字小文字が区別されません。  
  
    2.  Windows 認証を使用して接続するには、入力 **/** で、**ユーザー名**テキスト ボックスと参加解除、**パスワード**ボックスは空白です。  
  
4.  クリックして、 **URI プロパティ**タブをクリックし、接続パラメーターの値を指定します。 詳細については、接続 URI の[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[Oracle Database 接続 URI を作成](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)です。  
  
5.  クリックして、**バインド プロパティ**タブをクリックし、対象となる操作で、必要な場合、バインド プロパティの値を指定します。 たとえば、POLLINGSTMT 操作の対象とする場合は、設定する必要あります、 **PollingStatement**プロパティをバインドします。 バインドのプロパティの詳細については、次を参照してください。 [Oracle データベース アダプターのバインドのプロパティについてお読み](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)です。
  
6.  **[OK]** をクリックします。  
  
7.  **[接続]** をクリックします。 接続が確立されると、接続状態は表示**接続**です。  
  
     次の図に示しています、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]接続が確立された後にすぐにします。  
  
     ![アダプター サービスの使用 ダイアログ ボックスの接続](../../adapters-and-accelerators/adapter-oracle-database/media/b5bdb08c-4326-408b-8c2a-aedae64925c8.gif "b5bdb08c-4326-408b-8c2a-aedae64925c8")  
  
## <a name="see-also"></a>参照  
 [Visual Studio での Oracle データベースへの接続します。](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio.md)   
 [Windows 認証を使用して Oracle データベースへの接続します。](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)