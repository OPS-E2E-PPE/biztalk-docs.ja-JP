---
title: 手順 5 (オンプレミス):メッセージする SalesOrder テーブルを挿入するためのスキーマの生成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab0bc1a7-8bcd-4110-88e6-4eddf0b57068
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 594fef785d9de6b6fe1c2b750b4f17010d02ecbc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396072"
---
# <a name="step-5-on-premises-generate-the-schema-for-inserting-a-message-inito-salesorder-table"></a>手順 5 (オンプレミス):メッセージする SalesOrder テーブルを挿入するためのスキーマを生成します。
ビジネス シナリオに従って販売注文メッセージは、Contoso から送信された X12 を Northwind に挿入する必要があります**SalesOrder**テーブルの場合、注文、数量が 100 より大きい。 メッセージを挿入するのには、 **SalesOrder**テーブルのスキーマを生成する必要があります、**挿入**テーブルに対する操作。 このトピックでは、作成、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューションでは、次を使用して、[!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)]を実行するためのスキーマを生成する、**挿入**操作、 **SalesOrder**テーブル。  

### <a name="to-generate-the-schema-for-insert-operation-on-salesorder-table"></a>SalesOrder テーブルに対する挿入操作のスキーマを生成するには  

1. 作成、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Visual Studio プロジェクト。 Visual Studio から**ファイル** メニューのをクリックして**新規**、 をクリックし、**プロジェクト**します。 **新しいプロジェクト**] ダイアログ ボックスで、インストール済みのテンプレートの一覧からクリックして**BizTalk プロジェクト**、し、[**空[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクト**します。 プロジェクト名の入力`OrderProcessingDemo`順にクリックします**OK**します。  

2. ソリューション エクスプ ローラーでプロジェクト名を右クリックし、[**追加**、] をクリックし、**生成した項目の追加**します。  

3. **生成した項目の追加**ダイアログ ボックスで、 **Consume Adapter Service**、 をクリックし、**追加**します。 [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)] が表示されます。  

4. **バインディングを選択**ドロップダウン リスト、選択**sqlBinding**、 をクリックし、**構成**します。  

5. **アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リストで、次のいずれかの操作を行います。  


   |  このボタンをクリックします。  |                                                                                                                                                               目的                                                                                                                                                               |
   |--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |   **None**   |                                                                                                                                          Windows 認証を使用して SQL Server に接続します。                                                                                                                                           |
   | **Windows**  |                                                                                                                                          Windows 認証を使用して SQL Server に接続します。                                                                                                                                           |
   | **ユーザー名** | ユーザー名とパスワードを指定し、SQL Server データベースで定義されているユーザーの資格情報を指定して SQL Server に接続します。 ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。 **注:** ままにする場合、**ユーザー名**と**パスワード**フィールドを空白、アダプターが Windows 認証を使用して SQL Server に接続します。 |


6. をクリックして、 **URI プロパティ**タブをクリックし、接続パラメーターの値を指定します。 接続 URI の詳細についてはの[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]を参照してください[SQL Server の接続 URI](http://msdn.microsoft.com/library/dd788089.aspx)します。  

   > [!NOTE]
   >  接続パラメーターに予約済みの文字が含まれている場合、としてを指定する必要がありますのでは、 **URI プロパティ**タブ、つまり、エスケープ文字を使用せずします。 ただし、直接の URI を指定する場合、 **URI の構成**フィールドと接続パラメーターは、予約文字を含めることが、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。  
   > 
   > [!NOTE]
   >  [URI のプロパティ] タブで値を指定しないと、[!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)] により URI が `mssql://.//` になります。 このような場合、アダプターは既定のデータベースと、ローカル コンピューター上の既定のデータベース インスタンスに接続します。  

7. **アダプターの構成**ダイアログ ボックスで、をクリックして**OK**します。 **Consume Adapter Service**ダイアログ ボックスで、をクリックして**Connect**します。  

8. **カテゴリを選択**ボックスで、展開**テーブル**、 をクリックし、 **SalesOrder**テーブル。  

9. **利用可能なカテゴリと操作**ボックスで、**挿入**、 をクリックして**追加**、順にクリックします**OK**します。 新しい項目は、ソリューション エクスプ ローラーに追加されます。 スキーマ ファイル (**TableOperation.dbo.SalesOrder.xsd**) で挿入操作を実行するため、生成されたスキーマには、 **SalesOrder**テーブル。  

## <a name="see-also"></a>参照  
 [チュートリアル 4: BizTalk Server 2013 を使用してハイブリッド アプリケーションを作成します。](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)