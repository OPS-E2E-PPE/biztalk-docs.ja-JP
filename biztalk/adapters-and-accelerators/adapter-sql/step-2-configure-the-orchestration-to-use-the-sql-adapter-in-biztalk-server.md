---
title: "手順 2: SQL アダプターを使用して BizTalk Server 管理コンソールで、オーケストレーションの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d6152560-5ff0-4bdc-818c-e906b9642f52
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b090ae83f0ca36bb4ae95795480d5f0d1661f16
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-configure-the-orchestration-in-biztalk-server-administration-console-using-the-sql-adapter"></a>手順 2: SQL アダプターを使用して BizTalk Server 管理コンソールでオーケストレーションを構成します。
![手順 3 の 2](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")  
  
 **所要時間:** 10 分  
  
 **目標:**このステップでは、次のタスクを実行します。  
  
-   WCF カスタム作成送信-受信ポートを使用して、SQL Server データベースからメッセージを送受信、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 前の手順で作成したマップを使用するには、このポートを構成します。  
  
-   オーケストレーションを構成する WCF カスタム ポートを使用する前の手順で展開します。  
  
## <a name="prerequisites"></a>前提条件  
 説明に従って、WCF カスタム ポートを構成する BizTalk オーケストレーションを配置する必要がある[手順 1: vPrev SQL アダプターを使用して BizTalk プロジェクトを変更](../../adapters-and-accelerators/adapter-sql/step-1-modify-the-vprev-biztalk-project-using-the-sql-adapter.md)です。  
  
### <a name="to-create-a-wcf-custom-port"></a>WCF カスタム ポートを作成するには  
  
1.  SQL Server データベースを使用して、操作のスキーマを生成すると[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、バインド ファイルが BizTalk プロジェクトにも追加します。 このバインド ファイルをインポートすることができますに、BizTalk WCF カスタムを作成するアプリケーションの送受信ポートです。 バインド ファイルのインポート方法の詳細については、次を参照してください。[バインドのインポート](http://msdn.microsoft.com/library/48de3a04-4ce8-4ba9-91b6-7e125689fd53)です。  
  
2.  送信ポートが作成されたバインド ファイルをインポートした後、**送信ポート**内のフォルダー、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
3.  WCF カスタム ポートを右クリックし、をクリックして**プロパティ**です。  
  
4.  送信ポートのプロパティ ダイアログ ボックスの左ペインで、をクリックして、**全般**タブです。右側のウィンドウからをクリックして**構成**です。  
  
5.  **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**資格情報** タブをクリックして、SQL Server データベースに接続する資格情報を指定**OK**です。  
  
6.  送信ポートのプロパティ ダイアログ ボックスの左ペインで、をクリックして**受信マップ**です。 右側のペインの下のフィールドをクリックして、**マップ**列、およびドロップダウンの選択 から**ResponseMap**です。  
  
     ![受信マップを構成する](../../adapters-and-accelerators/adapter-sql/media/21e5a23c-7319-4324-8f09-52118ebeeea9.gif "21e5a23c-7319-4324-8f09-52118ebeeea9")  
  
7.  送信ポートのプロパティ ダイアログ ボックスの左ペインで、をクリックして**送信マップ**です。 右側のペインの下のフィールドをクリックして、**マップ**列、およびドロップダウンの選択 から**RequestMap**です。  
  
     ![送信マップを構成する](../../adapters-and-accelerators/adapter-sql/media/5b54e09b-8784-4df6-a279-e8aed813114e.gif "5b54e09b-8784-4df6-a279-e8aed813114e")  
  
8.  **[OK]**をクリックします。  
  
### <a name="to-configure-the-biztalk-application"></a>BizTalk アプリケーションを構成するには  
  
1.  BizTalk Server 管理コンソールで、展開**BizTalk グループ**、展開**アプリケーション**、し、オーケストレーションが展開されている BizTalk アプリケーションを展開します。  
  
2.  BizTalk アプリケーションを右クリックし、**構成**です。  
  
3.  左側のウィンドウを構成するオーケストレーションをクリックします。 右側のペインから、**ホスト**ドロップダウン リストで、BizTalk ホスト インスタンスを選択します。  
  
4.  下にある、**バインド**ボックスで物理ポートを BizTalk オーケストレーションの論理ポートのマッピング、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
    1.  要求メッセージを削除するファイル ポートを選択します。 BizTalk オーケストレーションは、要求メッセージを消費し、SQL Server データベースに送信します。  
  
    2.  ファイル ポートを BizTalk オーケストレーションが、SQL Server データベースからの応答を含む応答メッセージをドロップする場所を選択します。  
  
    3.  このトピックの前半で作成した、Wcf-custom 送信ポートを選択します。  
  
    4.  **[OK]**をクリックします。  
  
## <a name="next-steps"></a>次の手順  
 WCF ベースを使用して SQL Server データベースにメッセージを送信する BizTalk プロジェクトに vPrev BizTalk プロジェクトの移行が完了したので[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 今すぐ」の説明に従って、SQL Server データベースで挿入操作を実行する要求メッセージを送信することによって移行済みの BizTalk アプリケーションをテストする必要があります[手順 3: SQL アダプタを使用する移行されたアプリケーションをテスト](../../adapters-and-accelerators/adapter-sql/step-3-test-the-migrated-application-that-uses-the-sql-adapter.md)です。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 1: SQL アダプタを BizTalk プロジェクトを移行します。](../../adapters-and-accelerators/adapter-sql/tutorial-1-migrate-biztalk-projects-to-the-sql-adapter.md)