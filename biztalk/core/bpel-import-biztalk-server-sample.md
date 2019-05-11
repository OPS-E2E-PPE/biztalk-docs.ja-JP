---
title: BPEL インポート (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BPEL, orchestrations
- examples, orchestrations
- examples, BPEL Import Wizard
- BPEL, examples
- BPEL Import Wizard, examples
- BPEL Import Wizard, orchestrations
ms.assetid: 3fc70608-ccd9-4249-b238-c09fc6551db1
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d86d5b519d05c01389cff1c5a46e071c51e091a6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357858"
---
# <a name="bpel-import-biztalk-server-sample"></a>BPEL インポート (BizTalk Server サンプル)
BPEL インポート サンプルでは、Business Process Execution Language (BPEL) プロセスの説明とその関連アイテムからオーケストレーションを作成する方法を示します。  

## <a name="what-this-sample-does"></a>このサンプルの処理  
 Wide World importers 社は、小売業者に自動出荷サービスを提供する出荷業者です。 具体的には、Wide World importers 社は小売業者に有効にします。  

- 注文の出荷を要求します。  

- 出荷を追跡します。  

- 出荷を確認します。  

- 請求および支払いの送付を確認します。  

  BPEL ドキュメントが全体からの応答を期待する方法と製品の企業がサービスの呼び出しに予定されている通常の方法について説明します、これらのサービスの可用性は、Web サービス記述言語 (WSDL) ドキュメントを使用して表すことが、World importers 社です。  

  Northwind Traders 社に出荷処理 Wide World Importers 人材採用と BPEL ファイルが提供されるいくつかの関連成果物全体の相互作用を記述します。 BPEL ファイルを使用して、Northwind Traders の作成、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Wide World importers 社を介して自動的に処理するアプリケーション (BPELShipping) を並べ替えます。  

  このサンプルでは、このシナリオを説明します。 BPELShipping アプリケーション。  

1. Northwind traders 社の顧客の注文システムから注文を受信します。  

2. Wide World importers 社と要求の確認に出荷要求を送信します。  

3. Wide World importers 社から出荷要求の確認を受信します。  

4. Wide World importers 社からピックアップ通知を受信します。  

5. 最大の出荷状況メッセージと出荷が顧客によって受信されたときなどを受け取ります。  

6. Wide World importers 社から請求書を受信します。  

7. 請求書の受信確認では、Wide World importers 社に応答します。  

8. Wide World importers 社から支払い確認メッセージを受信します。  

9. 注文システムには、最終的な出荷確認を送信します。  

   別の BizTalk アプリケーション (ShipperProcess) は、このサンプルの Wide World importers 社のシミュレーションに使用されます。 BPELShipping アプリケーションは、一般的なファイル システムの場所を通信に使用されるファイル トランスポートを使用して、ShipperProcess と通信します。  

## <a name="how-this-sample-is-designed-and-why"></a>このサンプルのデザイン方法とその理由  
 BPEL の Web サービスは、Web サービスを使用して相互にビジネスを実行するさまざまな企業で簡単に共有できるように、ビジネス プロセスを記述する XML ベースの言語です。 BPEL はビジネス プロトコル レベルでは、ビジネス プロセスを処理する方法を説明しますが、パートナーから受信した注文書の処理を行う手順のような企業内の内部プロセスが説明されていません。 このサンプルは、BPEL ファイルと対応する WSDL ファイルをインポート、オーケストレーションに変換してから、パートナーとビジネス プロセスを実行する起動する方法について説明する設計されています。  

 BPEL および WSDL ファイルをインポートし、事前構築済みの BizTalk アプリケーション (ShipperProcess) と対話するためのオーケストレーションに変換する方法を示す一連の手順を次に示します。 次の手順を完了する場合は、「をビルドおよび初期化する BPELShipping アプリケーション」で説明されている手順を実行する必要はありません。  

#### <a name="to-import-from-bpel-and-build-a-working-solution"></a>BPEL からインポートし、実用的なソリューションをビルドするには  

1. Microsoft で[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]の**ファイル** メニューのをクリックして**新規**、 をクリックし、**プロジェクト**。  

   > [!NOTE]
   >  この手順を完了する前に、サポートのプロセスとスキーマのプロジェクトを作成する ShipperProcess アプリケーションを設定する必要があります。  

2. **新しいプロジェクト** ダイアログ ボックスで、プロジェクトの種類 ウィンドウで**BizTalk (プロジェクト)** します。 [テンプレート] ペインで選択**BizTalk Server BPEL インポート プロジェクト**します。  

3. **名前**ボックスに、入力**BPELShipping**します。  

   > [!NOTE]
   >  別の名前を使用する場合、最終的なバインドの手順で問題が発生する可能性があります。  

4. プロジェクトの場所を選択し、クリックして**OK** BPEL インポート ウィザードを開始します。  

5. **へようこそ**  ページで **次**します。  

6. **選択 BPEL、WSDL、および XSD ファイル**] ページで [**参照**します。  

7. すべてのファイルを選択、 \<*サンプル パス*\>\Orchestrations\BPELImport\BPELSource フォルダー、 をクリックして**オープン**、順にクリックします**次**.  

   > [!NOTE]
   >  この手順では、ビジネス プロセスの説明に BPEL および WSDL ファイルとビジネス ドキュメント スキーマを表す XSD ファイルを選択します。  

8. **呼び出した WebServices 用の WSDL ファイルの選択**] ページで [**完了**します。  

9. BPEL インポート ウィザードでは、インポートに成功を報告するウィザードを閉じます。 プロジェクトが作成されました。  

10. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプトでディレクトリ変更コマンド (**cd**) プロジェクトの場所にします。  

11. 次のコマンドを実行します。  

     **sn – k BPELShipping.snk**  

12. ソリューション エクスプ ローラーで右クリックし、 **BPELShipping**プロジェクトをクリックして**プロパティ**します。  

13. **Common properties \assembly**、アセンブリ キー ファイルを選択**BPELShipping.snk**ステップ 11 で作成され、順にクリックします**OK**します。  

14. ソリューション エクスプ ローラーで、すべての .xsd ファイルを選択し、それらを削除します。  

15. ソリューション エクスプ ローラーで選択**参照の追加**、し、**プロジェクト**] タブで [**参照**します。  

16. 選択**ShippingSchemas.dll**の場所から\<*サンプル パス*\>\Orchestrations\BPELImport\Solution\ShipperProcess\ShippingSchemas\bin\Development とクリックして**OK**します。  

    > [!NOTE]
    >  「ビルド、ShipperProcess アプリケーションを初期化して」セクションには、これを構築する方法の手順があります。  

17. ソリューション エクスプ ローラーでダブルクリック **[ordershippingprocess.bpel.odx]** します。  

18. **ビュー**メニューの **その他の Windows/オーケストレーション**します。  

19. オーケストレーションの種類 ウィンドウで、右クリック**オーケストレーションのプロパティ** をクリックし、**プロパティ ウィンドウ**します。  

20. [プロパティ] ウィンドウで次のように設定します。、**エクスポート可能なオーケストレーション**プロパティを**False**します。  

21. ソリューション エクスプ ローラーでダブルクリック **[ordershipping.wsdl.odx]** します。  

22. オーケストレーションの種類 ウィンドウで、**の種類、マルチパート メッセージの種類**します。  

23. 展開**InvoiceAckMessageType**し **[invoiceackmessagepart]** します。  

24. [プロパティ] ウィンドウで、展開、**型**フィールドを選択します**参照されたアセンブリからのスキーマと選択**。  

25. **成果物の種類の選択**ダイアログ ボックスで、 をクリックして**ShippingSchemas**を選択します、 **Imported_InvoiceAckMessage**を入力し、クリックして**OK**.  

    > [!NOTE]
    >  手順 23 ~ 25 では、ShippingSchemas で説明されている対応するメッセージの種類、BPEL プロセスに参加しているサービスのメッセージの種類を置き換えます。  

26. 次の値を使用してメッセージの種類ごとにステップ 23 ~ 25 を繰り返します。  


    |          メッセージ部分          |                    メッセージ型                     |
    |--------------------------------|-----------------------------------------------------|
    |       InvoiceMessagePart       |       ShippingSchemas.Imported_InvoiceMessage       |
    |      OrderAckMessagePart       |      ShippingSchemas.Imported_OrderAckMessage       |
    |        OrderMessagePart        |        ShippingSchemas.Imported_OrderMessage        |
    | PaymentConfirmationMessagePart | ShippingSchemas.Imported_PaymentConfirmationMessage |
    | PickupNotificationMessagePart  | ShippingSchemas.Imported_PickupNotificationMessage  |
    |  ShipConfirmationMessagePart   |  ShippingSchemas.Imported_ShipConfirmationMessage   |
    |      ShippingHistoryPart       |      ShippingSchemas.Imported_ShippingHistory       |
    |   ShipRequestAckMessagePart    |   ShippingSchemas.Imported_ShipRequestAckMessage    |
    |     ShipRequestMessagePart     |     ShippingSchemas.Imported_ShipRequestMessage     |
    |     ShipStatusMessagePart      |     ShippingSchemas.Imported_ShipStatusMessage      |


27. ソリューション エクスプ ローラーで右クリックし、 **BPELShipping**プロジェクトをポイントして、**追加**、 をクリックし、**既存項目の**。  

28. すべての .btm ファイルの場所から選択\<*サンプル パス*\>\Orchestrations\BPELImport\Solution\BPELShipping\BPELShipping します。  

29. オーケストレーションの種類 ウィンドウで、**メッセージの割り当て**ConstructMessage1 である MessageAssignment_1 という名前の図形し、それを削除します。  

30. ツールボックスからドラッグして、**変換**図形を ConstructMessage1 図形にします。  

31. プロパティ ウィンドウで、省略記号ボタンをクリックします (**...**) を開くと、**変換の構成** ダイアログ ボックス。  

32. 選択**既存のマップ**します。  

33. 選択、完全修飾マップ名として **[bpelshipping.order2shiprequest]** します。  

34. ソースとして選択**順序。OrderMessagePart**します。  

35. 変換先として選択**ship_request します。ShipRequestMessagePart**クリック**OK**します。  

36. 各ステップ 29 ~ 35 を繰り返し、**メッセージの割り当て**図形し、置き換え**変換**次の表に従って図形。  


    |  置き換える図形   |              マップを使用するには              |      ソース ドキュメント       |       宛先のドキュメント        |
    |---------------------|--------------------------------------|----------------------------|-----------------------------------|
    | MessageAssignment_2 |     BPELShipping.Order2OrderAck      |   順序。OrderMessagePart   |   order_ack します。OrderAckMessagePart   |
    | MessageAssignment_3 |     BPELShipping.Order2OrderNAck     |   順序。OrderMessagePart   |   order_ack します。OrderAckMessagePart   |
    | MessageAssignment_4 |    BPELShipping.Order2ShipHistory    |   順序。OrderMessagePart   | ship_history します。ShippingHistoryPart  |
    | MessageAssignment_5 |  BPELShipping.ShipHistory2Completed  |   順序。OrderMessagePart   | ship_history します。ShippingHistoryPart  |
    | MessageAssignment_6 |       BPELShipping.Invoice2Ack       | 請求書。InvoiceMessagePart | invoice_ack します。[Invoiceackmessagepart] |
    | MessageAssignment_7 | BPELShipping.Order2FinalConfirmation |   順序。OrderMessagePart   | order_shipped します。OrderAckMessagePart |


37. オーケストレーションを保存します。  

38. ダブルクリック **[rule_1]** で、**判断**図形**Decision_1**します。  

39. BizTalk 式エディターで置き換えます  

     ship_request_ack(BPELShipping.Ship_Acknowledged) true = =  

     これを次の行に置き換えます。  

     ship_request_ack(ShippingSchemas.Ship_Acknowledged) true = =  

40. ダブルクリックして、**ループ**という名前の図形**Loop_1**します。  

41. BizTalk 式エディターで置き換えます  

     ship_history(BPELShipping.Ship_Completed) true = =  

     これを次の行に置き換えます。  

     ship_history(ShippingSchemas.Ship_Completed) == true  

42. ダブルクリック**Rule_2**で、**判断**図形**Decision_2**します。  

43. BizTalk 式エディターで置き換えます  

     ship_status(BPELShipping.ShipStatus) == "DONE"  

     これを次の行に置き換えます。  

     ship_status(ShippingSchemas.ShipStatus) == "DONE"  

44. オーケストレーション ビューで、展開**型/関連付けの種類**クリック***OrderCorrelationSet_Type\\***します。  

45. [プロパティ] ウィンドウで、省略記号ボタンをクリックします (**...**) で**関連付けのプロパティ**します。  

46. ウィンドウに関連付けるプロパティで、次のようにクリックします。 **bpelshipping.orderid**、 をクリックし、**削除**します。  

47. 使用可能なプロパティ ウィンドウで  **Shippingschemas**を選択します**注文 ID**、 をクリックし、**追加**。  

48. **[OK]** をクリックします。  

49. すべてのファイルを保存し、ソリューションをビルドします。  

50. ソリューションを展開する。  

51. 場所を参照\<*サンプル パス*\>\Orchestrations\BPELImport\Solution\BPELShipping をダブルクリックします**BindAndStartOnly.bat**をバインドして開始しますオーケストレーションです。  

## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 *\<パスのサンプル\>* \Orchestrations\BPELImport  

 次の表は、このサンプルのファイルとその目的を示しています。  

|ファイル|説明|  
|---------------|-----------------|  
|BPELSource\InvoiceAckMessage.xsd|請求書の受信確認のスキーマです。|  
|BPELSource\InvoiceMessage.xsd|請求書スキーマです。|  
|BPELSource\OrderAckMessage.xsd|注文の受信確認のスキーマです。|  
|BPELSource\OrderHeader.xsd|注文ヘッダーのスキーマです。|  
|BPELSource\OrderMessage.xsd|発注書メッセージのスキーマ。|  
|BPELSource\OrderShipping.wsdl|BPEL で参照される WSDL ファイル。|  
|BPELSource\OrderShippingProcess.bpel|BPEL プロセス フローです。|  
|BPELSource\PaymentConfirmationMessage.xsd|支払い確認メッセージです。|  
|BPELSource\PickupNotificationMessage.xsd|ピックアップ通知メッセージです。|  
|BPELSource\ShipConfirmationMessage.xsd|出荷確認メッセージです。|  
|BPELSource\ShippingHistory.xsd|出荷履歴ドキュメントです。|  
|BPELSource\ShipRequestAckMessage.xsd|出荷要求の受信確認。|  
|BPELSource\ShipRequestMessage.xsd|出荷要求メッセージです。|  
|BPELSource\ShipStatusMessage.xsd|出荷状態メッセージです。|  
|Solution\bindings\BPELBindings.xml|BPELShipping オーケストレーションのポートのバインドを指定するバインド ファイルです。|  
|Solution\bindings\ShipperBindings.xml|ShipperProcess オーケストレーションのポートのバインドを指定するバインド ファイルです。|  
|Solution\BPELShipping\BindAndStartOnly.bat|バインドおよび手動で構築およびデプロイされた後、BPELImport オーケストレーションを開始するのに使用するバッチ ファイルです。|  
|Solution\BPELShipping\cleanup.bat|BPELShipping プロセスの削除に使用するバッチ ファイル。|  
|Solution\BPELShipping\Setup.bat|使用してインストールし、提供されている BPELShipping サンプルを起動するバッチ ファイルです。|  
|Solution\BPELShipping\BPELShipping.sln|事前構築済みの BPELShipping サンプルです。|  
olution\BPELShipping\BPELShipping\Invoice2Ack.btm|受信確認のマップの請求書を請求します。|  
|Solution\BPELShipping\BPELShipping\Order2FinalConfirmation.btm|注文メッセージから最終的な出荷確認に変換するマップです。|  
|Solution\BPELShipping\BPELShipping\Order2OrderAck.btm|注文メッセージから注文書受信確認に変換するマップです。|  
|Solution\BPELShipping\BPELShipping\Order2OrderNack.btm|注文メッセージから注文否定受信確認応答に変換するマップです。|  
|Solution\BPELShipping\BPELShipping\Order2ShipHistory.btm|注文メッセージから出荷履歴ドキュメントに変換するマップします。|  
|Solution\BPELShipping\BPELShipping\Order2ShipRequest.btm|注文メッセージを注文出荷要求から変換するマップします。|  
|Solution\BPELShipping\BPELShipping\ShipRequest2Completed.btm|出荷履歴を完了に設定するマップです。|  
|Solution\ShipperProcess\setup.bat|バッチ ファイルをビルドするには、展開し、バインド、ShipperProcess ヘルパー オーケストレーションとそのポートを開始します。|  
|Solution\ShipperProcess\cleanup.bat|停止、参加解除、および ShipperProcess ヘルパー オーケストレーションとそのポートを展開解除するバッチ ファイルです。|  

## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 最初の手順をビルドして Wide World importers 社をシミュレートするために使用する ShipperProcess アプリケーションを初期化します。  

#### <a name="to-build-and-initialize-the-shipperprocess-application"></a>ビルドし、ShipperProcess アプリケーションを初期化するには  

1. 開始**Visual Studio コマンド プロンプト**します。  

2. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプトでディレクトリ変更コマンド (**cd**) 次のフォルダーに。  

    *\<Samples Path\>* \Orchestrations\BPELImport\Solution\ShipperProcess  

3. ファイルは、次の操作を実行します。 Setup.bat を実行します。  

   -   、、ShipperProcess および BPELShipping プロセスで使用されるスキーマを含む ShippingSchemas プロジェクトをビルドします。  

   -   ShipperProcess をビルドします。  

   -   ShippingSchemas と ShipperProcess プロジェクトをデプロイします。  

   -   ShipperProcess で使用されるポートの受信の作成と送信のバインド  

   -   ShipperProcess で使用されるポートを開始します  

   -   参加させ、ShipperProcess オーケストレーションの開始  

   エラーが報告されていないこと、ビルドおよび初期化プロセス中にこのサンプルを実行する前に確認してください。 1 つ以上の次の警告が表示されます。これらを無視することができます。  

```  
The 'http://contoso.org/samples/Fragments:XXXX' element is not declared. An error occurred at , (35, 16).  
<SAMPLE_LOCATION>\Orchestrations\BPELImport\Solution\ShipperProcess\ShipperProcess\ShipperProcess.odx(701,13): warning X4014: convoy processing will not occur -- check your protocol if you were expecting it  
<SAMPLE_LOCATION>\Samples\Orchestrations\BPELImport\Solution\ShipperProcess\ShipperProcess\ShipperProcess.odx(667,22): convoy found at 'activate receive(Receive_ShipOrder.Operation_1, Request, initialize Correl)'  
<SAMPLE_LOCATION>\Samples\Orchestrations\BPELImport\Solution\ShipperProcess\ShipperProcess\ShipperProcess.odx(701,13): and 'receive(ReceiveInvoiceAck.Operation_1, Invoice_Ack, Correl)'  
```  

> [!NOTE]
>  "BPEL からインポートし、実用的なソリューションをビルドします"に記載の手順を完了している場合は、次の手順を実行する必要はありません。  

#### <a name="to-build-and-initialize-the-bpelshipping-application"></a>ビルドおよび BPELShipping アプリケーションを初期化するには  

1. > [!WARNING]
   >  次の手順を実行する前に使用権を持って「をビルドおよび初期化する ShipperProcess アプリケーション」上記の手順を完了する必要があります。  

    [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプトでディレクトリ変更コマンド (**cd**) 次のフォルダーに。  

    *\<パスのサンプル\>* \Orchestrations\BPELImport\Solution\BPELShipping  

2. ファイルは、次の操作を実行します。 Setup.bat を実行します。  

   -   BPELShipping プロジェクトをビルドします  

   -   BPELShipping プロジェクトをデプロイします。  

   -   BPELShipping プロセスで使用されるポートの受信の作成と送信のバインド  

   -   BPELShipping プロセスで使用されるポートを開始します  

   -   参加させ、BPELShipping オーケストレーションの開始  

## <a name="running-this-sample"></a>このサンプルの実行  

#### <a name="to-run-the-bpel-import-sample"></a>BPEL インポート サンプルを実行するには  

1.  コピー、 **Order.xml**ファイルから、 *\<サンプル パス\>* \Orchestrations\BPELImport\Solution フォルダーから、 \<*サンプル パス\>* \Orchestrations\BPELImport\Solution\Ports\ReceiveOrder フォルダー。  

2.  出荷プロセスを通じて、BPELShipping オーケストレーションが顧客の注文処理システムから注文書としてこのファイルが取得が実行され、ファイルが 1 つでそれぞれ、 \<*サンプル パス*\>\Orchestrations\BPELImport\Solution\Ports\SendOrder フォルダーと\<*サンプル パス*\>\Orchestrations\BPELImport\Solution\Ports\FinalConfirmation フォルダー。 これらのファイルの名前の形式が\< *MessageID*\>、.xml、 *\<MessageID\>* 一意に識別する GUID が生成、メッセージ。  

## <a name="uninstalling-this-sample"></a>このサンプルのアンインストール  

#### <a name="to-uninstall-the-bpel-import-sample"></a>BPEL インポート サンプルをアンインストールするには  

1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプトでディレクトリ変更コマンド (**cd**) に\<*サンプル パス*\>\Orchestrations\BPELImport\BPELShipping します。  

2. Cleanup.bat を実行します。  

3. 参照する\<*サンプル パス*\>\Orchestrations\BPELImport\ShipperProcess します。  

4. Cleanup.bat を実行します。  

## <a name="see-also"></a>参照  
 [オーケストレーション (BizTalk Server サンプル フォルダー)](../core/orchestrations-biztalk-server-samples-folder.md)