---
title: "手順 2: BizTalk Server 管理コンソール 1 で、オーケストレーションの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestration, configruing in BizTalk Server Administration console
- WCF-Custom port, creating
- migration
ms.assetid: fb057bce-5702-4ea0-8ed5-e299d3a78a11
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1783e56891ffd6d5d27058eab1df8a60663f481b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-configure-the-orchestration-in-biztalk-server-administration-console"></a>手順 2: BizTalk Server 管理コンソールでオーケストレーションを構成します。
![手順 3 の 2](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")  
  
 **所要時間:** 10 分  
  
 **目標:**このステップでは、次のタスクを実行します。  
  
-   作成、Wcf-custom 送信-受信ポートを使用して SAP システムからメッセージを送受信、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 前の手順で作成したマップを使用するには、このポートを構成します。  
  
-   オーケストレーションを構成する WCF カスタム ポートを使用する最後の手順で展開します。  
  
## <a name="prerequisite"></a>前提条件  
  
-   WCF カスタム ポートを構成する場合、BizTalk オーケストレーションを展開します。  
  
### <a name="to-create-a-wcf-custom-port"></a>WCF カスタム ポートを作成するには  
  
1.  使用して、RFC のスキーマを生成すると、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、バインド ファイルが BizTalk プロジェクトにも追加します。 このバインド ファイルをインポートすることができますに、BizTalk WCF カスタムを作成するアプリケーションの送受信ポートです。 バインド ファイルのインポート方法の詳細については、次を参照してください。[バインドのインポート](http://msdn.microsoft.com/library/c927efde-29bd-4efe-9da5-942e7da65dbf)です。  
  
2.  送信ポートが作成されたバインド ファイルをインポートした後、**送信ポート**BizTalk Server 管理コンソール内のフォルダーです。  
  
3.  WCF カスタム ポートを右クリックし、をクリックして**プロパティ**です。  
  
4.  送信ポートのプロパティ ダイアログ ボックスの左ペインで、をクリックして、**全般**タブです。右側のウィンドウからをクリックして**構成**です。  
  
5.  **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスをクリックして、**資格情報**タブをクリックし、SAP システムへの接続に資格情報を指定します。  
  
6.  **[OK]**をクリックします。  
  
7.  送信ポートのプロパティ ダイアログ ボックスの左ペインで、をクリックして**受信マップ**です。 右側のペインの下のフィールドをクリックして、**マップ**列で、ドロップダウン リストから選択して**ResponseMap**です。  
  
     ![WCF カスタム ポートで受信マップを構成する](../../adapters-and-accelerators/adapter-sap/media/10129a7d-211b-464b-b05a-b3ea72f46873.gif "10129a7d-211b-464b-b05a-b3ea72f46873")  
  
8.  送信ポートのプロパティ ダイアログ ボックスの左ペインで、をクリックして**送信マップします。** 右側のペインの下のフィールドをクリックして、**マップ**列で、ドロップダウン リストから選択して**RequestMap**です。  
  
     ![WCF カスタム ポートで送信マップを構成する](../../adapters-and-accelerators/adapter-sap/media/4ffcb4cd-4f53-4b67-92e2-3225d15d97ee.gif "4ffcb4cd-4f53-4b67-92e2-3225d15d97ee")  
  
9. **[OK]**をクリックします。  
  
### <a name="to-configure-the-biztalk-application"></a>BizTalk アプリケーションを構成するには  
  
1.  BizTalk Server 管理コンソールで、展開**BizTalk グループ**、展開**アプリケーション**、し、オーケストレーションが展開されている BizTalk アプリケーションを展開します。  
  
2.  BizTalk アプリケーションを右クリックし、**構成**です。  
  
3.  左側のウィンドウを構成するオーケストレーションをクリックします。 右側のペインから、**ホスト**ドロップダウン リストで、BizTalk ホスト インスタンスを選択します。  
  
4.  下にある、**バインド**ボックスで、BizTalk オーケストレーションの論理ポートを BizTalk Server 管理コンソールで物理ポートにマップします。  
  
    1.  要求メッセージを削除するファイル ポートを選択します。 BizTalk オーケストレーションは、要求メッセージを消費し、SAP システムに送信します。  
  
    2.  ファイル ポートを BizTalk オーケストレーションが SAP システムからの応答を含む応答メッセージをドロップする場所を選択します。  
  
    3.  このトピックの前半で作成した、wcf-custom 送信ポートを選択します。  
  
    4.  **[OK]**をクリックします。  
  
     アプリケーションの構成の詳細についてを参照してください「どのように構成するアプリケーションへ」 [http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360)です。  
  
## <a name="next-steps"></a>次の手順  
 WCF ベースを使用して SAP システムにメッセージを送信する BizTalk プロジェクトに vPrev BizTalk プロジェクトの移行が完了したので[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 今すぐ」の説明に従って、SD_RFC_CUSTOMER_GET RFC を呼び出すための要求メッセージを送信することによって移行済みの BizTalk アプリケーションをテストする必要があります[手順 3: アプリケーションをテストする移行](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application6.md)です。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 2: SAP RFC の BizTalk プロジェクトを移行します。](../../adapters-and-accelerators/adapter-sap/tutorial-2-migrating-an-sap-rfc-biztalk-project.md)