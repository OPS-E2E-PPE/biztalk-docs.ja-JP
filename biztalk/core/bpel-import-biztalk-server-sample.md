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
ms.openlocfilehash: 62eb5603ffca6f22e0e22f185886d0cfefb17746
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012555"
---
# <a name="bpel-import-biztalk-server-sample"></a>BPEL インポート (BizTalk Server サンプル)
BPEL インポート サンプルは、BPEL (Business Process Execution Language) 処理の記述ファイルと関連アイテムを利用してオーケストレーションを作成する方法を示すものです。  

## <a name="what-this-sample-does"></a>このサンプルの処理  
 Wide World Importers 社は、小売業者に自動出荷サービスを提供する出荷業者です。 具体的には、Wide World Importers 社は小売業者に次のサービスを提供しています。  

- 注文の出荷要求  

- 出荷の追跡  

- 出荷の確認  

- 出荷に対する請求書発行と支払いの確認  

  これらのサービスを利用できるかどうかは WSDL (Web Services Description Language) ドキュメントを使用して表すことができます。BPEL ドキュメントでは、製造業者がサービスを呼び出す通常の方法と Wide World Importers 社からの応答方法が記述されます。  

  Northwind Traders という会社が Wide World Importers 社に出荷処理を委託した場合、Northwind Traders 社は全体的な情報のやり取りを記述した BPEL ファイルと関連アイテムを受け取ります。 Northwind Traders 社はこの BPEL ファイルを使用して [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーション (BPELShipping) を作成し、Wide World Importers 社を介して自動的に注文を処理できます。  

  このサンプルでは、BPELShipping アプリケーションで次のシナリオを実行します。  

1. Northwind Traders 社の顧客注文システムから注文を受信します。  

2. Wide World Importers 社に出荷要求を送信し確認を求めます。  

3. Wide World Importers 社から出荷要求の確認を受信します。  

4. Wide World Importers 社からピックアップ通知を受信します。  

5. 出荷製品が顧客に配送され、受理されるまでの出荷状況メッセージを受信します。  

6. Wide World Importers 社から請求書を受信します。  

7. Wide World Importers 社に請求書受領の応答を返します。  

8. Wide World Importers 社から支払い確認を受信します。  

9. 注文システムに最終的な出荷確認を送信します。  

   このサンプルでは、個別の BizTalk アプリケーション (ShipperProcess) を使用して、Wide World Importers 社の役割をシミュレートします。 BPELShipping アプリケーションは、FILE トランスポートを介して ShipperProcess と通信します。ここでは、通信用に共通のファイル システムの場所が使用されます。  

## <a name="how-this-sample-is-designed-and-why"></a>このサンプルのデザイン方法とその理由  
 BPEL for Web Services はビジネス プロセスを記述する XML ベースの言語で、異なる企業間で Web サービスを使用して取引する場合に、ビジネス プロセスを簡単に共有できるようにするものです。 BPEL ではビジネス プロトコル レベルでビジネス プロセスの処理方法を記述します。パートナーから受信した注文書の処理など、企業内部で行うプロセスについては記述しません。 このサンプルでは、BPEL ファイルとそれに対応する WSDL ファイルをインポートし、これらのファイルをオーケストレーションに変換した後、パートナーとのビジネス プロセスを開始する方法を示します。  

 以下は、BPEL ファイルと WSDL ファイルをインポートし、これらのファイルをオーケストレーションに変換して、ビルド済みの BizTalk アプリケーション (ShipperProcess) とやり取りする場合の一連の手順です。 この手順を完了した場合、「BPELShipping アプリケーションをビルドおよび初期化するには」に示されている手順を実行する必要はありません。  

#### <a name="to-import-from-bpel-and-build-a-working-solution"></a>BPEL からインポートして実際のソリューションをビルドするには  

1. Microsoft で[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]の**ファイル** メニューのをクリックして**新規**、 をクリックし、**プロジェクト**。  

   > [!NOTE]
   >  この手順を完了する前に、サポートのプロセスとスキーマのプロジェクトを作成する ShipperProcess アプリケーションを設定する必要があります。  

2. **新しいプロジェクト** ダイアログ ボックスで、プロジェクトの種類 ウィンドウで**BizTalk (プロジェクト)** します。 [テンプレート] ペインで選択**BizTalk Server BPEL インポート プロジェクト**します。  

3. **名前**ボックスに、入力**BPELShipping**します。  

   > [!NOTE]
   >  別の名前を使用すると、最後のバインド ステップで問題が発生する場合があります。  

4. プロジェクトの場所を選択し、クリックして**OK** BPEL インポート ウィザードを開始します。  

5. **へようこそ**  ページで **次**します。  

6. **選択 BPEL、WSDL、および XSD ファイル**] ページで [**参照**します。  

7. すべてのファイルを選択、 \<*サンプル パス*\>\Orchestrations\BPELImport\BPELSource フォルダー、 をクリックして**オープン**、順にクリックします**次**.  

   > [!NOTE]
   >  このステップでは、ビジネス プロセスを記述する BPEL ファイルと WSDL ファイル、およびビジネス ドキュメント スキーマを表す XSD ファイルを選択します。  

8. **呼び出した WebServices 用の WSDL ファイルの選択**] ページで [**完了**します。  

9. BPEL インポート ウィザードにインポートが正常に完了したことが表示されたら、ウィザードを閉じます。 これでプロジェクトが作成されます。  

10. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプトでディレクトリ変更コマンド (**cd**) プロジェクトの場所にします。  

11. 次のコマンドを実行します。  

     **sn – k BPELShipping.snk**  

12. ソリューション エクスプ ローラーで右クリックし、 **BPELShipping**プロジェクトをクリックして**プロパティ**します。  

13. **Common properties \assembly**、アセンブリ キー ファイルを選択**BPELShipping.snk**ステップ 11 で作成され、順にクリックします**OK**します。  

14. ソリューション エクスプローラーで、すべての .xsd ファイルを選択して削除します。  

15. ソリューション エクスプ ローラーで選択**参照の追加**、し、**プロジェクト**] タブで [**参照**します。  

16. 選択**ShippingSchemas.dll**の場所から\<*サンプル パス*\>\Orchestrations\BPELImport\Solution\ShipperProcess\ShippingSchemas\bin\Development とクリックして**OK**します。  

    > [!NOTE]
    >  このビルド方法については、「ShipperProcess アプリケーションをビルドおよび初期化するには」で説明します。  

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
    >  ステップ 23 ～ 25 では、BPEL プロセスに参加しているサービスのメッセージの種類を、ShippingSchemas で記述されている対応するメッセージの種類に置き換えます。  

26. メッセージの種類ごとに、次の値を使用してステップ 23 ～ 25 を繰り返します。  


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

31. プロパティ ウィンドウで、省略記号ボタンをクリックします (**.**) を開くと、**変換の構成** ダイアログ ボックス。  

32. 選択**既存のマップ**します。  

33. 選択、完全修飾マップ名として **[bpelshipping.order2shiprequest]** します。  

34. ソースとして選択**順序。OrderMessagePart**します。  

35. 変換先として選択**ship_request します。ShipRequestMessagePart**クリック**OK**します。  

36. 各ステップ 29 ~ 35 を繰り返し、**メッセージの割り当て**図形し、置き換え**変換**次の表に従って図形。  


    |  置き換える図形   |              使用するマップ              |      置き換え元ドキュメント       |       置き換え先ドキュメント        |
    |---------------------|--------------------------------------|----------------------------|-----------------------------------|
    | MessageAssignment_2 |     BPELShipping.Order2OrderAck      |   order.OrderMessagePart   |   order_ack.OrderAckMessagePart   |
    | MessageAssignment_3 |     BPELShipping.Order2OrderNAck     |   order.OrderMessagePart   |   order_ack.OrderAckMessagePart   |
    | MessageAssignment_4 |    BPELShipping.Order2ShipHistory    |   order.OrderMessagePart   | ship_history.ShippingHistoryPart  |
    | MessageAssignment_5 |  BPELShipping.ShipHistory2Completed  |   order.OrderMessagePart   | ship_history.ShippingHistoryPart  |
    | MessageAssignment_6 |       BPELShipping.Invoice2Ack       | invoice.InvoiceMessagePart | invoice_ack.InvoiceAckMessagePart |
    | MessageAssignment_7 | BPELShipping.Order2FinalConfirmation |   order.OrderMessagePart   | order_shipped.OrderAckMessagePart |


37. オーケストレーションを保存します。  

38. ダブルクリック **[rule_1]** で、**判断**図形**Decision_1**します。  

39. BizTalk 式エディターで、次の部分を探します。  

     ship_request_ack(BPELShipping.Ship_Acknowledged) == true  

     これを次の行に置き換えます。  

     ship_request_ack(ShippingSchemas.Ship_Acknowledged) == true  

40. ダブルクリックして、**ループ**という名前の図形**Loop_1**します。  

41. BizTalk 式エディターで、次の部分を探します。  

     ship_history(BPELShipping.Ship_Completed) == true  

     これを次の行に置き換えます。  

     ship_history(ShippingSchemas.Ship_Completed) == true  

42. ダブルクリック**Rule_2**で、**判断**図形**Decision_2**します。  

43. BizTalk 式エディターで、次の部分を探します。  

     ship_status(BPELShipping.ShipStatus) == "DONE"  

     これを次の行に置き換えます。  

     ship_status(ShippingSchemas.ShipStatus) == "DONE"  

44. オーケストレーション ビューで、展開**型/関連付けの種類**クリック***OrderCorrelationSet_Type\\***します。  

45. [プロパティ] ウィンドウで、省略記号ボタンをクリックします (**.**) で**関連付けのプロパティ**します。  

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
|BPELSource\InvoiceAckMessage.xsd|請求書の受信確認応答スキーマです。|  
|BPELSource\InvoiceMessage.xsd|請求書スキーマです。|  
|BPELSource\OrderAckMessage.xsd|注文書の受信確認応答スキーマです。|  
|BPELSource\OrderHeader.xsd|注文書ヘッダー スキーマです。|  
|BPELSource\OrderMessage.xsd|注文書メッセージ スキーマです。|  
|BPELSource\OrderShipping.wsdl|BPEL で参照されている WSDL ファイルです。|  
|BPELSource\OrderShippingProcess.bpel|BPEL プロセス フローです。|  
|BPELSource\PaymentConfirmationMessage.xsd|支払い確認メッセージです。|  
|BPELSource\PickupNotificationMessage.xsd|ピックアップ通知メッセージです。|  
|BPELSource\ShipConfirmationMessage.xsd|出荷確認メッセージです。|  
|BPELSource\ShippingHistory.xsd|出荷履歴ドキュメントです。|  
|BPELSource\ShipRequestAckMessage.xsd|出荷要求の受信確認応答です。|  
|BPELSource\ShipRequestMessage.xsd|出荷要求メッセージです。|  
|BPELSource\ShipStatusMessage.xsd|出荷状態メッセージです。|  
|Solution\bindings\BPELBindings.xml|BPELShipping オーケストレーションのポートのバインドを指定するバインド ファイルです。|  
|Solution\bindings\ShipperBindings.xml|ShipperProcess オーケストレーションのポートのバインドを指定するバインド ファイルです。|  
|Solution\BPELShipping\BindAndStartOnly.bat|手動でビルドし展開した BPELImport オーケストレーションを、バインドおよび開始するときに使用するバッチ ファイルです。|  
|Solution\BPELShipping\cleanup.bat|BPELShipping プロセスの削除に使用するバッチ ファイルです。|  
|Solution\BPELShipping\Setup.bat|提供されている BPELShipping サンプルをインストールおよび開始するときに使用するバッチ ファイルです。|  
|Solution\BPELShipping\BPELShipping.sln|ビルド済みの BPELShipping サンプルです。|  
olution\BPELShipping\BPELShipping\Invoice2Ack.btm|請求書と請求書の受信確認応答を関連付けるマップです。|  
|Solution\BPELShipping\BPELShipping\Order2FinalConfirmation.btm|注文書メッセージを最終的な出荷確認に変換するマップです。|  
|Solution\BPELShipping\BPELShipping\Order2OrderAck.btm|注文書メッセージを注文書の受信確認応答に変換するマップです。|  
|Solution\BPELShipping\BPELShipping\Order2OrderNack.btm|注文書メッセージを注文書の否定応答に変換するマップです。|  
|Solution\BPELShipping\BPELShipping\Order2ShipHistory.btm|注文書メッセージを出荷履歴ドキュメントに変換するマップです。|  
|Solution\BPELShipping\BPELShipping\Order2ShipRequest.btm|注文書メッセージを注文出荷要求に変換するマップです。|  
|Solution\BPELShipping\BPELShipping\ShipRequest2Completed.btm|出荷履歴を完了に設定するマップです。|  
|Solution\ShipperProcess\setup.bat|ShipperProcess ヘルパー オーケストレーションとそのポートをビルド、展開、バインド、および開始するためのバッチ ファイルです。|  
|Solution\ShipperProcess\cleanup.bat|ShipperProcess ヘルパー オーケストレーションとそのポートを停止、参加解除、および展開解除するためのバッチ ファイルです。|  

## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 最初のステップでは、Wide World Importers 社の役割をシミュレートするために使用する ShipperProcess アプリケーションをビルドおよび初期化します。  

#### <a name="to-build-and-initialize-the-shipperprocess-application"></a>ShipperProcess アプリケーションをビルドおよび初期化するには  

1. 開始**Visual Studio コマンド プロンプト**します。  

2. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプトでディレクトリ変更コマンド (**cd**) 次のフォルダーに。  

    *\<パスのサンプル\>* \Orchestrations\BPELImport\Solution\ShipperProcess  

3. ファイルは、次の操作を実行します。 Setup.bat を実行します。  

   -   ShipperProcess および BPELShipping プロセスで使用されるスキーマを含む ShippingSchemas プロジェクトをビルドします。  

   -   ShipperProcess をビルドします。  

   -   ShippingSchemas プロジェクトと ShipperProcess プロジェクトを展開します。  

   -   ShipperProcess で使用される送信ポートと受信ポートを作成しバインドします。  

   -   ShipperProcess で使用されるポートを開始します。  

   -   ShipperProcess オーケストレーションを参加させ、開始します。  

   このサンプルを実行する前に、ビルド処理および初期化処理でエラーが報告されていないことを確認してください。 次の警告が 1 つ以上表示される場合がありますが、これらの警告は無視できます。  

```  
The 'http://contoso.org/samples/Fragments:XXXX' element is not declared. An error occurred at , (35, 16).  
<SAMPLE_LOCATION>\Orchestrations\BPELImport\Solution\ShipperProcess\ShipperProcess\ShipperProcess.odx(701,13): warning X4014: convoy processing will not occur -- check your protocol if you were expecting it  
<SAMPLE_LOCATION>\Samples\Orchestrations\BPELImport\Solution\ShipperProcess\ShipperProcess\ShipperProcess.odx(667,22): convoy found at 'activate receive(Receive_ShipOrder.Operation_1, Request, initialize Correl)'  
<SAMPLE_LOCATION>\Samples\Orchestrations\BPELImport\Solution\ShipperProcess\ShipperProcess\ShipperProcess.odx(701,13): and 'receive(ReceiveInvoiceAck.Operation_1, Invoice_Ack, Correl)'  
```  

> [!NOTE]
>  「BPEL からインポートして実際のソリューションをビルドするには」に記載されている手順を完了した場合、次の手順を実行する必要はありません。  

#### <a name="to-build-and-initialize-the-bpelshipping-application"></a>BPELShipping アプリケーションをビルドおよび初期化するには  

1. > [!WARNING]
   >  以下の手順を実行する前に、「ShipperProcess アプリケーションをビルドおよび初期化するには」の手順を完了しておく必要があります。  

    [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプトでディレクトリ変更コマンド (**cd**) 次のフォルダーに。  

    *\<パスのサンプル\>* \Orchestrations\BPELImport\Solution\BPELShipping  

2. ファイルは、次の操作を実行します。 Setup.bat を実行します。  

   -   BPELShipping プロジェクトをビルドします。  

   -   BPELShipping プロジェクトを展開します。  

   -   BPELShipping プロセスで使用される送信ポートと受信ポートを作成しバインドします。  

   -   BPELShipping プロセスで使用されるポートを開始します。  

   -   BPELShipping オーケストレーションを参加させ、開始します。  

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