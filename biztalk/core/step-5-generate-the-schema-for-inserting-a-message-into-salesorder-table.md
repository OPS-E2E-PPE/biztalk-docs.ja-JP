---
title: "手順 5 (オンプレミス): にメッセージを SalesOrder テーブルを挿入するためのスキーマの生成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ab0bc1a7-8bcd-4110-88e6-4eddf0b57068
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: facb5d638ed82e1632e434a2a9c9063a2c3daa68
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-5-on-premises-generate-the-schema-for-inserting-a-message-inito-salesorder-table"></a>手順 5 (オンプレミス): にメッセージを SalesOrder テーブルを挿入するためのスキーマを生成します。
ビジネス シナリオに従って、X12 販売注文メッセージは、Contoso から送信される必要があります挿入される Northwind の**SalesOrder**テーブルの場合は、注文、数量が 100 より大きい。 メッセージを挿入する、 **SalesOrder**テーブルのスキーマを生成する必要があります、**挿入**テーブルで操作します。 このトピックでは、作成、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューション、およびしを使用して、[!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)]を実行するためのスキーマを生成する、**挿入**での操作、 **SalesOrder**テーブル。  
  
### <a name="to-generate-the-schema-for-insert-operation-on-salesorder-table"></a>SalesOrder テーブルで挿入操作を行うスキーマを生成するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Visual Studio プロジェクトを作成します。 Visual Studio から**ファイル** メニューのをクリックして**新規**、クリックして**プロジェクト**です。 **新しいプロジェクト**ダイアログ ボックスで、インストール済みのテンプレートの一覧からクリックして**BizTalk プロジェクト**、し、**空[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクト**です。 プロジェクト名を入力してください。 `OrderProcessingDemo`  をクリックし、 **OK**です。  
  
2.  ソリューション エクスプ ローラーでプロジェクト名を右クリックし、**追加**、クリックして**生成した項目の追加**です。  
  
3.  **生成した項目の追加**ダイアログ ボックスで、**アダプター サービスの使用**、クリックして**追加**です。 [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)] が表示されます。  
  
4.  **バインディングを選択**ドロップダウン リスト、選択**sqlBinding**、クリックして**構成**です。  
  
5.  **アダプターの構成** ダイアログ ボックスをクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リストで、次のいずれかの操作を行います。  
  
    |このボタンをクリックします。|目的|  
    |----------------|----------------|  
    |**なし**|Windows 認証を使用して SQL Server に接続します。|  
    |**Windows**|Windows 認証を使用して SQL Server に接続します。|  
    |**ユーザー名**|ユーザー名とパスワードを指定し、SQL Server データベースで定義されているユーザーの資格情報を指定して SQL Server に接続します。 ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。 **注:**のままにする場合、**ユーザー名**と**パスワード**フィールドを空白には、アダプターが Windows 認証を使用して SQL Server に接続します。|  
  
6.  クリックして、 **URI プロパティ**タブをクリックし、接続パラメーターの値を指定します。 詳細については、接続 URI の[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]を参照してください[SQL Server の接続 URI](http://msdn.microsoft.com/library/dd788089.aspx)です。  
  
    > [!NOTE]
    >  接続パラメーターに予約済みの文字が含まれている場合、そのままを指定する必要がありますのでは、 **URI プロパティ** タブでは、エスケープ文字を使用せずします。 ただし、URI で直接指定する場合、 **URI の構成**フィールドと接続パラメーターは、予約文字を含める、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。  
  
    > [!NOTE]
    >  [URI のプロパティ] タブで値を指定しないと、[!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)] により URI が `mssql://.//` になります。 このような場合、アダプターは既定のデータベースと、ローカル コンピューター上の既定のデータベース インスタンスに接続します。  
  
7.  **アダプターの構成**ダイアログ ボックスで、をクリックして**OK**です。 **アダプター サービスの使用**ダイアログ ボックスで、をクリックして**接続**です。  
  
8.  **カテゴリを選択**ボックスで、展開**テーブル**、をクリックし、 **SalesOrder**テーブル。  
  
9. **利用可能なカテゴリと操作**ボックスで、**挿入**、 をクリックして**追加**、順にクリック**OK**です。 ソリューション エクスプローラーに新しい項目が追加されます。 スキーマ ファイル (**TableOperation.dbo.SalesOrder.xsd**) は、生成されたスキーマでは挿入操作を実行する場合、 **SalesOrder**テーブル。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 4: BizTalk Server 2013 を使用するハイブリッド アプリケーションを作成します。](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)