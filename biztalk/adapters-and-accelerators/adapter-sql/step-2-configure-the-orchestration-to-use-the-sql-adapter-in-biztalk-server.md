---
title: '手順 2: SQL アダプターを使用して BizTalk Server 管理コンソールで、オーケストレーションの構成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d6152560-5ff0-4bdc-818c-e906b9642f52
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6293758d9891d86e137d07e9735ce37162d6a96b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984027"
---
# <a name="step-2-configure-the-orchestration-in-biztalk-server-administration-console-using-the-sql-adapter"></a>手順 2: SQL アダプターを使用して BizTalk Server 管理コンソールでオーケストレーションを構成します。
![ステップ 2/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")  
  
 **所要時間:** 10 分  
  
 **目標:** この手順では、次のタスクを実行します。  
  
- WCF カスタム作成送受信ポートを使用して、SQL Server データベースからのメッセージの送受信、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 前の手順で作成したマップを使用するには、このポートを構成します。  
  
- オーケストレーションを構成する WCF カスタム ポートを使用する前の手順で展開されています。  
  
## <a name="prerequisites"></a>前提条件  
 」の説明に従って、WCF カスタム ポートを構成する BizTalk オーケストレーションを配置する必要がある[手順 1: vPrev BizTalk プロジェクトを SQL アダプターを使用して変更](../../adapters-and-accelerators/adapter-sql/step-1-modify-the-vprev-biztalk-project-using-the-sql-adapter.md)します。  
  
### <a name="to-create-a-wcf-custom-port"></a>WCF カスタム ポートを作成するには  
  
1. 使用して SQL Server データベースで操作のスキーマを生成すると[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、バインド ファイルが BizTalk プロジェクトにも追加します。 このバインド ファイルをインポートすることに、BizTalk WCF カスタムを作成するアプリケーション送信-受信ポート。 バインド ファイルのインポート方法の詳細については、[バインドのインポート](http://msdn.microsoft.com/library/48de3a04-4ce8-4ba9-91b6-7e125689fd53)を参照してください。  
  
2. 送信ポートが作成されたバインド ファイルをインポートした後、**送信ポート**フォルダーで、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
3. WCF カスタム ポートを右クリックし、**プロパティ**します。  
  
4. 送信ポートのプロパティ ダイアログ ボックスの左側のウィンドウからをクリックして、**全般**タブ。右側のウィンドウから次のようにクリックします。**構成**します。  
  
5. **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**資格情報**タブで、SQL Server データベースに接続し、をクリックし、資格情報を指定します。 **[ok]** します。  
  
6. 送信ポートのプロパティ ダイアログ ボックスの左側のウィンドウから次のようにクリックします。**受信マップ**します。 右側のペインの下のフィールドをクリックします。、**マップ**列、およびドロップダウンの選択から**ResponseMap**。  
  
    ![受信マップを構成する](../../adapters-and-accelerators/adapter-sql/media/21e5a23c-7319-4324-8f09-52118ebeeea9.gif "21e5a23c-7319-4324-8f09-52118ebeeea9")  
  
7. 送信ポートのプロパティ ダイアログ ボックスの左側のウィンドウから次のようにクリックします。**送信マップ**します。 右側のペインの下のフィールドをクリックします。、**マップ**列、およびドロップダウンの選択から**RequestMap**。  
  
    ![送信マップの構成](../../adapters-and-accelerators/adapter-sql/media/5b54e09b-8784-4df6-a279-e8aed813114e.gif "5b54e09b-8784-4df6-a279-e8aed813114e")  
  
8. **[OK]** をクリックします。  
  
### <a name="to-configure-the-biztalk-application"></a>BizTalk アプリケーションを構成するには  
  
1. BizTalk Server 管理コンソールで  **BizTalk グループ**、展開**アプリケーション**、オーケストレーションが展開されている BizTalk アプリケーションを展開します。  
  
2. BizTalk アプリケーションを右クリックし、**構成**します。  
  
3. 左側のウィンドウを構成するオーケストレーションをクリックします。 右側のペインから、**ホスト**ドロップダウン リストで、BizTalk ホスト インスタンスを選択します。  
  
4. 下、**バインド**ボックスに、BizTalk オーケストレーションの論理ポートをマップで物理ポートに、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
   1.  File ポートを要求メッセージをドロップする場所を選択します。 BizTalk オーケストレーションは要求メッセージを使用し、SQL Server データベースに送信します。  
  
   2.  File ポートを BizTalk オーケストレーションが、SQL Server データベースからの応答を含む応答メッセージをドロップする場所を選択します。  
  
   3.  このトピックの前半で作成した、Wcf-custom 送信ポートを選択します。  
  
   4.  **[OK]** をクリックします。  
  
## <a name="next-steps"></a>次の手順  
 WCF ベースを使用して SQL Server データベースにメッセージを送信する BizTalk プロジェクトに vPrev BizTalk プロジェクトの移行が完了したので[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 」の説明に従って、SQL Server データベースに対して、挿入操作を実行する要求メッセージを送信することによって移行済みの BizTalk アプリケーションを今すぐテストする必要があります[手順 3: SQL アダプタを使用する移行されたアプリケーションをテスト](../../adapters-and-accelerators/adapter-sql/step-3-test-the-migrated-application-that-uses-the-sql-adapter.md)します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 1: SQL アダプタを BizTalk プロジェクトを移行します。](../../adapters-and-accelerators/adapter-sql/tutorial-1-migrate-biztalk-projects-to-the-sql-adapter.md)