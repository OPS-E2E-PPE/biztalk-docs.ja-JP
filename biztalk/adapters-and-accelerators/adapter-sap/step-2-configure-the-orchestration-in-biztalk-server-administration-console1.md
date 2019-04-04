---
title: '手順 2: BizTalk Server 管理コンソール 1 で、オーケストレーションの構成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestration, configruing in BizTalk Server Administration console
- WCF-Custom port, creating
- migration
ms.assetid: fb057bce-5702-4ea0-8ed5-e299d3a78a11
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 696315b895ff778c0cc8f4f929cb62a4ba110846
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015059"
---
# <a name="step-2-configure-the-orchestration-in-biztalk-server-administration-console"></a>手順 2: BizTalk Server 管理コンソールでオーケストレーションを構成します。
![ステップ 2/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")  
  
 **所要時間:** 10 分  
  
 **目標:** この手順では、次のタスクを実行します。  
  
- WCF カスタム作成を使用して SAP システムからメッセージを送受信ポートの送信の受信、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 前の手順で作成したマップを使用するには、このポートを構成します。  
  
- オーケストレーションを構成する WCF カスタム ポートを使用する最後の手順で展開されています。  
  
## <a name="prerequisite"></a>前提条件  
  
-   WCF カスタム ポートを構成する BizTalk オーケストレーションを展開します。  
  
### <a name="to-create-a-wcf-custom-port"></a>WCF カスタム ポートを作成するには  
  
1. 使用して、RFC のスキーマを生成すると、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、バインド ファイルが BizTalk プロジェクトにも追加します。 このバインド ファイルをインポートすることに、BizTalk WCF カスタムを作成するアプリケーション送信-受信ポート。 バインド ファイルのインポート方法の詳細については、[バインドのインポート](http://msdn.microsoft.com/library/c927efde-29bd-4efe-9da5-942e7da65dbf)を参照してください。  
  
2. 送信ポートが作成されたバインド ファイルをインポートした後、**送信ポート**BizTalk Server 管理コンソール内のフォルダー。  
  
3. WCF カスタム ポートを右クリックし、**プロパティ**します。  
  
4. 送信ポートのプロパティ ダイアログ ボックスの左側のウィンドウからをクリックして、**全般**タブ。右側のウィンドウから次のようにクリックします。**構成**します。  
  
5. **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**資格情報**タブをクリックし、SAP システムへの接続に資格情報を指定します。  
  
6. **[OK]** をクリックします。  
  
7. 送信ポートのプロパティ ダイアログ ボックスの左側のウィンドウから次のようにクリックします。**受信マップ**します。 右側のペインの下のフィールドをクリックします。、**マップ**列で、ドロップダウン リストから選択します。 **ResponseMap**します。  
  
    ![WCF カスタム ポートで受信マップの構成](../../adapters-and-accelerators/adapter-sap/media/10129a7d-211b-464b-b05a-b3ea72f46873.gif "10129a7d-211b-464b-b05a-b3ea72f46873")  
  
8. 送信ポートのプロパティ ダイアログ ボックスの左側のウィンドウから次のようにクリックします。**送信マップします。** 右側のペインの下のフィールドをクリックします。、**マップ**列で、ドロップダウン リストから選択します。 **RequestMap**します。  
  
    ![WCF カスタム ポートで送信マップの構成](../../adapters-and-accelerators/adapter-sap/media/4ffcb4cd-4f53-4b67-92e2-3225d15d97ee.gif "4ffcb4cd-4f53-4b67-92e2-3225d15d97ee")  
  
9. **[OK]** をクリックします。  
  
### <a name="to-configure-the-biztalk-application"></a>BizTalk アプリケーションを構成するには  
  
1. BizTalk Server 管理コンソールで  **BizTalk グループ**、展開**アプリケーション**、オーケストレーションが展開されている BizTalk アプリケーションを展開します。  
  
2. BizTalk アプリケーションを右クリックし、**構成**します。  
  
3. 左側のウィンドウを構成するオーケストレーションをクリックします。 右側のペインから、**ホスト**ドロップダウン リストで、BizTalk ホスト インスタンスを選択します。  
  
4. で、**バインド**ボックスに、BizTalk オーケストレーションの論理ポートを BizTalk Server 管理コンソールで物理ポートにマップします。  
  
   1. File ポートを要求メッセージをドロップする場所を選択します。 BizTalk オーケストレーションは要求メッセージを使用し、SAP システムに送信します。  
  
   2. File ポートを BizTalk オーケストレーションでの SAP システムからの応答を含む応答メッセージをドロップする場所を選択します。  
  
   3. このトピックの前半で作成した、wcf-custom 送信ポートを選択します。  
  
   4. **[OK]** をクリックします。  
  
      アプリケーションを構成する方法の詳細についてを参照してください「する方法をアプリケーションの構成」 [ http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360)します。  
  
## <a name="next-steps"></a>次の手順  
 WCF ベースを使用して SAP システムにメッセージを送信する BizTalk プロジェクトに vPrev BizTalk プロジェクトの移行が完了したので[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 」の説明に従って、SD_RFC_CUSTOMER_GET RFC を呼び出すための要求メッセージを送信することによって移行済みの BizTalk アプリケーションを今すぐテストする必要があります[手順 3: 移行されたアプリケーションをテストする](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application6.md)します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 2: SAP の RFC BizTalk プロジェクトを移行する](../../adapters-and-accelerators/adapter-sap/tutorial-2-migrating-an-sap-rfc-biztalk-project.md)