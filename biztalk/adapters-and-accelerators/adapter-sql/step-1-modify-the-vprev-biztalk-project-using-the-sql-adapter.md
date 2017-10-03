---
title: "手順 1: vPrev SQL アダプターを使用して BizTalk プロジェクトを変更する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 25ad959b-2818-47b8-9a09-3681abb75887
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f0eb02594251fa5ab1c209c1d2655056cf489df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-modify-the-vprev-biztalk-project-using-the-sql-adapter"></a>手順 1: vPrev SQL アダプターを使用して BizTalk プロジェクトを変更します。
![手順 1/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **所要時間:** 10 分  
  
 **目標:**このステップで、次を変更する既存の vPrev BizTalk プロジェクト。  
  
-   WCF ベースを使用して、Customer テーブルに対する挿入操作のメタデータを生成[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
-   WCF ベースを使用する挿入操作を実行するための要求メッセージに vPrev SQL アダプターを使用して挿入操作を実行するための要求メッセージにマップ[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
-   WCF ベースを使用して受信した応答メッセージをマップ[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]vPrev SQL アダプターを使用して受信した応答メッセージにします。  
  
## <a name="prerequisites"></a>前提条件  
 SQL Server データベースに顧客テーブルに Insert 操作を実行する vPrev BizTalk プロジェクトが必要です。  
  
### <a name="to-modify-the-vprev-biztalk-project"></a>VPrev BizTalk プロジェクトを変更するには  
  
1.  WCF ベースを使用して、Customer テーブルに対する挿入操作のメタデータを生成[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 使用することができます、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]メタデータを生成します。  
  
     メタデータを生成する方法については、次を参照してください。 [SQL アダプターを使用して Visual Studio での SQL Server 操作のメタデータを取得](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)です。 スキーマを生成すると後のような名前のファイルが*TableOperation.dbo.Customer.xsd*が BizTalk プロジェクトに追加します。 このファイルには、WCF ベースを使用して SQL Server データベースに顧客テーブルに Insert 操作を実行するメッセージを送信するためのスキーマが含まれています。[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
2.  挿入操作のメタデータを生成すると、ポートのバインド ファイルも作成されます。 次の手順で、SQL Server データベースにメッセージを送信する Wcf-custom 送信ポートを作成するこのバインド ファイルが使用されます。 操作の SOAP アクションは、メタデータを生成する操作にも設定されます。 たとえば、挿入操作のメタデータを生成する場合、送信ポートでの SOAP アクションで、操作名されます"Insert"。 ただし、操作の名前、オーケストレーションの一部異なる場合があります、たとえばなどを作成する論理送信ポートで"Operation_1"。 その結果、送信ポートを使用して SQL Server データベースにメッセージを送信するときに、エラーを取得します。 これを防ぐためには、確認の論理送信ポート、オーケストレーションでは、メタデータの生成対象の操作名と同じ操作名。  
  
     そのため、このチュートリアルが発生した場合、挿入操作のメタデータを生成するための名前を変更"Insert"への論理送信ポート操作します。  
  
3.  要求メッセージの WCF ベースを使用して生成されたスキーマに vPrev SQL データベースのアダプターを使用して生成されたスキーマにマップ[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
    1.  BizTalk マッパーは、BizTalk プロジェクトに追加します。 BizTalk プロジェクトを右クリックし、**追加**、クリックして**新しい項目の**します。  
  
         **新しい項目の追加**ダイアログ ボックスで、左ペインで、**マップ ファイル**です。 右側のウィンドウから次のように選択します。**マップ**です。 など、マップの名前を指定**RequestMap.btm**です。 **[追加]**をクリックします。  
  
    2.  送信元スキーマ ペインで、をクリックして**ソース スキーマを開く**です。  
  
    3.  **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、vPrev SQL アダプターの要求メッセージのスキーマを選択します。 このチュートリアルでは、次のように選択します。 *New_Migration.InsertCustomerService*、クリックして**OK**です。  
  
    4.  **送信元スキーマのルート ノード**ダイアログ ボックスで、*挿入*、順にクリック**OK**。  
  
    5.  送信先スキーマ ペインで、をクリックして**送信先スキーマを開く**です。  
  
    6.  **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、WCF ベースの要求メッセージのスキーマを選択して[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 このチュートリアルでは、次のように選択します。 *New_Migration.TableOperation.dbo.Customer*、クリックして**OK**です。  
  
    7.  **ターゲット スキーマのルート ノード**ダイアログ ボックスで、*挿入*、順にクリック**OK**です。  
  
    8.  次の図に示すように、両方のスキーマ内の各要素をマップします。  
  
         ![要求スキーマのマッピング](../../adapters-and-accelerators/adapter-sql/media/850bbf52-fc3e-42c5-b879-51c6e39a502d.gif "850bbf52-fc3e-42c5-b879-51c6e39a502d")  
  
    9. マップを保存します。  
  
4.  応答メッセージは、WCF ベースを使用して生成されたスキーマに vPrev SQL アダプターを使用して生成されたスキーマにマップ[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
    1.  BizTalk マッパーは、BizTalk プロジェクトに追加します。 BizTalk プロジェクトを右クリックし、[**追加**、] をクリック**新しい項目の**します。  
  
         **新しい項目の追加**ダイアログ ボックスで、左ペインで、**マップ ファイル**です。 右側のウィンドウから次のように選択します。**マップ**です。 など、マップの名前を指定**ResponseMap.btm**、クリックして**追加**です。  
  
    2.  送信元スキーマ ペインで、をクリックして**ソース スキーマを開く**です。  
  
    3.  **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、WCF ベースの応答メッセージのスキーマを選択して[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 このチュートリアルでは、次のように選択します。 *New_Migration.TableOperation.dbo.Customer*、クリックして**OK**です。  
  
    4.  **送信元スキーマのルート ノード**ダイアログ ボックスで、 *InsertResponse*、順にクリック**OK**です。  
  
    5.  送信先スキーマ ペインで、をクリックして**送信先スキーマを開く**です。  
  
    6.  **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、vPrev の応答メッセージのスキーマを選択[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 このチュートリアルでは、次のように選択します。 *New_Migration.InsertCustomerService*、クリックして**OK**です。  
  
    7.  **ターゲット スキーマのルート ノード**ダイアログ ボックスで、 *InsertResponse*、順にクリック**OK**です。  
  
    8.  2 つのアダプターによって生成される応答スキーマの違いがいくつかがわかります。 これらの相違点は以下のとおり。  
  
        -   WCF ベースを使用して[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]レコードを挿入する場合は、テーブルの主キーが含まれています (いても id フィールド) 挿入の応答に操作が挿入された行の id フィールドの値を返します。 そのため、WCF ベースに準拠した応答メッセージのスキーマ[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]追加が含まれています*InsertResult*要素。 この要素には、さらに、挿入された行の id フィールドを格納する配列が含まれています。  
  
        -   使用して、vPrev [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、応答メッセージの一部として空の"Success"要素をアダプターがのみを返します、テーブルにレコードを挿入する場合。  
  
         このような方法でスキーマをマップするを WCF ベースからの応答[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]id フィールドの値を含む「コピー」、vPrev からの応答メッセージの一部では「成功」要素の一部として[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 一括コピー functoid を使用して、別に 1 つのスキーマから要素をコピーすることができます。  
  
         一括コピー functoid を使用する、**ツールボックス**、一括コピー functoid をドラッグおよびマッパー グリッドの上にドロップします。 接続、 **InsertResult** functoid への送信元スキーマ内の要素。 同様に、接続、**成功**を functoid に送信先スキーマ内の要素。 次の図は、functoid を使用して 2 つの要素をマップする方法を示しています。  
  
         ![応答スキーマのマッピング](../../adapters-and-accelerators/adapter-sql/media/c4a347ae-8d2d-4357-b18d-37f36bef17c7.gif "c4a347ae-8d2d-4357-b18d-37f36bef17c7")  
  
        > [!NOTE]
        >  一括コピー functoid の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=119749](http://go.microsoft.com/fwlink/?LinkId=119749)です。  
  
    9. マップを保存します。  
  
5.  保存し、BizTalk ソリューションをビルドします。 ソリューションを右クリックし、をクリックして**ソリューションのビルド**です。  
  
6.  ソリューションを展開する。 ソリューションを右クリックし、をクリックして**ソリューションの配置**です。  
  
## <a name="next-steps"></a>次の手順  
 Wcf-custom 送信ポートを作成し、」の説明に従って、この手順で作成したマップを使用するように構成[手順 2: SQL アダプターを使用して BizTalk Server 管理コンソールでオーケストレーションを構成する](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-orchestration-to-use-the-sql-adapter-in-biztalk-server.md)です。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 1: SQL アダプタを BizTalk プロジェクトを移行します。](../../adapters-and-accelerators/adapter-sql/tutorial-1-migrate-biztalk-projects-to-the-sql-adapter.md)