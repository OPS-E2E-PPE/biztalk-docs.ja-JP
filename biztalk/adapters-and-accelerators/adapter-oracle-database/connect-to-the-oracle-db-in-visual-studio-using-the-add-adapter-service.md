---
title: アダプター サービス参照の追加を使用して Visual Studio での Oracle データベースへの接続 |Microsoft Docs
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
ms.openlocfilehash: 06ae5d68ea1dcaced65d57b0f1a832588b5aeb11
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994147"
---
# <a name="connect-to-the-oracle-database-in-visual-studio-using-the-add-adapter-service-reference"></a>アダプター サービス参照の追加を使用して Visual Studio での Oracle データベースへの接続します。
使用して Oracle データベースに接続するため、 [!INCLUDE[adapteroracle_short_md](../../includes/adapteroracle-short-md.md)] .NET プログラミング ソリューションでは、使用する必要があります、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]します。 このトピックでは、手順を使用する方法には、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
## <a name="connect-using-the-add-adapter-service-reference-plug-in"></a>Add Adapter Service Reference プラグインを使用して接続します。  
使用して Oracle データベースに接続するには、次の手順を完了、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。   

  
1. 使用して接続する、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]プログラミング ソリューション。  
  
   1.  Visual Studio を使用してプロジェクトを作成します。  
  
   2.  ソリューション エクスプ ローラーでプロジェクトを右クリックし、をクリックし、**アダプター サービス参照の追加**します。 Add Adapter Service Reference プラグインを開きます。  
  
2. **バインディングを選択**ドロップダウン リスト、選択**oracleDBBinding**  をクリック**構成**します。  
  
3. **アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**ユーザー名と Oracle データベースに接続するためのパスワードを指定します。  
  
   1. Oracle データベースの資格情報を使用して接続するでデータベースの資格情報を入力、**ユーザー名**と**パスワード**テキスト ボックス。 ユーザー名と Oracle データベースに接続するためのパスワードを指定するときに、次の考慮事項に従うことを確認します。  
  
      - **ユーザー名**します。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースでの接続を開くときにユーザー名を入力する値の大文字小文字を保持します。 Oracle データベースでのユーザー名は大文字小文字を区別します。 Oracle ユーザー名を指定することを確認してください、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースで想定されている場合。 通常、これは SCOTT/TIGER 資格情報にユーザー名は大文字である必要があります。"SCOTT"。  
  
      - **パスワード**します。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースでの接続を開くときにパスワードを入力する値の大文字小文字を保持します。 リリース 10 g、前の Oracle システム上のパスワードは大文字小文字を区別しない.  
  
   2. Windows 認証を使用して接続するには、入力**/** で、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。  
  
4. をクリックして、 **URI プロパティ**タブをクリックし、接続パラメーターの値を指定します。 接続 URI の詳細についてはの[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[Oracle Database 接続 URI の作成](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)です。  
  
5. をクリックして、**バインド プロパティ**タブをクリックし、対象と操作に必要な場合、バインドのプロパティの値を指定します。 たとえば、POLLINGSTMT 操作の対象とする場合は、する必要があります設定、 **PollingStatement**プロパティをバインドします。 バインド プロパティの詳細については、次を参照してください。 [Oracle データベース アダプターのバインドのプロパティについて](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)します。
  
6. **[OK]** をクリックします。  
  
7. **[接続]** をクリックします。 接続が確立されると、接続の状態が表示として**接続**します。  
  
    次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]接続が確立された後すぐにします。  
  
    ![アダプター サービスの使用 ダイアログ ボックスの接続](../../adapters-and-accelerators/adapter-oracle-database/media/b5bdb08c-4326-408b-8c2a-aedae64925c8.gif "b5bdb08c-4326-408b-8c2a-aedae64925c8")  
  
## <a name="see-also"></a>参照  
 [Visual Studio での Oracle データベースへの接続します。](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio.md)   
 [Windows 認証を使用して Oracle データベースへの接続します。](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)