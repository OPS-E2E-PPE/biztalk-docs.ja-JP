---
title: "手順 2: Siebel アダプターと BizTalk Server 管理コンソールで、オーケストレーションの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 41338723-055d-46b4-acee-6969ea79fac0
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa0ed6c6609ccca3d13ea0eba46f9e2d0ee6cc14
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-configure-the-orchestration-in-biztalk-server-administration-console-with-the-siebel-adapter"></a>手順 2: BizTalk Server 管理コンソールで Siebel アダプターとオーケストレーションを構成します。
![手順 3 の 2](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")  
  
 **所要時間:** 10 分  
  
 **目標:**このステップでは、次のタスクを実行します。  
  
-   作成、Wcf-custom 送信-受信ポートを使用して、Siebel システムからメッセージを送受信、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。 前の手順で作成したマップを使用するには、このポートを構成します。  
  
-   オーケストレーションを構成する WCF カスタム ポートを使用する最後の手順で展開します。  
  
## <a name="prerequisite"></a>前提条件  
  
-   WCF カスタム ポートを構成する場合、BizTalk オーケストレーションを展開する必要があります。  
  
### <a name="to-create-a-wcf-custom-port"></a>WCF カスタム ポートを作成するには  
  
1.  Siebel システムを使用して、操作のスキーマを生成すると[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、バインド ファイルが BizTalk プロジェクトにも追加します。 このバインド ファイルをインポートすることができますに、BizTalk WCF カスタムを作成するアプリケーションの送受信ポートです。 バインド ファイルのインポート方法の詳細については、次を参照してください。[バインドのインポート](http://msdn.microsoft.com/library/908ab90c-2ba2-4c65-9f74-10579f06e372)です。  
  
2.  送信ポートが作成されたバインド ファイルをインポートした後、**送信ポート**BizTalk Server 管理コンソール内のフォルダーです。  
  
3.  WCF カスタム ポートを右クリックし、をクリックして**プロパティ**です。  
  
4.  送信ポートのプロパティ ダイアログ ボックスの左ペインで、をクリックして、**全般**タブです。右側のウィンドウからをクリックして**構成**です。  
  
5.  **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**資格情報**タブし、Siebel システムへの接続に資格情報を指定します。  
  
6.  **[OK]**をクリックします。  
  
7.  送信ポートのプロパティ ダイアログ ボックスの左ペインで、をクリックして**受信マップ**です。 右側のペインの下のフィールドをクリックして、**マップ**列、およびドロップダウンの選択 から**ResponseMap**です。  
  
     ![受信マップを構成する](../../adapters-and-accelerators/adapter-siebel/media/e1ceee98-9f10-40f1-a611-88d3a2c102a9.gif "e1ceee98-9f10-40f1-a611-88d3a2c102a9")  
  
8.  送信ポートのプロパティ ダイアログ ボックスの左ペインで、をクリックして**送信マップ**です。 右側のペインの下のフィールドをクリックして、**マップ**列、およびドロップダウンの選択 から**RequestMap**です。  
  
     ![送信マップを構成する](../../adapters-and-accelerators/adapter-siebel/media/8f8efeaa-d5cd-4ed3-b2f3-a600c48c3bb9.gif "8f8efeaa-d5cd-4ed3-b2f3-a600c48c3bb9")  
  
9. **[OK]**をクリックします。  
  
### <a name="to-configure-the-biztalk-application"></a>BizTalk アプリケーションを構成するには  
  
1.  BizTalk Server 管理コンソールで、次のように展開します。 **BizTalk グループ**、展開**アプリケーション**、オーケストレーションが展開されている BizTalk アプリケーションに展開します。  
  
2.  BizTalk アプリケーションを右クリックし、**構成**です。  
  
3.  左側のウィンドウを構成するオーケストレーションをクリックします。 右側のペインから、**ホスト**ドロップダウン リストで、BizTalk ホスト インスタンスを選択します。  
  
4.  下にある、**バインド**ボックスで、BizTalk オーケストレーションの論理ポートを BizTalk Server 管理コンソールで物理ポートにマップします。  
  
    1.  要求メッセージを削除するファイル ポートを選択します。 BizTalk オーケストレーションは、要求メッセージを消費し、Siebel システムに送信します。  
  
    2.  ファイル ポートを BizTalk オーケストレーションが Siebel システムからの応答を含む応答メッセージをドロップする場所を選択します。  
  
    3.  このトピックの前半で作成した、Wcf-custom 送信ポートを選択します。  
  
    4.  **[OK]**をクリックします。  
  
     アプリケーションの構成の詳細についてを参照してください「どのように構成するアプリケーションへ」 [http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360)です。  
  
## <a name="next-steps"></a>次の手順  
 WCF ベースを使用して、Siebel システムにメッセージを送信する BizTalk プロジェクトに vPrev BizTalk プロジェクトの移行が完了したので[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。 今すぐ」の説明に従って、アカウントのビジネス コンポーネントに対する挿入操作を呼び出すための要求メッセージを送信することによって移行済みの BizTalk アプリケーションをテストする必要があります[手順 3: アプリケーションをテストする移行 Siebel アダプターと](../../adapters-and-accelerators/adapter-siebel/step-3-test-the-migrated-application-with-the-siebel-adapter.md)です。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 2: Siebel の BizTalk プロジェクトを移行します。](../../adapters-and-accelerators/adapter-siebel/tutorial-2-migrating-biztalk-projects-in-siebel.md)