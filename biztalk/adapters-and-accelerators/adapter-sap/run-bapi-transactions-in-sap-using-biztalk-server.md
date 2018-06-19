---
title: BizTalk Server を使用して SAP でトランザクションを BAPI を実行 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75ff5cf7-5e98-4d74-a13f-4de65c215d41
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79cfa3f1b799c4a96cdad7f4c9b89b4b594dc4d8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967952"
---
# <a name="run-bapi-transactions-in-sap-using-biztalk-server"></a>BizTalk Server を使用して SAP でトランザクションを BAPI を実行します。
[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]により、トランザクションを実行する SAP システムで使用して、クライアントはアダプター[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 トランザクションのオーケストレーションを作成する前に、まずトランザクションを実行する基本的なシナリオを理解する必要があります。 通常のトランザクションのシナリオで要求メッセージ (BAPI の呼び出し) などの複数の操作は SAP システムへ送信します。 これが参照されますとして、「操作のメッセージ」 オーケストレーションは、各操作メッセージを要求メッセージから抽出し、SAP システムに個別の操作のメッセージを送信する必要があります。 オーケストレーションに送信した後、同じ接続を使用して他のいずれか。 オーケストレーションは、BizTalk マップを使用して XML 変換を使用して、「操作のメッセージ」から個々 のメッセージを抽出します。  
  
 操作が実行されると、オーケストレーションは必要がありますをコミットするか、それぞれ BAPI_TRANSACTION_COMMIT または BAPI_TRANSACTION_ROLLBACK、メッセージを送信することによって、トランザクションを中止します。 これらが参照されます「トランザクション メッセージ」として  
  
## <a name="how-does-the-adapter-enable-transactions-through-biztalk-server"></a>アダプターが BizTalk Server を使用したトランザクションを有効する方法  
 使用して SAP システムでのトランザクションを有効にする、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]:  
  
-   メッセージ コンテキスト プロパティを開く、再利用、CLOSE、および ABORT を提供します。  
  
-   コミットまたはアボート操作 BAPI_TRANSACTION_COMMIT と BAPI_TRANSACTION_ROLLBACK を使用します。 これらは、SAP システムで公開されます。  
  
 次の表に、BAPI_TRANSACTION_COMMIT または BAPI_TRANSACTION_ROLLBACK でプロパティの使用に関するガイドラインを示します。  
  
|メッセージ|OPEN|再利用します。|CLOSE|中止|  
|-------------|----------|-----------|-----------|-----------|  
|最初のメッセージ (メッセージを操作する)|可|いいえ|いいえ|不可|  
|後続のメッセージ (メッセージの操作)|不可|可|いいえ|不可|  
|BAPI_TRANSACTION_COMMIT (トランザクション メッセージ)|不可|いいえ|可|不可|  
|BAPI_TRANSACTION_ROLLBACK (トランザクション メッセージ)|不可|いいえ|はい|可|  
  
 テーブルでは、"Yes"は、メッセージに使用するメッセージ コンテキスト プロパティを示します。 同様に、"No"は、メッセージと共に使用することはできません、メッセージ コンテキスト プロパティを表します。  
  
 テーブルを要約。  
  
-   最初のメッセージが操作メッセージを常にする必要があり、開いているプロパティのみを使用する必要があります。  
  
-   後続の操作メッセージには、再利用プロパティを使用する必要があります。  
  
-   BAPI_TRANSACTION_COMMIT に対応するトランザクションのコミット トランザクション メッセージには、閉じるプロパティを使用する必要があります。  
  
-   トランザクションを中止する BAPI_TRANSACTION_ROLLBACK に対応するトランザクション メッセージには、終了または中止のいずれかのプロパティを使用できます。 ABORT を使用する場合は理想的には、メッセージがオーケストレーションの例外ブロックでなければなりません。  
  
## <a name="key-considerations-related-to-transactions-using-biztalk-server"></a>BizTalk Server を使用してトランザクションに関連するキーの考慮事項  
  
-   オーケストレーションに 2 つ以上の送信ポートがある場合、アダプターは各ポートから受信したメッセージのトランザクションを自動的に分割します。 つまり、トランザクションがポートにまたがることはできません。  
  
-   メッセージの再試行回数は、SAP トランザクション内のメッセージに対してはサポートされていません。 そのため、ユーザーは、ゼロにメッセージの再試行を設定する必要があります。  
  
-   アダプターは、前の表に「いいえ」としてマークされている、組み合わせのため、望ましくない結果を生じる可能性があります。 "Yes"としてマークされている組み合わせを使用する必要があります。  
  
-   メッセージ コンテキスト プロパティがない、アダプターに送信されたメッセージは、現在のトランザクション コンテキストにバインドされないように通常実行されます。  
  
-   BAPI_TRANSACTION_COMMIT または BAPI_TRANSACTION_ROLLBACK 理想的には、オーケストレーションでは、現在のトランザクション コンテキストの最後のメッセージはあります。  
  
 次のセクションでは、SAP でトランザクションを実行する方法の手順を説明する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
## <a name="how-to-perform-a-transaction-on-an-sap-system"></a>SAP システムに対してトランザクションを実行する方法ですか。  
 SAP システムを使用して、操作を実行、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明した手順のタスクでは、 [SAP アプリケーションを作成するビルド ブロック](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)です。 トランザクションを実行する SAP システムで、これらのタスクは。  
  
1.  BizTalk プロジェクトを作成し、トランザクションを実行する RFC のスキーマを生成します。 さらに、BAPI_TRANSACTION_COMMIT と BAPI_TRANSACTION_ROLLBACK Rfc のスキーマを生成する必要があります。  
  
2.  SAP システムからメッセージを送受信するための BizTalk プロジェクトでメッセージを作成します。  
  
3.  要求メッセージから個人「操作のメッセージ」を抽出し、SAP システムに送信するオーケストレーションを作成します。 要求メッセージに基づき、オーケストレーションも判断コミットまたはトランザクションをロールバックするかどうか。  
  
4.  構築し、BizTalk プロジェクトを展開します。  
  
5.  BizTalk アプリケーションを作成する物理送信ポートと受信ポートを構成します。  
  
6.  BizTalk アプリケーションを起動します。  
  
 このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="sample-based-on-this-topic"></a>このトピックの内容に基づくサンプル  
 サンプルは、SAPTransaction、このトピックの内容に基づいてが付属して、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 詳細については、次を参照してください。 [SAP アダプターのサンプル](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)です。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 SAP システムに対してトランザクションを実行する方法を示すためには、次のスキーマが必要です。  
  
-   「操作メッセージ」の SAP システムに対して操作を実行します。 アダプターに送信された要求メッセージは、このスキーマに準拠している必要があります。 操作のノードの任意の数を格納しているユーザーに固有の任意のスキーマを指定できます。 このトピックでは、スキーマ MultipleOrders.xsd が使用されます。 付属しているトランザクションのサンプルの一部として、スキーマが指定されても、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]サンプルです。 詳細については、次を参照してください。[スキーマのサンプル](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)です。  
  
-   RFC を起動するなど、SAP システムでは、操作を実行します。 操作を実行する要求メッセージは、このスキーマに準拠している必要があります。 使用してこのスキーマを生成する必要があります、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]です。 このトピックでは、BAPI_SALESORDER_CREATEFROMDAT2 RFC が呼び出されます。 RFC のスキーマを生成する方法の詳細については、次を参照してください。[参照、検索と get メタデータの SAP RFC 操作](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md)です。  
  
-   中止またはトランザクションをコミットします。 トランザクションをコミットまたは中止する要求は、このスキーマに準拠する必要があります。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] BAPI_TRANSACTION_COMMIT と BAPI_TRANSACTION_ROLLBACK RFC に commit および rollback 操作それぞれ使用します。 使用してこれらの Rfc のスキーマを生成する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。  
  
> [!NOTE]
>  必要なすべてのスキーマが BizTalk プロジェクトに追加されたことを確認する必要があります。  
  
> [!IMPORTANT]
>  BizTalk プロパティ スキーマへの参照を追加する必要があります[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]BizTalk プロジェクトにします。 スキーマ ファイル*Microsoft.Adapters.SAP.BiztalkPropertySchema.dll*がインストールされている、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップでは、通常は\<インストール ドライブ\>: \Program Files\Microsoft BizTalk Adapter Pack\bin です。  
  
## <a name="defining-messages-and-message-types"></a>メッセージとメッセージの種類を定義します。  
 以前に生成したスキーマには、オーケストレーション内のメッセージに対して必要な「種類」がについて説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 BizTalk プロジェクトのオーケストレーションの種類 ウィンドウからのメッセージに最初の手順で生成したスキーマをリンクする必要があります。  
  
 メッセージを作成する前に、(MultipleOrders.xsd 型) の要求メッセージに「操作」ノードの数を決定する必要があります。 この例では、要求メッセージに BAPI_SALESORDER_CREATEFROMDAT2 RFC を呼び出すための 2 つの操作メッセージであると仮定します。 したがって、この RFC に対して生成されたスキーマにマップされる 1 つの要求-応答メッセージ セットを作成する必要があります。  
  
 BizTalk プロジェクトで、次のメッセージを作成する必要があります。  
  
-   SendtoAdapter のメッセージをオーケストレーションに送信される要求メッセージ。 このメッセージは、入力メッセージ、MultipleOrders.xsd のスキーマにマップする必要があります。  
  
-   メッセージ、BAPIMessage、SAP システムに送信される最初の操作。 応答メッセージ BAPIResponse、最初の操作の応答を作成することも必要があります。 要求および応答メッセージは、BAPI_SALESORDER_CREATEFROMDAT2 RFC に対して生成されたスキーマにマップする必要があります。  
  
-   メッセージ、BAPICommitMessage、コミット操作のためです。 応答メッセージ BAPICommitResponse、対応する応答メッセージを作成することも必要があります。 要求および応答メッセージは、BAPI_TRANSACTION_COMMIT RFC のスキーマにマップする必要があります。  
  
-   メッセージ、BAPIRollbackMessage、ロールバック操作のためです。 応答メッセージ BAPIRollbackResponse、対応する応答メッセージを作成することも必要があります。 要求および応答メッセージは、BAPI_TRANSACTION_ROLLBACK RFC のスキーマにマップする必要があります。  
  
 メッセージを作成し、スキーマにそれらをリンクするには、次の手順を実行します。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  既に開かれていない場合は、オーケストレーションの種類、BizTalk プロジェクトを開きます。 をクリックして**ビュー**、 をポイント**その他のウィンドウ**、 をクリック**オーケストレーション**です。  
  
2.  **オーケストレーション ビュー**を右クリックして**メッセージ**、クリックして**新しいメッセージ**です。  
  
3.  右クリックし、メッセージを新しく作成し、[**プロパティ] ウィンドウ**します。  
  
4.  **プロパティ**のウィンドウ**Message_1**次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**SendToAdapter**です。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**を選択して*SAPTransaction.MultipleOrders*ここで、 *SAPTransaction* BizTalk プロジェクトの名前を指定します。 *MultipleOrders*要求メッセージのスキーマです。|  
  
5.  6 つ以上のメッセージを作成する前の手順を繰り返します。 **プロパティ**、新しいメッセージ ウィンドウ、次の操作です。  
  
    |識別子に設定します。|メッセージの種類を設定|  
    |-----------------------|-------------------------|  
    |BAPIMessage|*SAPTransaction.SAPBindingSchema.BAPI_SALESORDER_CREATEFROMDAT2*|  
    |BAPIResponse|*SAPTransaction.SAPBindingSchema.BAPI_SALESORDER_CREATEFROMDAT2Response*|  
    |BAPICommitMessage|*SAPTransaction.SAPBindingSchema.BAPI_TRANSACTION_COMMIT*|  
    |BAPICommitResponse|*SAPTransaction.SAPBindingSchema.BAPI_TRANSACTION_COMMITResponse*|  
    |BAPIRollbackMessage|*SAPTransaction.SAPBindingSchema.BAPI_TRANSACTION_ROLLBACK*|  
    |BAPIRollbackResponse|*SAPTransaction.SAPBindingSchema.BAPI_TRANSACTION_ROLLBACKResponse*|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションを設定します。  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SAP システムでトランザクションを実行するためです。 このオーケストレーションでの要求メッセージを削除する受信場所が、定義されています。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]メッセージを使用して、SAP システムに渡されます。 SAP システムからの応答は、別の場所に保存されます。  
  
 別のオーケストレーションを作成するときに考慮事項:  
  
-   BAPI_SALESORDER_CREATEFROMDAT2 RFC の要求メッセージのスキーマにマップします。  
  
-   BAPI_TRANSACTION_COMMIT と BAPI_TRANSACTION_ROLLBACK RFC の要求メッセージのスキーマにマップします。  
  
 BizTalk マップを使用して XML 変換を使用してスキーマをマップすることができます。 これを実現するには、オーケストレーションの変換図形が含まれます。  
  
 最後に、要求メッセージが、トランザクション コミットまたは中止に情報にするかどうかに基づき、オーケストレーション決定する必要があります、SAP システムに送信される適切なメッセージです。 これを実現するには、オーケストレーションに判断図形を含めます。  
  
 オーケストレーションに含まれる別の図形の詳細については、次を参照してください。、**オーケストレーション デザイナー UI** [!INCLUDE[ui-guidance-developers-reference](../../includes/ui-guidance-developers-reference.md)]です。
  
 SAP トランザクションのサンプルのオーケストレーションには、次のようになります。  
  
 ![SAP でトランザクションを実行するためのオーケストレーション](../../adapters-and-accelerators/adapter-sap/media/727f82e9-51a9-4a94-9d0a-d05c17904bde.gif "727f82e9-51a9-4a94-9d0a-d05c17904bde")  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認してください。 図形の列に表示される名前は、上記のオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveInputXML|Receive|-設定**名前**に*ReceiveInputXML*<br /><br /> -設定**アクティブ**に*は True。*|  
|SendToLOB|Send|-設定**名前**に*SendToLOB*|  
|ReceiveResponse|Receive|-設定**名前**に*ReceiveResponse*<br /><br /> -設定**アクティブ**に*False*|  
|SendResponse|Send|-設定**名前**に*SendResponse*|  
  
 要求メッセージには、2 つの挿入メッセージがあるためは、送信の別のセットを作成し、受信図形のメッセージを SAP に送信して、応答を受信する必要があります。 ただし、挿入メッセージをコミットまたはロールバックされる可能性があります、ために、意思決定ブロック内での図形の 2 番目のセットを作成する必要があります。 コミットの図形の 1 つのセットとロールバックの図形の別のセットを作成する必要があります。  
  
> [!NOTE]
>  ドラッグ アンド BizTalk オーケストレーション ツールボックスから、判断図形をドロップして判断ブロックを追加できます。  
  
#### <a name="message-shapes-for-commit"></a>メッセージの構築図形をコミットします。  
 次の表では、"コミット"のパス、オーケストレーションの図形が一覧表示します。 ここでは、要求メッセージの受信メッセージを作成する必要はありません。 前のメッセージの形状から要求メッセージが渡されます。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|SendBAPICommit|Send|-設定**名前**に*SendBAPICommit*|  
|ReceiveCommitResponse|Receive|-設定**名前**に*ReceiveCommitResponse*<br /><br /> -設定**アクティブ**に*False*|  
|SendResponse2|Send|-設定**名前**に*SendResponse2*|  
  
#### <a name="message-shapes-for-abort"></a>メッセージの構築図形を中止します。  
 次の表では、"rollback"のパス、オーケストレーションの図形が一覧表示します。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|SendBAPIRollback|Send|-設定**名前**に*SendBAPIRollback*|  
|ReceiveRollbackResponse|Receive|-設定**名前**に*ReceiveRollbackResponse*<br /><br /> -設定**アクティブ**に*False*|  
|SendResponse3|Send|-設定**名前**に*SendResponse3*|  
  
### <a name="setting-the-rule-expression"></a>ルール式の設定  
 コミット メッセージの構築図形を含めるし、判断図形を追加することによって判断ブロック内の操作を中止します。 オーケストレーションが意思決定を行うは条件を指定するには、ルール図形に式をトランザクションがするコミットまたはロールバックのベースを指定する必要があります。 たとえば、ルール図形の次の式を指定する必要があります。  
  
```  
SendToAdapter.isCommit == true  
```  
  
 ここで、SendToAdapter は、要求メッセージのスキーマ用に作成したメッセージです。 要求メッセージの場合、`isCommit`にタグが設定されている**True**オーケストレーションは「コミット」のルートです。 それ以外の場合、オーケストレーションは「ロールバック」ルートを受け取ります。  
  
 式エディターでこの条件を指定する、する昇格必要がありますが、`isCommit`アダプターに送信された要求メッセージのメッセージ スキーマ内のプロパティです。 このトピックでは、使用する入力のスキーマは MultipleOrders.xsd です。 昇格する必要があります、`isCommit`このスキーマのプロパティです。 プロパティを昇格させる方法の詳細については、次を参照してください。[プロパティの昇格](../../core/promoting-properties.md)です。
  
### <a name="adding-construct-message-shapes"></a>構築メッセージの構築図形を追加します。  
 既に説明したように、2 つの insert メッセージと、コミットまたは中止メッセージをアダプターに送信された要求メッセージが含まれます。 メッセージの構築図形を追加する必要があり、SAP システムに送信される個々 の操作メッセージを抽出する変換図形の内です。 また、メッセージにトランザクションを有効にするためのコンテキスト プロパティを設定するメッセージの割り当て図形を追加する必要があります。  
  
#### <a name="the-first-construct-message-shape"></a>最初のメッセージの構築図形  
 最初のメッセージの構築図形には、"ReceiveXML"が呼び出されたと仮定します この図形には、"BAPIMessage"として構築メッセージ プロパティを指定します。 開くには変換図形をダブルクリックして、**変換の構成** ダイアログ ボックス。 ダイアログ ボックスで。  
  
-   新しいマップを作成するを選択します。  
  
-   左側のウィンドウから次のように選択します。**ソース**との間、**変数名**ドロップダウン選択*SendToAdapter*です。  
  
-   左側のウィンドウから次のように選択します。**先**との間、**変数名**ドロップダウン選択*BAPIMessage*です。  
  
-   をクリックして**OK**をマッパーを起動します。 要求メッセージのスキーマを BAPI_SALESORDER_CREATEFROMDAT2 のスキーマにマップします。 使用することができます、**インデックス**functoid をソース スキーマと送信先スキーマの間のマップを作成します。 **インデックス**functoid では、一連のレコードの情報を特定のレコードを選択することができます。  
  
     次の図を使用してマッピングされたスキーマを示しています、**インデックス**functoid です。  
  
     ![インデックス functoid を使用してマッピングされたスキーマ](../../adapters-and-accelerators/adapter-sap/media/d0ade577-ea74-4be3-a724-4ba19397d8d3.gif "d0ade577-ea74-4be3-a724-4ba19397d8d3")  
  
     使用しての詳細については、**変換の構成**ダイアログ ボックスを参照してください、**変換の構成 ダイアログ ボックス**[!INCLUDE[ui-guidance-developers-reference](../../includes/ui-guidance-developers-reference.md)]です。
  
     インデックス functoid の使用に関する詳細については、次を参照してください。[インデックス Functoid](../../core/index-functoid.md)です。
       
     スキーマをマップした後は、マップ ファイルのプロパティ ページを使用してマッピングをテストできます。 詳細については、次を参照してください。、  **<Map File>プロパティ ページ ダイアログ ボックスで、マップのテスト**タブ[!INCLUDE[ui-guidance-developers-reference](../../includes/ui-guidance-developers-reference.md)]です。
  
 メッセージの割り当て図形では、トランザクションの開始をメッセージ コンテキスト プロパティを指定します。 たとえば、最初のメッセージをメッセージ コンテキスト プロパティ可能性があります。  
  
```  
BAPIMessage(Microsoft.Adapters.SAP.BiztalkPropertySchema.ConnectionState) = "OPEN";  
```  
  
#### <a name="the-commit-construct-message-shape"></a>コミット メッセージの構築図形  
 コミット操作のメッセージの構築図形には、"CommitMessage"が呼び出されたとします この図形には、"BAPICommitMessage"として構築メッセージ プロパティを指定します。 開くには変換図形をダブルクリックして、**変換の構成** ダイアログ ボックス。 ダイアログ ボックスで。  
  
-   新しいマップを作成するを選択します。  
  
-   左側のウィンドウから次のように選択します。**ソース**との間、**変数名**ドロップダウン選択*SendToAdapter*です。  
  
-   左側のウィンドウから次のように選択します。**先**との間、**変数名**ドロップダウン選択*BAPICommitMessage*です。  
  
-   マッパーを起動するには、[ok] をクリックします。 要求メッセージのスキーマを BAPI_TRANSACTION_COMMIT のスキーマにマップします。 BAPI_TRANSACTION_COMMIT ノードには、レコードの階層が含まれていないためにこのマッピング インデックス functoid を含める必要はありません。  
  
 メッセージの割り当て図形では、トランザクションをコミットするメッセージ コンテキスト プロパティを指定します。 たとえば、最初のメッセージをメッセージ コンテキスト プロパティ可能性があります。  
  
```  
BAPICommitMessage(Microsoft.Adapters.SAP.BiztalkPropertySchema.ConnectionState) = "CLOSE";  
```  
  
#### <a name="the-rollback-construct-message-shape"></a>ロールバック メッセージの構築図形  
 ロールバック操作のメッセージの構築図形には、"RollbackMessage"が呼び出されたとします この図形には、"BAPIRollbackMessage"として構築メッセージ プロパティを指定します。 開くには変換図形をダブルクリックして、**変換の構成** ダイアログ ボックス。 ダイアログ ボックスで。  
  
-   新しいマップを作成するを選択します。  
  
-   左側のウィンドウから次のように選択します。**ソース**との間、**変数名**ドロップダウン選択*SendToAdapter*です。  
  
-   左側のウィンドウから次のように選択します。**先**との間、**変数名**ドロップダウン選択*BAPIRollbackMessage*です。  
  
-   マッパーを起動するには、[ok] をクリックします。 要求メッセージのスキーマを BAPI_TRANSACTION_ROLLBACK のスキーマにマップします。 BAPI_TRANSACTION_ROLLBACK ノードには、レコードの階層が含まれていないためにこのマッピング インデックス functoid を含める必要はありません。  
  
 メッセージの割り当て図形では、ロールバック、トランザクションをメッセージ コンテキスト プロパティを指定します。 たとえば、最初のメッセージをメッセージ コンテキスト プロパティ可能性があります。  
  
```  
BAPIRollbackMessage(Microsoft.Adapters.SAP.BiztalkPropertySchema.ConnectionState) = "ABORT";  
```  
  
> [!IMPORTANT]
>  一般的には、例外ブロックで中止コンテキスト プロパティを持つ BAPI_TRANSACTION_ROLLBACK に対応するメッセージを使用する必要があります。  
  
### <a name="adding-ports"></a>ポートの追加  
 論理ポートごとに、次のプロパティを指定することを確認してください。 示されている名前、*ポート*オーケストレーションで表示される、列が、ポートの名前を示します。  
  
 このオーケストレーションでは、3 つのポートが作成されます。 最初のポートは、指定したフォルダーから要求メッセージを取得します。 2 番目のポートは、SAP システムにメッセージを送信し、応答を受信します。 3 番目のポートでは、別のフォルダーへの応答を保存します。 そこで：  
  
-   最初のポートは、1 つのスキーマ、つまり、MultipleOrders.xsd のメッセージのみを受け取ります。  
  
-   2 番目のポートは、BAPI_SALESORDER_CREATEFROMDAT2 RFC のスキーマのメッセージを送受信します。 また、同じポートをコミットまたはロールバック、トランザクションに使用されます。 そのため、このポートは、BAPI_TRANSACTION_COMMIT および BAPI_TRANSACTION_ROLLBACK Rfc のスキーマのメッセージも受信します。 これを有効にするのには、それぞれ特定のメッセージ スキーマに対応する、このポートで 3 つの異なる操作が作成されます。  
  
-   2 番目のポートと同様に、このポートもメッセージを受信する 3 つの異なるスキーマを持つ。 そのため、このポートで 3 つの異なる操作を作成する必要はします。  
  
|ポート|[プロパティ]|  
|----------|----------------|  
|FileIn|-設定**識別子**に*FileIn*<br /><br /> -設定**型**に*FileInType*<br /><br /> -設定**通信パターン**に*一方向*<br /><br /> -設定**通信方向**に*受信*|  
|LOBPort|-設定**識別子**に*LOBPort*<br /><br /> -設定**型**に*LOBPortType*<br /><br /> -設定**通信パターン**に*要求-応答*<br /><br /> -設定**通信方向**に*送受信*<br /><br /> 操作を作成する*BAPIMessage*です。<br /><br /> 操作を作成する*CommitMessage*です。 この操作は、コミット メッセージの送信に使用されます。<br /><br /> 操作を作成する*RollbackMessage*です。 この操作は、ロールバックのメッセージの送信に使用されます。|  
|SaveResponse|-設定**識別子**に*SaveResponse*<br /><br /> -設定**型**に*SaveResponseType*<br /><br /> -設定**通信パターン**に*一方向*<br /><br /> -設定**通信方向**に*送信*です。<br /><br /> 操作を作成する*BAPIMessage*です。<br /><br /> 操作を作成する*CommitMessage*です。 この操作は、コミット メッセージに対する応答の保存に使用されます。<br /><br /> 操作を作成する*RollbackMessage*です。 この操作は、ロールバック メッセージに対する応答の保存に使用されます。|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>アクション図形のメッセージを指定し、ポートに接続  
 次の表は、プロパティと、メッセージのアクション図形およびポートにリンクすることを指定するために設定するには、その値を指定します。 示されている名前、*図形*列が上記のオーケストレーションで表示される、メッセージの構築図形の名前を示します。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveInputXML|-設定**メッセージ**に*SendToAdapter*<br /><br /> -設定**操作**に*FileIn.Transaction.Request*|  
|SendToLOB|-設定**メッセージ**に*BAPIMessage*<br /><br /> -設定**操作**に*LOBPort.BAPIMessage.Request*|  
|ReceiveResponse|-設定**メッセージ**に*BAPIResponse*<br /><br /> -設定**操作**に*LOBPort.BAPIMessage.Response*|  
|SendResponse|-設定**メッセージ**に*BAPIResponse*<br /><br /> -設定**操作**に*SaveResponse.BAPIMessage.Request*|  
|SendBAPICommit|-設定**メッセージ**に*BAPICommitMessage*<br /><br /> -設定**操作**に*LOBPort.CommitMessage.Request*|  
|ReceiveCommitResponse|-設定**メッセージ**に*BAPICommitResponse*<br /><br /> -設定**操作**に*LOBPort.CommitMessage.Response*|  
|SendResponse2|-設定**メッセージ**に*BAPICommitResponse*<br /><br /> -設定**操作**に*SaveResponse.CommitMessage.Request*|  
|SendBAPIRollback|-設定**メッセージ**に*BAPIRollbackMessage*<br /><br /> -設定**操作**に*LOBPort.RollbackMessage.Request*|  
|ReceiveRollbackResponse|-設定**メッセージ**に*BAPIRollbackResponse*<br /><br /> -設定**操作**に*LOBPort.RollbackMessage.Response*|  
|SendResponse3|-設定**メッセージ**に*BAPIRollbackResponse*<br /><br /> -設定**操作**に*SaveResponse.RollbackMessage.Request*|  
  
 これらのプロパティを指定した後、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
## <a name="handling-exceptions"></a>例外の処理  
 BAPI のトランザクションを実行するような複雑なオーケストレーションでは、重要なは、オーケストレーションの状態の追跡、発生すると、問題を解決できるように、発生すると、エラーを報告することです。 BizTalk オーケストレーションでは、トランザクション、補正、および例外処理を通じて発生する問題を解決して、オーケストレーションの状態を維持するために、エラーを処理するためのツールを提供します。  
  
 オーケストレーション デザイナーにはトランザクションと例外処理のフレームワーク、として、**スコープ**図形です。 スコープには、トランザクションの種類、補正、および任意の数の例外ハンドラーを設定できます。 1 つのスコープには、1 つ以上のブロックが含まれます。 本文が含まれると、必要に応じて、任意の数の例外処理ブロックが追加されます。 スコープには、BAPI トランザクションの場合、オーケストレーション全体を含めることできます (前の図を参照してください)。  
  
 例外をキャッチを追加する必要があります、**例外のキャッチ**オーケストレーションをブロックします。 **例外をキャッチ**の末尾に関連付けられているブロック、**スコープ**オーケストレーション デザイナーでの図形です。 BAPI のトランザクションの場合は、「中止」ルーチンを追加する必要があります、**例外のキャッチ**ブロック、つまり、「中止」ルーチンに次を追加する必要があります。  
  
-   (入力メッセージから要求メッセージを抽出) を変換し (プロパティを設定するコンテキスト) メッセージの割り当て図形で構成されるメッセージの構築図形  
  
-   送信図形と受信図形。  
  
 SAP トランザクションのサンプルを[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)](SAPTransaction) が付属[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]例外処理、すぎるを示しています。 このサンプルの詳細については、次を参照してください。 [SAP アダプターのサンプル](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)です。  
  
 例外を処理する方法の詳細については、次を使用して一般に、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[トランザクションを使用して、例外処理](../../core/using-transactions-and-handling-exceptions.md)です。
  
## <a name="add-the-biztalk-property-schema-to-biztalk"></a>BizTalk プロパティ スキーマの BizTalk への追加します。  
 BizTalk プロジェクトでアセンブリを BizTalk プロパティ スキーマへの参照を追加した[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 BizTalk アプリケーション、つまり、BizTalk プロジェクトが配置されるアプリケーションにリソースとして、同じアセンブリを追加する必要があります。 スキーマ ファイル*Microsoft.Adapters.SAP.BiztalkPropertySchema.dll*がインストールされている、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]通常セットアップ\<インストール ドライブ\>: \Program Files\Microsoft BizTalk アダプターPack\bin です。 このリソースせずいないことができます、プロジェクトを配置します。  
  
#### <a name="to-add-an-assembly-as-a-resource-in-biztalk"></a>BizTalk のリソースとしてアセンブリを追加するには  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  コンソール ツリーで  **BizTalk グループ**、展開**アプリケーション**、および BizTalk アセンブリを追加するアプリケーション、します。  
  
3.  右クリック**リソース**、 をポイント**追加** をクリックし、 **BizTalk アセンブリ**です。  
  
4.  **リソースの追加**ダイアログ ボックスで、をクリックして**追加**は、BizTalk アセンブリ ファイルを含むフォルダーに移動し、BizTalk アセンブリ ファイルを選択し、をクリックして**開く**です。  
  
5.  **オプション**、GAC に BizTalk アセンブリをインストールするためのオプションを指定し、クリックして**OK**です。  
  
 これで、BizTalk ソリューションをビルドしして、BizTalk Server に展開する必要があります。 詳細については、次を参照してください。[のビルドおよび実行されているオーケストレーション](../../core/building-and-running-orchestrations.md)です。
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 以前に作成したオーケストレーションが下に表示、BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。 BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。 アプリケーションの構成の詳細については、次を参照してください。[アプリケーションを構成する方法](../../core/how-to-configure-an-application.md)です。
  
 アプリケーションの構成が含まれます。  
  
-   アプリケーションのホストを選択します。  
  
-   BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。 このオーケストレーションの次の操作を行う必要があります。  
  
    -   ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポート上の場所を定義します。 BizTalk オーケストレーションは、要求メッセージを消費し、SAP システムに送信します。  
  
    -   ハード ディスクと、対応する file ポートを BizTalk オーケストレーションが SAP システムからの応答を含む応答メッセージをドロップする場所に場所を定義します。  
  
    -   SAP システムにメッセージを送信する物理 Wcf-custom または WCF SAP 送信ポートを定義します。 ポートを作成する方法については、次を参照してください。 [SAP アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)です。 送信は、送信ポートし 2 つ以上のスキーマに準拠したメッセージを受信し、2 つの操作を実行、ために、動的操作の両方の操作を設定する必要があります。 アクションの詳細については、次を参照してください。 [SAP システムの SOAP アクションを構成する](../../adapters-and-accelerators/adapter-sap/configure-the-soap-action-for-the-sap-system.md)です。 WCF カスタムを作成中に次の重要な考慮事項に従う必要がまたは WCF SAP 送信トランザクションを実行するポートを確認します。  
  
        |次を設定します。|この値を|  
        |-----------------------|-------------------|  
        |操作|送信ポートは、1 つ以上の操作に関するメッセージを送受信します。 それで、操作ごとに、送信ポートでアクションを設定する必要があります。<br /><br /> `<BtsActionMapping>   <Operation Name="BAPIMessage" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/BAPI_SALESORDER_CREATEFROMDAT2" />   <Operation Name="CommitMessage" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/BAPI_TRANSACTION_COMMIT" />   <Operation Name="RollbackMessage" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/BAPI_TRANSACTION_ROLLBACK" /> </BtsActionMapping>`|  
        |EnableBizTalkCompatibilityMode|このバインディングのプロパティを設定**True**です。|  
        |EnableConnectionPooling|このバインディングのプロパティを設定**False**すべてのトランザクションを実行する前にします。 アダプターと BizTalk 間設定チャネルが予期せず終了しましたのシナリオでは、対応する接続が接続プールに追加されます。 別のチャネルを開くし、新しいチャネルが同じ接続オブジェクトを取得、古い接続オブジェクトでコミットされていないトランザクションもコミットされます新しいチャネル経由で、トランザクションがコミットされたときにします。 これを回避するには、接続プールを使用できないトランザクションの実行中にします。|  
  
        > [!NOTE]
        >  使用してスキーマを生成する、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 (発信) の送信ポートを作成または受信ポート (着信)、BizTalk Server 管理コンソールから、このバインド ファイルをインポートすることができます。 詳細については、次を参照してください。 [sap ポートのバインド ファイルを使用して物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)です。
  
        > [!IMPORTANT]
        >  WCF カスタム バックアップ トランスポートを構成するか、SAP WCF 送信ポート、主要なトランスポートは、関数が失敗した場合、別の SAP システムにメッセージを送信することができます。 ただし、トランザクションを実行する SAP システムで、WCF ベース[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]は別の SAP サーバーを指すバックアップ トランスポートを指定することをサポートしていません。  
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 SAP システムのトランザクションを実行する BizTalk アプリケーションを開始する必要があります。 BizTalk アプリケーションの起動方法の詳細については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)、[アプリケーションを起動する方法](../../core/how-to-start-and-stop-a-biztalk-application.md)です。
  
 この段階で確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   SAP システムにメッセージを送信する Wcf-custom または SAP WCF 送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 アプリケーションを実行した後に、定義済みの場所で、オーケストレーションの要求メッセージを削除する必要があります。 要求メッセージが、インスタンスの MultipleOrders.xsd スキーマする特定のスキーマに従う必要があります。 たとえば、要求メッセージを SAP システムでの販売注文を作成し、操作をコミットします。  
  
```  
<ns0:Orders xmlns:ns0="http://BAPISend.MultipleOrders">  
  <Order>  
      <ORDER_HEADER_IN>  
        <DOC_TYPE>TA</DOC_TYPE>  
        <SALES_ORG>1000</SALES_ORG>  
        <DISTR_CHAN>10</DISTR_CHAN>  
        <DIVISION>00</DIVISION>  
        <SALES_OFF>1000</SALES_OFF>  
        <REQ_DATE_H>20060901</REQ_DATE_H>  
        <PURCH_DATE>20060901</PURCH_DATE>  
        <PURCH_NO_C>Cust A</PURCH_NO_C>  
        <CURRENCY>EUR</CURRENCY>  
      </ORDER_HEADER_IN>  
      <ORDER_ITEMS_IN>  
          <MATERIAL>P-109</MATERIAL>  
          <PLANT>1000</PLANT>  
          <TARGET_QU>ST</TARGET_QU>  
      </ORDER_ITEMS_IN>  
      <ORDER_PARTNERS>  
          <PARTN_ROLE>AG</PARTN_ROLE>  
          <PARTN_NUMB>0000000257</PARTN_NUMB>  
      </ORDER_PARTNERS>  
    <RETURN></RETURN>  
  </Order>  
  <isCommit>true</isCommit>  
  <BAPI_TRANSACTION_COMMIT>  
  </BAPI_TRANSACTION_COMMIT>  
</ns0:Orders>  
```  
  
 オーケストレーションはメッセージを処理して、SAP システムに送信します。 SAP システムからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。 上記の要求メッセージの 2 つの応答メッセージを取得する — BAPI_SALESORDER_CREATEFROMDAT2 RFC と BAPI_TRANSACTION_COMMIT を使用して、コミット操作の呼び出しのいずれか。  
  
 BAPI_SALESORDER_CREATEFROMDAT2 に対する応答は次のとおりです。  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<BAPI_SALESORDER_CREATEFROMDAT2Response xmlns="http://Microsoft.LobServices.Sap/2007/03/Rfc/">  
  <SALESDOCUMENT />   
  <ORDER_ITEMS_IN>  
    <BAPISDITM xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
      <ITM_NUMBER>0</ITM_NUMBER>   
      <HG_LV_ITEM>0</HG_LV_ITEM>   
      <PO_ITM_NO />   
      ......  
    </BAPISDITM>  
  </ORDER_ITEMS_IN>  
  <ORDER_PARTNERS>  
    <BAPIPARNR xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
      <PARTN_ROLE>AG</PARTN_ROLE>   
      <PARTN_NUMB>0000000257</PARTN_NUMB>   
      <ITM_NUMBER>0</ITM_NUMBER>   
      ......   
    </BAPIPARNR>  
  </ORDER_PARTNERS>  
</BAPI_SALESORDER_CREATEFROMDAT2Response>  
```  
  
 BAPI_TRANSACTION_COMMIT に対する応答は次のとおりです。  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<BAPI_TRANSACTION_COMMITResponse xmlns="http://Microsoft.LobServices.Sap/2007/03/Rfc/">  
  <RETURN>  
    <TYPE xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <ID xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <NUMBER xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">0</NUMBER>   
    <MESSAGE xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <LOG_NO xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <LOG_MSG_NO xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">0</LOG_MSG_NO>   
    <MESSAGE_V1 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <MESSAGE_V2 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <MESSAGE_V3 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <MESSAGE_V4 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <PARAMETER xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <ROW xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">0</ROW>   
    <FIELD xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <SYSTEM xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
  </RETURN>  
</BAPI_TRANSACTION_COMMITResponse>  
```  
  
> [!NOTE]
>  要求メッセージには、BAPI_TRANSACTION_ROLLBACK RFC が呼び出され、2 番目の応答の BAPI_TRANSACTION_ROLLBACK になります。  
  
## <a name="possible-exceptions"></a>可能性のある例外  
 例外については、BizTalk Server を使用して SAP システムでトランザクションを実行中に発生する可能性が、次を参照してください。[例外とエラー処理、SAP アダプター](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md)です。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開して、BizTalk プロジェクトを構成することが後、は、バインド ファイルと呼ばれる XML ファイルに構成設定をエクスポートできます。 バインド ファイルを生成したできるように、送信ポートを作成し、同じオーケストレーション用のポートを受信する必要はありません、ファイルから構成設定をインポートすることができます。 バインド ファイルの詳細については、次を参照してください。[を再利用の SAP アダプターのバインド](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)です。  
  
## <a name="see-also"></a>参照  
[BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)