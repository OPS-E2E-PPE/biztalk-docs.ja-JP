---
title: "手順 2: Oracle データベース アダプターを使用する BizTalk Server 管理コンソールで、オーケストレーションの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 598b4ab0-ff22-4dfa-aa9c-774c60c90227
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b348a21a54ece0e5db736e18f60c9bed2b8d047d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-configure-the-orchestration-in-biztalk-server-administration-console-to-use-the-oracle-database-adapter"></a>手順 2: Oracle データベース アダプターを使用する BizTalk Server 管理コンソールでオーケストレーションを構成します。
![手順 3 の 2](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")  
  
 **所要時間:** 10 分  
  
 **目標:**このステップでは、次のタスクを実行します。  
  
-   WCF カスタムを作成する送信の受信ポートを使用して Oracle データベースからメッセージを送受信、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。 前の手順で作成したマップを使用するには、このポートを構成します。  
  
-   オーケストレーションを構成する WCF カスタム ポートを使用する最後の手順で展開します。  
  
## <a name="prerequisite"></a>前提条件  
  
-   WCF カスタム ポートを構成する場合、BizTalk オーケストレーションを展開する必要があります。  
  
### <a name="to-create-a-wcf-custom-port"></a>WCF カスタム ポートを作成するには  
  
1.  Oracle データベースを使用して、操作のスキーマを生成すると[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、バインド ファイルが BizTalk プロジェクトにも追加します。 このバインド ファイルをインポートすることができますに、BizTalk WCF カスタムを作成するアプリケーションの送受信ポートです。 バインド ファイルのインポート方法の詳細については、次を参照してください。[バインドのインポート](http://msdn.microsoft.com/library/4cac9267-8bd8-453b-96b4-5c038912463f)です。  
  
2.  送信ポートが作成されたバインド ファイルをインポートした後、**送信ポート**BizTalk Server 管理コンソール内のフォルダーです。  
  
3.  WCF カスタム ポートを右クリックし、をクリックして**プロパティ**です。  
  
4.  送信ポートのプロパティ ダイアログ ボックスの左ペインで、をクリックして、**全般**タブです。右側のウィンドウからをクリックして**構成**です。  
  
5.  **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスをクリックして、**資格情報**タブをクリックし、Oracle データベースへの接続に資格情報を指定します。  
  
6.  **[OK]**をクリックします。  
  
7.  送信ポートのプロパティ ダイアログ ボックスの左ペインで、をクリックして**受信マップ**です。 右側のペインの下のフィールドをクリックして、**マップ**列、およびドロップダウンの選択 から**ResponseMap**です。  
  
     ![受信マップを構成する](../../adapters-and-accelerators/adapter-oracle-database/media/a5e49da1-fe34-46fe-80ca-9316d217171a.gif "a5e49da1-fe34-46fe-80ca-9316d217171a")  
  
8.  送信ポートのプロパティ ダイアログ ボックスの左ペインで、をクリックして**送信マップ**です。 右側のペインの下のフィールドをクリックして、**マップ**列、およびドロップダウンの選択 から**RequestMap**です。  
  
     ![送信マップを構成する](../../adapters-and-accelerators/adapter-oracle-database/media/697b23d8-4231-4718-8a52-8013fac35e3e.gif "697b23d8-4231-4718-8a52-8013fac35e3e")  
  
9. **[OK]**をクリックします。  
  
### <a name="to-configure-the-biztalk-application"></a>BizTalk アプリケーションを構成するには  
  
1.  BizTalk Server 管理コンソールで、次のように展開します。 **BizTalk グループ**、展開**アプリケーション**、オーケストレーションが展開されている BizTalk アプリケーションに展開します。  
  
2.  BizTalk アプリケーションを右クリックし、**構成**です。  
  
3.  左側のウィンドウを構成するオーケストレーションをクリックします。 右側のペインから、**ホスト**ドロップダウン リストで、BizTalk ホスト インスタンスを選択します。  
  
4.  下にある、**バインド**ボックスで、BizTalk オーケストレーションの論理ポートを BizTalk Server 管理コンソールで物理ポートにマップします。  
  
    1.  要求メッセージを削除するファイル ポートを選択します。 BizTalk オーケストレーションは、要求メッセージを消費し、Oracle データベースに送信します。  
  
    2.  ファイル ポートを BizTalk オーケストレーションが Oracle データベースからの応答を含む応答メッセージをドロップする場所を選択します。  
  
    3.  このトピックの前半で作成した、Wcf-custom 送信ポートを選択します。  
  
    4.  **[OK]**をクリックします。  
  
     アプリケーションの構成の詳細についてを参照してください「どのように構成するアプリケーションへ」 [http://go.microsoft.com/fwlink/?LinkID=196961](http://go.microsoft.com/fwlink/?LinkID=196961)です。  
  
## <a name="next-steps"></a>次の手順  
 WCF ベースを使用して Oracle データベースにメッセージを送信する BizTalk プロジェクトに vPrev BizTalk プロジェクトの移行が完了したので[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。 今すぐ」の説明に従って、Oracle データベースで挿入操作を実行する要求メッセージを送信することによって移行済みの BizTalk アプリケーションをテストする必要があります[手順 3: Oracle データベース アダプターに移行したアプリケーションをテスト](../../adapters-and-accelerators/adapter-oracle-database/step-3-test-the-migrated-application-to-oracle-database-adapter.md)です。  
  
## <a name="see-also"></a>参照  
 [チュートリアル: BizTalk プロジェクトを移行します。](https://msdn.microsoft.com/library/dd788186(v=bts.80).aspx)