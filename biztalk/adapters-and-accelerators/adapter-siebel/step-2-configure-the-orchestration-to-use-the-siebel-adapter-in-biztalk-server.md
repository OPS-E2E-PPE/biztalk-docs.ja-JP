---
title: '手順 2: Siebel アダプターと BizTalk Server 管理コンソールで、オーケストレーションの構成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41338723-055d-46b4-acee-6969ea79fac0
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f779c9b347c43fb9bd2a6dcdbdb3c33ac8ad09c5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009131"
---
# <a name="step-2-configure-the-orchestration-in-biztalk-server-administration-console-with-the-siebel-adapter"></a>手順 2: Siebel アダプターと BizTalk Server 管理コンソールでオーケストレーションを構成します。
![ステップ 2/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")  
  
 **所要時間:** 10 分  
  
 **目標:** この手順では、次のタスクを実行します。  
  
- WCF カスタム作成を使用して Siebel システムからメッセージを送受信ポートの送信、受信、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。 前の手順で作成したマップを使用するには、このポートを構成します。  
  
- オーケストレーションを構成する WCF カスタム ポートを使用する最後の手順で展開されています。  
  
## <a name="prerequisite"></a>前提条件  
  
-   WCF カスタム ポートを構成する BizTalk オーケストレーションを展開する必要があります。  
  
### <a name="to-create-a-wcf-custom-port"></a>WCF カスタム ポートを作成するには  
  
1. 使用して Siebel システムで操作のスキーマを生成すると[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、バインド ファイルが BizTalk プロジェクトにも追加します。 このバインド ファイルをインポートすることに、BizTalk WCF カスタムを作成するアプリケーション送信-受信ポート。 バインド ファイルのインポート方法の詳細については、次を参照してください。[バインドのインポート](http://msdn.microsoft.com/library/908ab90c-2ba2-4c65-9f74-10579f06e372)します。  
  
2. 送信ポートが作成されたバインド ファイルをインポートした後、**送信ポート**BizTalk Server 管理コンソール内のフォルダー。  
  
3. WCF カスタム ポートを右クリックし、**プロパティ**します。  
  
4. 送信ポートのプロパティ ダイアログ ボックスの左側のウィンドウからをクリックして、**全般**タブ。右側のウィンドウから次のようにクリックします。**構成**します。  
  
5. **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**資格情報**タブし、Siebel システムへの接続に資格情報を指定します。  
  
6. **[OK]** をクリックします。  
  
7. 送信ポートのプロパティ ダイアログ ボックスの左側のウィンドウから次のようにクリックします。**受信マップ**します。 右側のペインの下のフィールドをクリックします。、**マップ**列、およびドロップダウンの選択から**ResponseMap**。  
  
    ![受信マップを構成する](../../adapters-and-accelerators/adapter-siebel/media/e1ceee98-9f10-40f1-a611-88d3a2c102a9.gif "e1ceee98-9f10-40f1-a611-88d3a2c102a9")  
  
8. 送信ポートのプロパティ ダイアログ ボックスの左側のウィンドウから次のようにクリックします。**送信マップ**します。 右側のペインの下のフィールドをクリックします。、**マップ**列、およびドロップダウンの選択から**RequestMap**。  
  
    ![送信マップの構成](../../adapters-and-accelerators/adapter-siebel/media/8f8efeaa-d5cd-4ed3-b2f3-a600c48c3bb9.gif "8f8efeaa-d5cd-4ed3-b2f3-a600c48c3bb9")  
  
9. **[OK]** をクリックします。  
  
### <a name="to-configure-the-biztalk-application"></a>BizTalk アプリケーションを構成するには  
  
1. BizTalk Server 管理コンソールで  **BizTalk グループ**、展開**アプリケーション**オーケストレーションが展開されている BizTalk アプリケーションを展開します。  
  
2. BizTalk アプリケーションを右クリックし、**構成**します。  
  
3. 左側のウィンドウを構成するオーケストレーションをクリックします。 右側のペインから、**ホスト**ドロップダウン リストで、BizTalk ホスト インスタンスを選択します。  
  
4. で、**バインド**ボックスに、BizTalk オーケストレーションの論理ポートを BizTalk Server 管理コンソールで物理ポートにマップします。  
  
   1. File ポートを要求メッセージをドロップする場所を選択します。 BizTalk オーケストレーションは要求メッセージを使用し、Siebel システムに送信します。  
  
   2. File ポートを BizTalk オーケストレーションで Siebel システムからの応答を含む応答メッセージをドロップする場所を選択します。  
  
   3. このトピックの前半で作成した、Wcf-custom 送信ポートを選択します。  
  
   4. **[OK]** をクリックします。  
  
      アプリケーションを構成する方法の詳細についてを参照してください「する方法をアプリケーションの構成」 [ http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360)します。  
  
## <a name="next-steps"></a>次の手順  
 WCF ベースを使用して Siebel システムにメッセージを送信する BizTalk プロジェクトに vPrev BizTalk プロジェクトの移行が完了したので[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。 」の説明に従って、アカウントのビジネス コンポーネントに対する挿入操作を呼び出すための要求メッセージを送信することによって移行済みの BizTalk アプリケーションを今すぐテストする必要があります[手順 3: Siebel アダプターを使用した移行されたアプリケーションをテストする](../../adapters-and-accelerators/adapter-siebel/step-3-test-the-migrated-application-with-the-siebel-adapter.md)します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 2: Siebel の BizTalk プロジェクトを移行します。](../../adapters-and-accelerators/adapter-siebel/tutorial-2-migrating-biztalk-projects-in-siebel.md)